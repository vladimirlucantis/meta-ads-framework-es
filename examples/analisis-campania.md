# Ejemplo: Análisis de campaña con detección de estrategia

Este ejemplo muestra cómo responde el skill cuando un usuario comparte un informe y el skill primero identifica la estrategia antes de diagnosticar.

## Caso 1: FRIA + CALIENTE (detección por nombres de ad sets)

### Prompt del usuario

> Te comparto datos de mi campaña de mensajes. 14 días corriendo, USD 60 total.
>
> **AD SET FRIA - Advantage+** (USD 40)
> - 105 conversaciones, costo/conv USD 0.38, CTR 3.2%, frecuencia 1.7
>
> **AD SET CALIENTE - IG engagers + web visitors** (USD 20)
> - 12 conversaciones, costo/conv USD 1.66, CTR 1.8%, frecuencia 3.4
>
> ¿Qué hago?

### Respuesta del skill

Veo que estás usando estrategia FRIA + CALIENTE (prospecting + retargeting). Los umbrales se aplican separadamente a cada audiencia.

**Dashboard**

| Métrica | FRIA | CALIENTE | Total |
|---|---|---|---|
| Gasto | USD 40 | USD 20 | USD 60 |
| Conversaciones | 105 | 12 | 117 |
| Costo/conv | USD 0.38 | USD 1.66 | USD 0.51 |

**Diagnóstico**

FRIA → aceptable. Costo/conv USD 0.38 dentro del umbral (< USD 0.65). Frecuencia 1.7 sana. Mantener.

CALIENTE → pausar. Dos señales de pausa:
- Costo/conv USD 1.66 supera umbral (> USD 1.00)
- Frecuencia 3.4 supera umbral CALIENTE (> 3.0)
- Además el ratio está invertido: CALIENTE debería convertir más barato que FRIA, no al revés

**Plan de acción**

PAUSAR: Ad set CALIENTE completo
MANTENER: FRIA sin tocar
CREAR: Reel nuevo específico para retargeting, probablemente el CALIENTE está usando el mismo creativo que FRIA

Próxima revisión: 7 días con el creativo nuevo listo.

---

## Caso 2: Advantage+ puro (detección por un solo ad set + nombre)

### Prompt del usuario

> Tengo una campaña de ventas en mi tienda de ropa. 21 días, USD 450 gastados.
>
> **Advantage+ Shopping Campaign**
> - 1 ad set, 8 anuncios adentro
> - ROAS 2.8
> - Costo por compra USD 18
> - Frecuencia 2.2
> - CTR 1.4%
>
> El ROAS vino bajando de 3.5 a 2.8 en las últimas 2 semanas. ¿Lo pauso?

### Respuesta del skill

Veo que estás usando Advantage+ Shopping Campaign. Los umbrales son distintos a una estrategia manual: la frecuencia tolerable es más alta y el período de aprendizaje es de 10-14 días, no 7.

**Diagnóstico**

ROAS 2.8 → aceptable (umbral excelente > 3.0, aceptable 1.5-3.0). El descenso de 3.5 a 2.8 es preocupante pero todavía está en zona rentable.

Frecuencia 2.2 → dentro del umbral Advantage+ (< 2.5). No es causa de pausa.

CTR 1.4% → aceptable para ventas (umbral 1-2%).

**NO pausar.** Acciones recomendadas:

1. Revisar los 8 anuncios dentro del ad set. Probablemente 1-2 están arrastrando el promedio para abajo
2. Identificar el creativo ganador por ROAS individual y considerar hacer un ad set propio para él
3. Filmar 2-3 creativos nuevos para rotar antes de que la frecuencia supere 2.5

**Insight**

El descenso de ROAS en Advantage+ suele ser fatiga de catálogo/creativo, no problema estructural. Antes de cambiar estrategia, rotá creativos.

---

## Caso 3: Estrategia ambigua (el skill pregunta)

### Prompt del usuario

> Analizá mis campañas, te paso el reporte.
>
> Campaña 1: USD 85 gastados, 42 leads, costo/lead USD 2.02
> Campaña 2: USD 120 gastados, 18 leads, costo/lead USD 6.67
>
> Son para un servicio de consultoría financiera.

### Respuesta del skill

Antes de analizarte esto en detalle, necesito contexto de estrategia.

1. **¿Cómo estructurás las campañas?** ¿Usás Advantage+, segmentación manual por intereses, separación FRIA/CALIENTE, creative testing, o una mezcla?

2. **¿Las dos campañas apuntan a lo mismo?** Si apuntan a diferentes objetivos (ej: una a prospecting, otra a retargeting) los umbrales se evalúan separadamente. Si apuntan a lo mismo con distinta estrategia, estás duplicando audiencias y fragmentando la optimización.

3. **¿Qué es "costo/lead" en tu caso?** ¿Es un formulario en el sitio, un mensaje de WhatsApp, una llamada agendada?

Te pregunto porque con los datos actuales:
- USD 2.02/lead está excelente para consultoría financiera
- USD 6.67/lead está en zona aceptable, pero el 3x de diferencia entre campañas merece investigación

Pero sin saber la estrategia no puedo decirte con certeza si pausar la más cara, fusionarlas, o dejarlas correr.

---

## Caso 4: Creative testing

### Prompt del usuario

> Lancé un ad set con 5 creativos para testear cuál convierte mejor en mi taller de pastelería. 10 días corriendo, USD 50 gastados.
>
> - Ad 1 "Hook dolor" - 12 mensajes, USD 0.42/conv
> - Ad 2 "Testimonio" - 18 mensajes, USD 0.28/conv
> - Ad 3 "Producto en uso" - 4 mensajes, USD 1.25/conv
> - Ad 4 "Behind the scenes" - 9 mensajes, USD 0.56/conv
> - Ad 5 "Oferta directa" - 2 mensajes, USD 2.50/conv

### Respuesta del skill

Veo que estás usando creative testing. Cada creativo se evalúa contra el promedio del ad set.

**Promedio del ad set: USD 0.56/conv**

**Ranking**

| Posición | Ad | Conv | Costo/conv | vs promedio | Estado |
|---|---|---|---|---|---|
| 1 | Testimonio | 18 | USD 0.28 | 0.5x | Estrella |
| 2 | Hook dolor | 12 | USD 0.42 | 0.75x | Fuerte |
| 3 | Behind the scenes | 9 | USD 0.56 | 1.0x | Promedio |
| 4 | Producto en uso | 4 | USD 1.25 | 2.2x | Pausar |
| 5 | Oferta directa | 2 | USD 2.50 | 4.5x | Pausar |

**Plan de acción**

PAUSAR: Ad 3 "Producto en uso" y Ad 5 "Oferta directa" (ambos superan 2x el promedio)

ESCALAR GANADOR: Sacá "Testimonio" de este ad set y armale un ad set propio con USD 10/día. Dejalo correr 7 días.

MANTENER EN TESTING: Ad 2 "Hook dolor" y Ad 4 "Behind the scenes" tienen data suficiente, pueden convivir con nuevos challengers.

CREAR: 3 variantes nuevas para testear contra "Testimonio" en un ad set paralelo. Probá distintos testimonios, no mismo formato repetido.

**Insight**

Los testimonios consistentemente ganan en rubros de servicio/artesanal. Considerá grabar 2-3 testimonios más de clientes que ya pasaron por el taller.
