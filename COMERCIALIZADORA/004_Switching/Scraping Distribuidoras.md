# Scraping Distribuidoras

Se puede pedir acceso a las distris antes de tener clientes de esas distris

Importante que los clientes vengan de las distris grandes las otras son un coñazo, algunas están en ASEME o CIDE (conjunto de distris) y otras muy peques por email

Fran sabe de sobre cómo funciona pq lo ha tenido que automatizar dos veces.

Problemas: Dónde se ejecuta? Puede tardar 40-50min e igual tardamos demasiado, en ingebau era tarea programada en un pc

cuantos dias atras

donde lo guardamos y cómo, 

tmb en base de datos?

van a cambiar los xmls, de neuro energia

- Scraping de cada distri
- Lectura de xml

flujos: enlace de la cnmc → [https://cambiodecomercializador.cnmc.es/cnmc-e-v24-20191217-1](https://cambiodecomercializador.cnmc.es/cnmc-e-v24-20191217-1)
buscar nuevos (no es preciso este procedimiento) en site:cambiodecomercializador.cnmc.es

[xsd para leer y crear los xml](xsd_para_leer_y_crear_los_xml.md)

xsd mirar si se puede obtener el xml completo con sus campos (en principio sí)

una lamba para descargas por cada distri,  una lamba (unica) para procesar con evento de S3 cuando alguna de las lambas de scraping distris descargue algo

qué meter en la tabla? todos los campos o solo los utiles

estructura de tabla

una principal con id, tipo, paso, version de procesador…¿?

Una tabla de cada tipo de comunicación, fk a la tabla principal

Guardar los xml en glacier a partir 1mes en S3.

obtener tipo archivo → transformar con esquema xsd correspondiente → guardar en base de datos en tabla correspondiente

que hacer si cambia un campo de la tabla? _old? nuevo campo y el resto null?

donde guardar las contraseñas? keeper api? Automatizar el cambio de contraseña periodico? guau (a veces se necesita el telefono movil)

[AWS Secrets Manager o keeper api?](AWS_Secrets_Manager_vs_keeper_api.md)

[https://github.com/gisce/switching/tree/master](https://github.com/gisce/switching/tree/master)

![image.png](Assets/image.png)

Este esquema indica la idea de juanmi de una lambda por cada distri y otra lambda para procesar cada vez que haya un archivo en S3, un evento.

![image.png](Assets/image%201.png)

Estructura de base de datos:
https://chatgpt.com/share/673db0e4-f4f0-800d-8812-e3cf7aa00fa9

![image.png](Assets/image%202.png)

![image.png](Assets/image%203.png)

Al leer el archivo de manera binaria obtenemos el hash, esto lo podemos usar para comparar con una tabla de fichero/hash (o con metadatos de S3) Y no tener que procesar todos los archivos que nos descargamos, solo aquellos que no tenemos en S3