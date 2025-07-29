# AWS Secrets Manager o keeper api?

se pediría por API 8 contraseñas 3 veces al dia cada una, cual seria mas barata

### ChatGPT Plus

ChatGPT

Se ha buscado 5 sitios

El costo de AWS Secrets Manager se basa en dos componentes principales:

1. **Costo mensual por secreto almacenado**: $0.40 por secreto al mes.
2. **Costo por solicitudes a la API**: $0.05 por cada 10,000 solicitudes​​.
    
    [SaaSworthy](https://www.saasworthy.com/product/aws-secrets-manager/pricing)
    
    [TrustRadius](https://www.trustradius.com/products/aws-secrets-manager/pricing)
    

En tu caso, considerando que harás 24 solicitudes diarias para cada una de las 8 contraseñas (3 solicitudes diarias por contraseña), esto implica:

- **Número de solicitudes mensuales**:8contrasen˜as×3solicitudes/dıˊa×30dıˊas=720solicitudes/mes.
    
    8 contrasen˜as×3 solicitudes/dıˊa×30 dıˊas=720 solicitudes/mes8 \, \text{contraseñas} \times 3 \, \text{solicitudes/día} \times 30 \, \text{días} = 720 \, \text{solicitudes/mes}
    

Esto está muy por debajo del límite de 10,000 solicitudes para el mínimo costo por API ($0.05). Entonces, el costo total sería:

- **Costo mensual por secretos**: 8contrasen˜as×0.40=3.20USD/mes.
    
    8 contrasen˜as×0.40=3.20 USD/mes8 \, \text{contraseñas} \times 0.40 = 3.20 \, \text{USD/mes}
    
- **Costo mensual por API**: $0.05 (mínimo).

En total, el costo estimado sería aproximadamente **$3.25 USD al mes** usando AWS Secrets Manager.

Por otro lado, el costo de **Keeper API** depende del plan que contrates, ya que sus precios suelen estar asociados a usuarios en vez de solicitudes API, lo que podría hacerlo más costoso para este caso en particular si solo necesitas gestionar contraseñas y no usuarios​

[SaaSworthy](https://www.saasworthy.com/product/aws-secrets-manager/pricing)

​

[TrustRadius](https://www.trustradius.com/products/aws-secrets-manager/pricing)

.

Si tu prioridad es la economía y simplicidad, AWS Secrets Manager parece ser una buena opción. Sin embargo, Keeper puede ser más adecuado si prefieres tener un sistema más orientado a gestión centralizada por usuarios.

4o