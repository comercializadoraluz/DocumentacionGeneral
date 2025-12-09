# Mercado electrico BOEs

[Rango de legislación en España](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/Rango%20de%20legislacio%CC%81n%20en%20Espan%CC%83a%2019dea46c450d80f1a94dd91c1179d45b.md)

[Entérate de los cambios del mercado eléctrico:](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/Ente%CC%81rate%20de%20los%20cambios%20del%20mercado%20ele%CC%81ctrico%20194ea46c450d80fabaa4f9b28e5d51d4.md)

# BOES PEAJES Y CARGOS

- CARGOS (Cargos, Pagos por capacidad, pago a OMIE y bono social)
    - **Real Decreto 148/2021, de 9 de marzo, por el que se establece la metodología de cálculo de los cargos del sistema eléctrico.** [https://www.boe.es/eli/es/rd/2021/03/09/148/con](https://www.boe.es/eli/es/rd/2021/03/09/148/con)
        
        ![image.png](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/image.png)
        
    - **(OK) Orden TED/1487/2024, de 26 de diciembre, por la que se establecen los precios de los cargos del sistema eléctrico y se establecen diversos costes regulados del sistema eléctrico para el ejercicio 2025 y por la que se aprueba el reparto de las cantidades a financiar relativas al bono social y al coste del suministro de electricidad de los consumidores a que hacen referencia los artículos 52.4.j) y 52.4.k) de la Ley 24/2013, de 26 de diciembre, del Sector Eléctrico, correspondiente al año 2025.**
    [https://www.boe.es/diario_boe/txt.php?id=BOE-A-2024-27289](https://www.boe.es/diario_boe/txt.php?id=BOE-A-2024-27289)
        - Resumen (los precios están en orden como vienen en el BOE)
            - Precios de los cargos (normales y VE)
            - Pagos por capacidad
            - OJO a incluir en la factura, el destino del coste de los cargos del sistema electrico
                
                ![image.png](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/image%201.png)
                
            - Pago a OMIE por energía en último PHF de cada Hora
            - Bono social (Poner el de todos en la tabla, no solo comercialización)
- PEAJES (Peajes, exceso de potencia y reactiva)
    - **Circular 3/2020, de 15 de enero, de la Comisión Nacional de los Mercados y la Competencia, por la que se establece la metodología para el cálculo de los peajes de transporte y distribución de electricidad.**
     https://www.boe.es/buscar/act.php?id=BOE-A-2020-1066#top
        - Importancia: 5. (Definición peajes TD) (TD→ Transporte-Distribución)
        - Resumen
            - Niveles de tensión tarifarios: (NT0, NT1, NT2, NT3, NT4)
            - Peajes: 2.0TD, 3.0TD, 6.1-6.4TD. También 2.0TDA, 3.0TDA, 6.1-6.4TDA. En disposición adicional segunda 3.0TDVE, 6.1TDVE
            - Periodos horarios(periodo tarifarios) por región y tarifa(peaje)
            - Peajes de aplicación para contratos de duración inferior a un año (de instalación, si cambia antes del año no aplica)
            - Artículo 9. Forma de facturar el termino de energia y potencia de los peajes y excesos de potencia y energía reactiva.
            - Referencia a tipos de medida Tipo1, 2, 3, 4 y 5  (El residencial es el 5) ([https://www.boe.es/buscar/act.php?id=BOE-A-2007-16478](https://www.boe.es/buscar/act.php?id=BOE-A-2007-16478) **Artículo 7. Clasificación de los puntos de medida y frontera.** )
            - Coeficientes de pérdidas. De contador a barras de central. IMPORTANTE
            - Metodología para el calculo de los peajes(la suda pero a finales de 2025 igual cambia la metodología)
        - Resolución de dudas sobre la nueva tarifa:
        [https://www.cnmc.es/file/305506/download](https://www.cnmc.es/file/305506/download)
    - **(OK) Resolución de 4 de diciembre de 2024, de la Comisión Nacional de los Mercados y la Competencia, por la que se establecen los valores de los peajes de acceso a las redes de transporte y distribución de electricidad de aplicación a partir del 1 de enero de 2025.**
    [https://www.boe.es/diario_boe/txt.php?id=BOE-A-2024-26218](https://www.boe.es/diario_boe/txt.php?id=BOE-A-2024-26218)
        - Resumen
            - Precios peajes (potencia/energia distribucion/transporte)
            - Excesos de potencia
                - Si hay cambio de potencia o cambio de temporada, se tendrá en cuenta (obvio)
                - Si se cambia de comercializadora, el recargo por exceso de potencia, lo pagará la COMERCIALIZADORAentrante (Sí, pagará parte la entrante, aunque no fuera cliente suyo todavía) (NO tan obvio)
            - Coeficientes de discriminación por periodo:
                
                ![image.png](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/image%202.png)
                
                Hay dos formas de calcular el exceso de potencia en función del tipo de medida del punto de suministro
                
                - Punto de suministro con tipo de medida 4  y 5 (Baja potencia)
                - Punto de suministro con tipo de medida 1, 2 y 3 (alta potencia) → se tiene en cuenta el coeficiente Kp
                - El sentido del kp es que si solo te has excedido por 15min, pagar por 15min, no una hora (como el caso de tipo de medida 4 y 5 )
                - Los **excesos de potencia** en puntos de medida **tipo 4** se calculan sobre la **potencia máxima alcanzada en cada período de facturación**, sin importar cuánto tiempo haya durado.
                - No se suman horas de exceso, sino que se compara la potencia máxima medida con la contratada en cada período de potencia (P1 y P2).
                - Esto es diferente a los puntos **tipo 1, 2 y 3**, donde los excesos se calculan en base a intervalos de 15 minutos con coeficiente KP
                - Los punto de suministros y tipo de medida se explica en **Circular 3/2020**
            - Facturación reactiva:
- Pagos a REE
    - **(medio ok, podría leer con mas detalle resoluciones a las que alude)
    Resolución de 12 de diciembre de 2024, de la Comisión Nacional de los Mercados y la Competencia, por la que se establece la cuantía de retribución del operador del sistema eléctrico para 2025 y los precios a repercutir a los agentes para su financiación.**
        
        [https://www.boe.es/diario_boe/txt.php?id=BOE-A-2024-26690](https://www.boe.es/diario_boe/txt.php?id=BOE-A-2024-26690)
        
        Para 2025, pago a REE, 200€/mes y 0,16853 euros/MWh por programa horario
        
- Factura mínima:
    - [https://www.boe.es/buscar/act.php?id=BOE-A-2022-4361#dd](https://www.boe.es/buscar/act.php?id=BOE-A-2022-4361#dd) necesitamos tabla distribuidora- numero de telefono- lo sabes por los 4 primeros numeros del CUPS
    - [https://www.boe.es/buscar/act.php?id=BOE-A-2021-7120](https://www.boe.es/buscar/act.php?id=BOE-A-2021-7120) PUNTO 4

[Términos de factura](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/Te%CC%81rminos%20de%20factura%20189ea46c450d8070a965db480e91813e.md)

# GRUPOS DE BOES DE ELECTRICIDAD

- Código de la energía eléctrica BOE: https://www.boe.es/biblioteca_juridica/codigos/codigo.php?id=14&modo=2&nota=0&tab=2&utm_source=chatgpt.com
- [https://www.cnmc.es/sectores-que-regulamos/energia](https://www.cnmc.es/sectores-que-regulamos/energia)
- [https://www.ree.es/es/conocenos/marco-regulatorio/procedimientos-de-operacion](https://www.ree.es/es/conocenos/marco-regulatorio/procedimientos-de-operacion)
- [https://www.cnmc.es/somos-cnmc/sobre-nosotros/normativa/normativa-energia](https://www.cnmc.es/somos-cnmc/sobre-nosotros/normativa/normativa-energia)
- 

# BOES GENERALES

- **Real Decreto 1955/2000, de 1 de diciembre, por el que se regulan las actividades de transporte, distribución, comercialización, suministro y procedimientos de autorización de instalaciones de energía eléctrica.** [https://www.boe.es/buscar/act.php?id=BOE-A-2000-24019](https://www.boe.es/buscar/act.php?id=BOE-A-2000-24019)
    - Resumen
        - Definición de Red de transporte. Líneas iguales o superiores a 220kV
        - Red eléctrica de España, Sociedad Anónima, como operador del sistema y gestor de la red de transporte. Obligaciones.
        - Calidad de servicio: Definición de ENS(Energía no suministrada), TIM(Tiempo de interrupción medio) y ID(Indice de disponibilidad). Valores de referencia:
            
            ![image.png](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/image%203.png)
            
        - Importante, CAPÍTULO VI PÉRDIDAS EN LA RED DE TRANSPORTE
        A las ofertas de compra(previsiones) hay que sumarles las pérdidas y por tanto también a las facturas. Hay pérdidas para cada día(No se m
            - Artículo 34.2 
            “Los agentes del mercado, tanto oferentes como demandantes de energía, serán responsables de presentar ofertas de compra y venta de energía en las que internalizarán las pérdidas de la red de transporte que les correspondan por su participación en el mercado de producción”
            - Artículo 35.2 
            ”El operador del sistema, independientemente de la afección que pueda suponer para la liquidación de los agentes, calculará y publicará diariamente los factores de pérdidas reales de cada nudo y la asignación de las pérdidas reales que correspondan a cada sujeto conforme a lo establecido en el procedimiento de operación correspondiente”
            - Nos quedamos en ese ultimo articulo
        
        ### 
        
- **Ley 24/2013, de 26 de diciembre, del Sector Eléctrico.**
[https://www.boe.es/buscar/act.php?id=BOE-A-2013-13645](https://www.boe.es/buscar/act.php?id=BOE-A-2013-13645)
    - Resumen
        
        I : Habla de lo buena que fue la Ley 54/1997, de 27 de noviembre, del Sector Eléctrico, liberalizando el mercado…
        El principal problema ha sido el [Déficit de tarifa](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/De%CC%81ficit%20de%20tarifa%2019eea46c450d80ef9484e6ccc8cacc13.md), que en esta ley fue prohibido aumentar.
        Se crean los cargos del sistema, para pagar principalmente el déficit de tarifa, el RECORE(renovables) y TNP
        
- vulnerable
- vulnerable severo
- **(NO OK LA PARTE DE LOS CAMPOS)Creación de la OCSUM (oficina de cambio de suministro) 
Ya no existe la oficina pero sus labores las lleva la CNMC
Real Decreto 1011/2009, de 19 de junio, por el que se regula la Oficina de Cambios de Suministrador.** https://www.boe.es/buscar/act.php?id=BOE-A-2009-10220
    - Resumen
        
        La oficina ya no existe, las labores la hace la CNMC. De la ley del sector eléctrico de 2013 [https://www.boe.es/buscar/act.php?id=BOE-A-2013-13645](https://www.boe.es/buscar/act.php?id=BOE-A-2013-13645)
        
        ![image.png](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/image%204.png)
        
        - No tan importante
            - La Oficina de Cambios de Suministrador es una sociedad mercantil destinada a garantizar que el derecho al cambio del suministrador de los consumidores de gas se ejerza bajo los principios de transparencia, objetividad e independencia, y que realiza sus funciones simultáneamente en los sectores del gas natural y de la electricidad.
            Es interesante porque pone ejemplos de como lo hacen en Alemania, Francia, Reino Unido y Holanda
            - (DUDA) Habría que saber cuál información  y cuál no ha de considerarse comercialmente sensible, por si alguna vez nos la piden
            - Los datos sobre cambios hay que tenerlos controlados porque la oficina de cambios de suministrador nos lo puede pedir en cualquier momento:
                
                ![image.png](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/image%205.png)
                
            - El accionariado de esta sociedad anónima se forma por :(Ya esta oficina no existe asi que no importa)
                
                ![image.png](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/image%206.png)
                
            - Los informes que crea la oficina de cambios de suministrador le llegan a los socios 10 días antes. 
            Supuestamente tenemos derecho a ser parte del accionariado aunque seamos pequeños… no sé qué cosas implica desde el punto de vista económico… pero nos enteraríamos mas y antes de cambios regulatorios e informes de actualidad del sector. Como ya no existe la oficina, entiendo que ni caso a este apartado.
        - IMPORTANTE
            - MUY IMPORTANTE:
            **Disposición final tercera. Modificación del Real Decreto 1435/2002, de 27 de diciembre, por el que se regulan las condiciones básicas de los contratos de adquisición de energía y de acceso a las redes en baja tensión.
            Están todos los campos que devuelven las distribuidoras, importante leerlo para ver qué info necesitamos**
            - Uno de los objetivos de la oficina de cambios de suministrador es ceder gratuitamente información relativa a la base de datos de suministro de cualquier empresa distribuidora y IMPORTANTE, los clientes en situación de impago aparecerán en esa base de datos
                
                ![image.png](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/image%207.png)
                
        - Campos que debe guardar la distribuidora
            - CUPS
            - Empresa Distribuidora
            - Ubicación del punto de suministro:
                - Tipo de vía, nombre de vía, numero, piso y puerta
                - Población del punto de suministros y el CP(código postal)
                - Provincia
            - Fecha de alta de suministro
            - -
            - Clasificación del punto de suministro (tipo 1,2,3,4 o 5)
            aquí se define, existe una table en nuestra DB con descripción [https://www.boe.es/buscar/act.php?id=BOE-A-2007-16478](https://www.boe.es/buscar/act.php?id=BOE-A-2007-16478)


- Orden TEC/1172/2018, de 5 de noviembre, por la que se redefinen los sistemas eléctricos aislados del territorio no peninsular de las Illes Balears y se modifica la metodología de cálculo del precio de adquisición de la demanda y del precio de venta de la energía en el despacho de producción de los territorios no peninsulares.
 https://www.boe.es/buscar/act.php?id=BOE-A-2018-15515
    - Aquí es donde se promulga que las islas baleares es un solo subsistema Mallorca-Menorca-Ibiza-Formentera.	

# Procedimientos de operación

- **Resolución de 8 de agosto de 2022, de la Secretaría de Estado de Energía, por la que se aprueban procedimientos de operación, para su adaptación a mejoras en relación con las garantías exigidas a los sujetos participantes en el mercado, y a mejoras en la gestión técnica de las medidas en el sistema eléctrico.**
[https://www.boe.es/buscar/doc.php?id=BOE-A-2022-13771](https://www.boe.es/buscar/doc.php?id=BOE-A-2022-13771)
    - (OK) P.O. «10.4 Concentradores de medidas eléctricas y sistemas de comunicaciones»
        - En el PO10.4 se establece el sistema de conexiones entre los concentradores de medidas eléctricas y sus protocolos y requisitos para poder conectarse a ellos. Lo que mas nos interesa es conectarnos al concentrador principal (aunque no es esencial)
        Un concentrador, hace eso, “concentrar”, “recopilar” datos de medida de diferentes tipos de medida (que van del 1 al 5) ([https://www.boe.es/buscar/act.php?id=BOE-A-2007-16478](https://www.boe.es/buscar/act.php?id=BOE-A-2007-16478) **Artículo 7. Clasificación de los puntos de medida y frontera.** ) )
        - Existe el CONCENTRADOR PRINCIPAL, que REE es el responsable, y es el que aglutina la mayor parte de las medidas, luego están los concentradores secundarios, cuyos dueños son distribuidoras y generadoras principalmente.
        La responsabilidad de esos concentradores secundarios es mandar información fehaciente al principal.
        Definición en el PO 10.14:
        ”””El concentrador principal está constituido por un sistema informático que recibe, trata, almacena y difunde los datos de los equipos de medida necesarios para el cálculo y la comprobación de las liquidaciones, facilitando la información al sistema de liquidaciones y garantizando la confidencialidad de la información recibida.”””
        - También incluye el concepto de “registradores de medida”:
        ”””El concentrador principal obtendrá los datos de medidas correspondientes a los puntos de medida mediante la interrogación a registradores de medida, comunicación con concentradores secundarios, o bien mediante el volcado de datos obtenidos tras lecturas locales mediante terminales portátiles de lectura, lecturas visuales o estimaciones.”””
        - Conclusión: Este PO es útil para saber que existe el concentrador Principales, concentradores secundarios y registradores de medida. 
        Nosotros no medimos así que no tenemos que crear un concentrador secundario, ni mandar información al concentrador principal. 
        Aún así, entiendo que es necesario conectarse al concentrador principal para hacer nuestras comprobaciones de medidas/liquidaciones.
            
            
    - P.O. «10.5 Cálculo del mejor valor de energía en los puntos frontera y cierres de energía del sistema de información de medidas eléctricas»
    - P.O. «10.6 Agregaciones de puntos de medida»
    - P.O. «10.11 Tratamiento e intercambio de información entre Operador del Sistema, encargados de la lectura, comercializadores y resto de participantes»
- **Resolución de 2 de junio de 2015, de la Secretaría de Estado de Energía, por la que se aprueban determinados procedimientos de operación para el tratamiento de los datos procedentes de los equipos de medida tipo 5 a efectos de facturación y de liquidación de la energía.** [https://www.boe.es/buscar/act.php?id=BOE-A-2015-6203](https://www.boe.es/buscar/act.php?id=BOE-A-2015-6203) (OJO cuidado que no están actualizados todos los PO en este BOE)
    - P.O. 10.13 «Procedimiento por el que los distribuidores intercambian información con los comercializadores de energía eléctrica, y ponen a disposición de los comercializadores y los consumidores los datos procedentes de los equipos de medida tipo 5 efectivamente integrados en el sistema de telegestión»
        
        

## Otros

[Déficit de tarifa](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/De%CC%81ficit%20de%20tarifa%2019eea46c450d80ef9484e6ccc8cacc13.md)

[Resolución de dudas: PVPC, TUR, CUR, COMERCIALIZADORAde referencia, COMERCIALIZADORAde ultimo recurso…](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/Resolucio%CC%81n%20de%20dudas%20PVPC,%20TUR,%20CUR,%20comercializad%2018eea46c450d8037a8edc1a6f0b54a89.md)

- Códigos QR en la factura
    
    [https://boe.es/diario_boe/txt.php?id=BOE-A-2021-11035](https://boe.es/diario_boe/txt.php?id=BOE-A-2021-11035)
    

[Webs de comercializadoras para entender las factura de la luz](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/Webs%20de%20comercializadoras%20para%20entender%20las%20factur%2018eea46c450d80e6a646fef65d289642.md)

[Glosario](Mercado%20electrico%20BOEs%20161ea46c450d80e59995e668ca3513d2/Glosario%201a5ea46c450d80bbaac2d479046a6a5c.md)

[Calendario Liquidaciones 2025](https://www.ree.es/sites/default/files/12_CLIENTES/Documentos/CalendarioLiquidaciones2025.pdf?utm_source=chatgpt.com)

informes cnmc cambios comercializadora
https://www.cnmc.es/sectores-que-regulamos/energia/informes-de-supervision-de-los-cambios-de-comercializador-de-energia-electrica-y-gas