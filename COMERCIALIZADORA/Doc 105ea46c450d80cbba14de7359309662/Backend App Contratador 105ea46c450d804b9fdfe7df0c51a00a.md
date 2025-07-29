# Backend: App Contratador

Verifica solvencia, datos del cliente, crea el pdf del contrato, se conecta a la API de firma de contratos(la que manda sms y pdf al cliente para que lo firme), avisa a compras

1. Verificar datos del cliente [https://nominatim.org/release-docs/develop/](https://nominatim.org/release-docs/develop/) y validaciones del estilo que sea de península
2.  Una vez estemos seguros, verificamos solvencia
3. Generar PDF de contrato (De la API de PDFs)
[https://comercializadora.electricadecadiz.es/tarifa-indexada#componentes](https://comercializadora.electricadecadiz.es/tarifa-indexada#componentes)
4. Api de firma y para que el cliente firme. 

Flujo de datos de APP contratador:

Web contrador se conecta con la App contratador. App contratador se conecta con las apis de validador, solvencia, generador de pdfs y firma.

![image.png](Backend%20App%20Contratador%20105ea46c450d804b9fdfe7df0c51a00a/image.png)

Datos necesarios:

- Nombre
- Apellidos
- DNI / NIE
- Telefono
- Investigar bases de datos que asocien CUPS con direccion. Y cuando pones direcciones que te vaya saliendo codigo postal, calle, pisos…. [https://octopusenergy.es/unete/datos-personales](https://octopusenergy.es/unete/datos-personales) Octopus no los relaciona, te obliga a poner los dos.
- 

Diseño de PDF:

Según chatgpt es mejor APIs, usando lambdas.

Firma: webhook, lambda no estaría mas de 15min

EN cuanto a la api de terceros para la firma, cuando le mandamos el pdf para firmar , tmb le mandamos un endpoint (webhook) para que esa api de terceros nos mande el pdf firmado por el cliente (siempre y cuando sea compatible) En caso contrario habrá que hacer polling

polling (llamar a cada rato a para ver si ha cambiado el estado de la firma)

2024/11/15

Entre repo monolítico, librería y apis, se elije de primeras repo monolitico, ahorraremos tiempo de cara a desarrollo, mantenimiento y no creemos que vayamos a necesitar que los servicios tengan que escalar por separado, al menos a corto/medio plazo. Si a largo plazo lo necesitaramos 3/5 años, podríamos crear esos servicios por separado. 
El repo tendrá diferentes secciones Validador, Solventador, Pdfcontratador, firmardor

lambda vs EC2

No vemos bien usar una lambda por cada servicio, porque tendría que tener su propio requirements.txt y para desarrollador un coñazo

Usar una sola lambda no sabemos exactamente si se puede hacer, porque puede que necesitemos demasiado recursos. Juanmi comenta que igual se puede configurar para que cada endpoint tenga recursos diferentes (aunque sea dentro de una misma funcion lambda)(cree que no se puede)

Quizas podríamos usar mas de una lambda ya que son baratas, pero en cualquier caso solo usar un requirements (porque es mas sencillo desarrollar) aunque eso implicara que tardara mas en importar libreria que uno mismo no necesita.

Conclusión REPO MONOLITICO SEGURO, lambda unica(por confirmar cuando desarrollemos) y si es mas de una lambda, un solo requirements

01/01/2025

https://nominatim.org/release-docs/latest/api/Search/

https://mapsplatform.google.com/intl/es/pricing/

https://developers.google.com/maps/documentation/address-validation/support?hl=es-419

[https://www.postcode.eu/es/products/address-api](https://www.postcode.eu/es/products/address-api)

14/01/2025
[https://sede.cnmc.gob.es/tramites/energia-electricidad-energia-gas/bases-de-datos-de-consumidores-y-puntos-de-suministro](https://sede.cnmc.gob.es/tramites/energia-electricidad-energia-gas/bases-de-datos-de-consumidores-y-puntos-de-suministro)
SIPS

10/07/2025

habria que pensar en los P0 sirven para vlaidar

bases de datos de contratador:

- cliente tabla
    - id
    - nombre
    - primer_apellido
    - segundo_apellido (opcional)
    - nif_nie
    - telefono_codigo_pais  → “(ES) +34”
    - numero_telefono
    - email
    - misma direccion suministro que direccion facturacion TRUE FALSE
    - estado ?¿?¿
- cliente_direccion_suministro tabla
    - id
    - id_cliente_tabla
    - tipo_de_via
    - nombre_de_via
    - numero
    - piso (opcional)
    - bloque (opcional)
    - escalera (opcional)
    - puerta (opcional)
    - informacion_adicional (opcional)
    - codigo_postal
    - localidad
    - provincia
    - CUPS
- cliente_direccion_facturacion tabla
    - id
    - id_cliente_tabla
    - nombre_completo
    - nif_del_titular
    - email_del_titular
    - direccion
    - direcicon (opcional)
    - direccion(opcional)
    - localidad
    - codigo_postal
- contrato
    - id
    - id_cliente
- producto
    - Por ahora solo hay un producto, indexado