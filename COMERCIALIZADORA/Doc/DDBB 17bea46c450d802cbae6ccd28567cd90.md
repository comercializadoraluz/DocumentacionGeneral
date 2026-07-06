# DDBB

https://app.diagrams.net/#G1m155nDZoY44pdHZirmVefrS_e5BSva-j#%7B%22pageId%22%3A%2255yUbBlAOaXlAWXzbGLn%22%7D

- **Escritura de datos maestros**: Exclusiva del repositorio **DB**, gestionada mediante pipelines para versionado y calidad.
- **Lectura**: Disponible para todos los microservicios.
- **Escritura**: Restringida al microservicio responsable de cada tabla. Por ejemplo, la API **Contratador** escribe en `contratos`, mientras otros microservicios, como **Facturador**, solo tienen acceso de lectura.
- **Enfoque**: Priorizar velocidad de desarrollo y facilidad de mantenimiento.
- **Caché/redis**: No se implementará por ahora para evitar complejidad innecesaria.
- **API Gateway**: Se evaluará su incorporación más adelante.