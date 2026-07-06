# Facturador

Calcula la factura (resultados de la factura sin crear documento)

[(potencia + energia) * impuesto_electricidad + alquiler_equipo_medida + FEE] * IVA

Esto incluye

1. Término potencia (se obtienen de una tabla tarifa-termino_potencia (BOE))
[https://www.boe.es/diario_boe/txt.php?id=BOE-A-2023-26251](https://www.boe.es/diario_boe/txt.php?id=BOE-A-2023-26251)
2. Término energía = (precio_compra + precio_desvio * 0.3) * consumo
    1. precio_compra
    2. desvíos Ese 0,3 es inventado y posiblemente mucho.
    ingebau solo es 0,0015 €/KWh [https://ingebau.com/tarifas/](https://ingebau.com/tarifas/)
    3. consumo
    4. % impagos
3. Impuesto electricidad (BOE)
    1. ahora 4.864%
    2. ahora 1.05113
4. Alquiler de equipo de medida / Contador (BOE, 0.81)
5. FEE (lo ponemos nosotros, la idea es ir bajando con la antigüedad)
    1. NO sabemos si hay que aplicarle el impuesto de electricidad
6. IVA

codigo QR ->