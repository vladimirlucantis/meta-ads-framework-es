# Umbrales de decisión por métrica

Tablas de referencia para decidir si una métrica está en zona excelente, aceptable o de pausa. Calibradas para cuentas chicas y medianas (USD 50 a USD 1000 mensuales) en mercado hispanohablante.

## Objetivo: Conversaciones (Mensajes)

| Métrica | Excelente | Aceptable | Pausar/revisar |
|---|---|---|---|
| Costo por conversación | < USD 0.35 | USD 0.35 a USD 0.65 | > USD 1.00 |
| CTR (all) | > 5% | 2% a 5% | < 1% |
| CPM | < USD 1.00 | USD 1.00 a USD 2.50 | > USD 3.50 |
| Frecuencia FRIA | < 1.5 | 1.5 a 2.0 | > 2.0 |
| Frecuencia CALIENTE | < 2.5 | 2.5 a 3.0 | > 3.0 |

## Objetivo: Ventas (e-commerce)

| Métrica | Excelente | Aceptable | Pausar/revisar |
|---|---|---|---|
| ROAS | > 3.0 | 1.5 a 3.0 | < 1.5 |
| Costo por compra | < 10% del ticket | 10% a 25% del ticket | > 30% del ticket |
| CTR (all) | > 2% | 1% a 2% | < 0.5% |
| Tasa de conversión | > 3% | 1% a 3% | < 0.5% |

Nota: El ROAS aceptable depende del margen del producto. Un negocio con 70% de margen tolera ROAS más bajo que uno con 20%.

## Objetivo: Tráfico

| Métrica | Excelente | Aceptable | Pausar/revisar |
|---|---|---|---|
| CPC | < USD 0.15 | USD 0.15 a USD 0.40 | > USD 0.60 |
| CTR outbound | > 2% | 1% a 2% | < 0.5% |
| Tasa de rebote en destino | < 60% | 60% a 80% | > 85% |

## Reglas de decisión

### Cuándo pausar un anuncio

Aplica al menos UNA de estas condiciones:

1. Costo por conversión más de 3x el promedio del ad set
2. Cero conversiones con gasto equivalente a 3 conversiones promedio del ad set
3. CTR menor a 0.5% con más de USD 10 gastados
4. Frecuencia superior al umbral (2.0 FRIA / 3.0 CALIENTE) Y costo/conv en deterioro

### Cuándo pausar un ad set completo

Aplica al menos UNA:

1. Todos los anuncios dentro del ad set están en zona de pausa
2. Frecuencia > 3.5 con costo/conv en deterioro durante 7 días seguidos
3. Gasto acumulado USD 30+ con menos de 3 conversiones

### Cuándo escalar

Todas estas condiciones a la vez:

1. Ad set con más de 5 conversiones en los últimos 7 días
2. Costo/conv en zona "excelente" según tabla del objetivo
3. Frecuencia dentro del umbral
4. Mínimo 7 días desde el último cambio en el ad set

Escalar = aumentar presupuesto **máximo +20%**. Nunca duplicar de golpe.

Esperar mínimo 5 a 7 días antes del siguiente aumento.

### Cuándo NO tocar nada

1. Si costo/conv mejora período a período, dejar correr
2. Si el ad set está en fase de aprendizaje (menos de 7 días o 50 eventos de optimización)
3. Si la frecuencia está subiendo pero el costo/conv sigue en zona aceptable

## Consideraciones sobre fatiga creativa

La fatiga no se mide solo por frecuencia. Señales combinadas:

- Frecuencia > umbral
- CTR bajando semana a semana
- Costo/conv subiendo semana a semana
- Mismos usuarios en pixel de retargeting que ya vieron el ad

Si hay 3 de 4 señales, hay fatiga. Acción: rotar creativos, no pausar el ad set.

## Calibración para cuentas fuera del rango típico

### Cuentas muy chicas (< USD 50/mes)

- Los umbrales de frecuencia son más tolerantes (audiencias chicas saturan más rápido)
- Tomar decisiones con más datos (10 días mínimo en vez de 7)
- CPM puede ser mayor por volumen bajo, no siempre es señal de problema

### Cuentas grandes (> USD 5000/mes)

- Este framework no está calibrado para ese segmento
- Recalibrar contra data propia de la cuenta
- Considerar estrategias de Advantage+ Shopping Campaigns
