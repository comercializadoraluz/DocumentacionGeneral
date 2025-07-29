# API Switching

Como primeros pasos:
1.4 módulo archivos intercambios comercializadora (C1,C2,M1,F1) (procesamiento) (Leer(pasos de distri) y escribir(pasos de comer))(Pasos1,2,3,5 y 6 del C1,C2,M1)
Un solo bucket, se levanta una lambda por fichero (Se puede limitar el número de veces simultáneas que una lambda que se puede levantar, con 6h en una cola interna, sin pagar de mas)

- Un Buckect
    
    Solo tendremos una carpeta.
    La carpeta donde el scraping deja los xml descargados es la misma que donde el switching lee, procesar y luego cambia de nombre los xml. Pero no los mueve a otro bucket. Ni siquiera en error.
    hash.xml
    nombre_hash.xml (Para poder filtrar en la carpeta)
    KO_nombre_hash.xml o ko_hash.xlm (SI ha fallado)
    
- Tablas SQL:
    - switching_distris_hash_xml (id, hash)
    - switching_distris_hash_nombre_xml (id, id_hash, ruta_completa, nombre_completo_con_hash, fechahora_creacion)
    - switching_distri_hash_estado_xml(id, id_hash, id_estado, fechahora_creacion)
    - switching_distri_estado_xml(id, estado) (tabla maestra)
    - dia 2025-05-28
        - switching_distris_hash_xml (id, hash)
        - switching_distris_hash_nombre_xml (id, id_hash, ruta_completa, nombre_completo_con_hash, es_valido, fechahora_creacion) (es_valido nunca se cambiará)
        - switching_distri_casos_no_validos(id_switching_distris_hash_nombre_xml, fechahora_resuelto, fechahora_creacion, comentario)
    - dia 2025-07-05 (fran solo)
        - Problematicas:
            - incorporacion de estados → tendrá que haber mas tablas para no perder trazabilidad
            - no saber si es necesaria la tabla →switching_distris_hash_xml
            - distinción de valido-no valido por validacion proceso_paso_anterior o pq no sea correcto el xml o falle el codigo de switching
        
        - sw_distri_xml (id, hash, intento, fechahora_ultimo_cambio_de_estado) (está ultima columna sería repetida) Se cambia este regristro cada vez que hay un cambio de estado, COlumna intento la primera vez se rellena con “1”. Solo en caso de que haya hash ya en la tabla, y su estado sea error, aumentar intento y no borramos la anterior ejecución de error
        - sw_distri_xml_historico_estado(id, id_sw_distri_xml, id_sw_distri_estado, fecha_hora_ingreso)NUNCA se cambia el registro,
        - sw_distri_estado(tabla maestra)(””,procesando, error, secuencia_validada, procesado_acciones_realizadas),
        - ~~sw_distri_estado_error(tabla maestra)(xml_no_validado, no_hay_xsd, no hay dataclass, no hay proceso_paso, no trazabilidad del proceso_paso),~~
        - • ~~sw_distri_estado_error(tabla maestra)(xml_no_validado, no_hay_xsd, no hay dataclass, no hay proceso_paso, no trazabilidad del proceso_paso),~~ Lo errrores lo veremos en los logs
        - ~~sw_distri_xml_errores(id, id_sw_distri_xml , tipo_error, fechahora_resuelto, fechahora_creacion, comentario) Sí puede cambiar el registro, con el comentario y fechahora_resuelto o crear otra tabla de historico de error…,~~
        - sw_distri_xml_detalles(id,id_sw_distri_xml,ruta_completa, nombre_completo_con_hash, CUPS, codigo de solicitud, codigo de paso, secuencia de solicitud, versionCNMC, distribuidora, ~~comercializadora~~, fechahora_creacion del registro),
        - sw_distri_xml_detalles_reclamacion(id,id_sw_distri_xml_detalles, tipo, subtipo, comentarios),
        - sw_distri_xml_detalles_suspension(id,id_sw_distri_xml_detalles, motivo, comentarios
    - REINTENTOS:
        - En el código, lo primero que hacemos es el guardado en la tb sw_distri_xml y sw_distri_xml_historic, pero antes debemos comprobar que o ese registro no existe (con el hash, y poner en la colunmna “intento” un 1) o que si existe, su estado es “error” para el registro con el maximo intento (y la columna “intento” el max intento +1). Y si no que levante excepción (o se termine ahí el programa), pero no cambia nada en base de datos. Esto hace que no se vuelva a procesar algo que estaba bien y no perder trazabilidad de errores
        - Hay dos lambdas, una que procesaba de manera individual cada fichero y otra que llamaba a la primera lambda con un bucle sobre una lista de ficheros.
        En el proceso automatico solo se usa la primera, y se lanza cada vez que hay un fichero nuevo en el bucket
        En el proceso manual se usan las dos (directamente solo la segunda, se le pasa la lista de hash de ficheros a reintentar y ya de la tb coge su path)
        Si ni si quiera entra habria que pasarla por el proceso automatico o permitir que la segunda lambda coja tanto el hash como el path (nada de usar stepfuntion SQS…)
        - En el caso de la ejecución automática se puede reintentar dos veces mas, eso resolvería el caso en el que llegan al mismo bucket dos ficheros por ejemplo paso 02 y 05. Pero para otro tipo de errores, ya sea que el paso 02 no esté o haya fallado el código, habrá que ejecutar la forma manual
        
- Comprobación de ficheros anteriores
    
    Cuando llega un C105, antes de procesar, repasaremos si existe o no un C102 en la tabla SQL.
    SOLO REPASAREMOS EL PASO JUSTO ANTERIOR, solo el anterior pq confiamos en los procesos anteriores se hicieron bien, sumado a que si se quisiera revisar todo el camino para cada proceso sería mucho mas complicada la lógica.
    {C1:
       {”paso” : 1, paso_justamente_anterior:[]},
       {”paso” : 2, paso_justamente_anterior:[1,]},
       {”paso” : 3, paso_justamente_anterior:[2,]},   
       {”paso” : 5, paso_justamente_anterior:[3,5]},
    
    }
    
- Proceso:
    
    Entra en la única carpeta donde está los xml, que es donde el scraping_distris lo deja.
    Lo primero que hace es registrar el hash.xml en las tablas, (todas) 
    Luego comprueba xsd, pero es una funcion independiente. Si funciona OK, si no funciona levanta error.
    Luego habrá un procesador (C1.py) porque cada tipo (o por cada tipo_paso...) ya veremos si usamos factories…
    
    El ultimo paso:
    Estábamos entre leer todos los campos y luego realizar cada una de las tareas (cambiar tabla contratos, mandar email…) o leer cada campo necesario (abrir y cerrar xml, con el problema de rendimiento y memoria usada que puede causar) y realizar tarea correspondiente.
    Optamos por leer todo y ejecutar cada proceso luego. Y cada proceso que use lo necesario. Además cada funcion que use lo que necesite del dataclass ( y vscode permite cambiarlo con el F2)
    
    ```
    from dataclasses import dataclass
    @dataclass
    class contrato:
        name: str
        apellido1: str
        apellido2: str
    
    def function (contratos: contrato):
        nombre = contratos.name
        apellido1 = contratos.apellido1
        apellido2 = contratos.apellido2
    ```