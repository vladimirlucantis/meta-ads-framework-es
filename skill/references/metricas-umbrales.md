# Umbrales de decisión por métrica

Tablas de referencia para decidir si una métrica está en zona excelente, aceptable o de pausa. Calibradas para cuentas chicas y medianas (USD 50 a USD 1000 mensuales) en mercado hispanohablante.

Los umbrales varían según la estrategia de campaña. Antes de aplicar esta tabla, identificar la estrategia (ver `estrategias-campania.md`).

## Objetivo: Conversaciones (Mensajes)

### Umbrales base (agnóstico de estrategia)

| Métrica | Excelente | Aceptable | Pausar/revisar |
|---|---|---|---|
| Costo por conversación | < USD 0.35 | USD 0.35 a USD 0.65 | > USD 1.00 |
| CTR (all) | > 5% | 2% a 5% | < 1% |
| CPM | < USD 1.00 | USD 1.00 a USD 2.50 | > USD 3.50 |

### Umbrales de frecuencia por estrategia

| Estrategia | Frecuencia OK | Alerta | Pausar |
|---|---|---|---|
| Advantage+ (audiencia amplia) | < 2.5 | 2.5 a 3.5 | > 3.5 |
| Segmentación manual por intereses | < 1.8 | 1.8 a 2.2 | > 2.2 |
| FRIA (prospecting) | < 1.5 | 1.5 a 2.0 | > 2.0 |
| CALIENTE (retargeting) | < 2.5 | 2.5 a 3.0 | > 3.0 |
| Creative testing (todos los ads del ad set combinados) | < 2.0 | 2.0 a 2.5 | > 2.5 |

## Objetivo: Ventas (e-commerce)

### Umbrales base

| Métrica | Excelente | Aceptable | Pausar/revisar |
|---|---|---|---|
| ROAS | > 3.0 | 1.5 a 3.0 | < 1.5 |
| Costo por compra | < 10% del ticket | 10% a 25% del ticket | > 30% del ticket |
| CTR (all) | > 2% | 1% a 2% | < 0.5% |
| Tasa de conversión | > 3% | 1% a 3% | < 0.5% |

El ROAS aceptable depende del margen del producto. Un negocio con 70% de margen tolera ROAS más bajo que uno con 20%.

### ROAS por estrategia

- **Advantage+ Shopping**: suele dar ROAS 2.5 a 4.0 en cuentas con volumen suficiente. Evaluar con mínimo 14 días
- **Segmentación manual**: ROAS más variable entre ad sets. Comparar entre ellos para priorizar
- **FRIA**: ROAS más bajo (1.5 a 2.5 es normal) porque es audiencia nueva
- **CALIENTE (retargeting)**: ROAS más alto (4.0+). Si el CALIENTE no supera al FRIA, hay un problema

## Objetivo: Tráfico

| Métrica | Excelente | Aceptable | Pausar/revisar |
|---|---|---|---|
| CPC | < USD 0.15 | USD 0.15 a USD 0.40 | > USD 0.60 |
| CTR outbound | > 2% | 1% a 2% | < 0.5% |
| Tasa de rebote en destino | < 60% | 60% a 80% | > 85% |

## Objetivo: Leads (formularios)

| Métrica | Excelente | Aceptable | Pausar/revisar |
|---|---|---|---|
| Costo por lead | < USD 1.00 | USD 1.00 a USD 3.00 | > USD 5.00 |
| Tasa de apertura del formulario | > 25% | 15% a 25% | < 10% |
| Tasa de completación | > 80% | 60% a 80% | < 50% |

Nota: estos umbrales son para leads de bajo valor (consultas de servicios genéricos). Para leads de alto valor (B2B, servicios premium, inmobiliaria), el costo por lead aceptable es mucho mayor.

## Reglas de decisión

### Cuándo pausar un anuncio

Aplica al menos UNA de estas condiciones:

1. Costo por conversión más de 3x el promedio del ad set
2. Cero conversiones con gasto equivalente a 3 conversiones promedio del ad set
3. CTR menor a 0.5% con más de USD 10 gastados
4. Frecuencia superior al umbral de la estrategia Y costo/conv en deterioro

### Cuándo pausar un ad set completo

Aplica al menos UNA:

1. Todos los anuncios dentro del ad set están en zona de pausa
2. Frecuencia supera el umbral de pausa de la estrategia durante 7 días seguidos
3. Gasto acumulado USD 30+ con menos de 3 conversiones (ajustar según presupuesto diario)

### Cuándo escalar

Todas estas condiciones a la vez:

1. Ad set con más de 5 conversiones en los últimos 7 días
2. Costo/conv en zona "excelente" según tabla del objetivo
3. Frecuencia dentro del umbral de la estrategia
4. Mínimo 7 días desde el último cambio (10-14 días si es Advantage+)

Escalar = aumentar presupuesto **máximo +20%**. Nunca duplicar de golpe.

Esperar mínimo 5 a 7 días antes del siguiente aumento.

### Cuándo NO tocar nada

1. Si costo/conv mejora período a período, dejar correr
2. Si el ad set está en fase de aprendizaje (menos de 7 días o 50 eventos de optimización, más si es Advantage+)
3. Si la frecuencia está subiendo pero el costo/conv sigue en zona aceptable

## Consideraciones sobre fatiga creativa

La fatiga no se mide solo por frecuencia. Señales combinadas:

- Frecuencia > umbral de la estrategia
- CTR bajando semana a semana
- Costo/conv subiendo semana a semana
- Mismos usuarios en pixel de retargeting que ya vieron el ad

Si hay 3 de 4 señales, hay fatiga. Acción: rotar creativos, no pausar el ad set.

La fatiga aparece antes en estrategias con audiencias chicas (retargeting, segmentación manual nichada) y más tarde en estrategias con audiencias amplias (Advantage+).

## Calibración para cuentas fuera del rango típico

### Cuentas muy chicas (< USD 50/mes)

- Los umbrales de frecuencia son más tolerantes (audiencias chicas saturan más rápido)
- Tomar decisiones con más datos (10 días mínimo en vez de 7)
- CPM puede ser mayor por volumen bajo, no siempre es señal de problema
- Advantage+ puede no funcionar bien por falta de volumen. Mejor segmentación manual

### Cuentas grandes (> USD 5000/mes)

- Este framework no está calibrado para ese segmento
- Recalibrar contra data propia de la cuenta
- Considerar estrategias de Advantage+ Shopping Campaigns
- Los umbrales de frecuencia pueden ser más tolerantes por el volumen de audiencia disponible

### Cuentas B2B con ciclo de venta largo

- El costo por lead aceptable es mucho mayor (USD 20-100 vs USD 1-5 en B2C)
- Medir por costo por cliente, no por costo por lead
- Atribución en plataforma no refleja la realidad del cierre (ocurre semanas después)
- Considerar complementar con tracking manual vía CRM
