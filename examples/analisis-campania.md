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

---

## Caso 5: Segmentación manual por intereses

### Prompt del usuario

> Tengo una campaña de ventas para mi tienda de suplementos deportivos. 14 días corriendo, USD 280 gastados. Armé 4 ad sets distintos por interés:
>
> **AD SET Crossfit** (USD 80) - 14 compras, costo/compra USD 5.71, ROAS 3.2, CTR 2.1%, frecuencia 1.6
> **AD SET Running** (USD 70) - 11 compras, costo/compra USD 6.36, ROAS 2.9, CTR 1.8%, frecuencia 1.7
> **AD SET Gimnasio general** (USD 75) - 4 compras, costo/compra USD 18.75, ROAS 1.1, CTR 1.2%, frecuencia 2.4
> **AD SET Nutrición deportiva** (USD 55) - 9 compras, costo/compra USD 6.11, ROAS 3.0, CTR 2.3%, frecuencia 1.5
>
> El ticket promedio es USD 28. ¿Qué hago?

### Respuesta del skill

Veo que estás usando segmentación manual por intereses, con 4 ad sets apuntando a clusters distintos. Los umbrales se aplican por ad set individualmente, no al total de la campaña.

**Dashboard**

| Ad set | Gasto | Compras | Costo/compra | ROAS | Frec |
|---|---|---|---|---|---|
| Crossfit | USD 80 | 14 | USD 5.71 | 3.2 | 1.6 |
| Running | USD 70 | 11 | USD 6.36 | 2.9 | 1.7 |
| Gimnasio general | USD 75 | 4 | USD 18.75 | 1.1 | 2.4 |
| Nutrición deportiva | USD 55 | 9 | USD 6.11 | 3.0 | 1.5 |
| **Total** | USD 280 | 38 | USD 7.37 | 2.7 | — |

**Diagnóstico por ad set**

- **Crossfit** → ganador claro. ROAS 3.2 (excelente), costo/compra 20% del ticket (aceptable), frecuencia sana. Mantener
- **Nutrición deportiva** → fuerte. ROAS 3.0, costo/compra similar al Crossfit. Mantener y considerar escalar +20%
- **Running** → aceptable. ROAS 2.9 en zona buena. Dejar correr una semana más antes de decidir
- **Gimnasio general** → pausar. Tres señales: ROAS 1.1 (< 1.5 umbral de pausa), costo/compra 67% del ticket (> 30%), frecuencia 2.4 supera umbral manual (2.2). El interés es demasiado amplio, no resuena

**Plan de acción**

```
PAUSAR:
- Ad set Gimnasio general - ROAS sub-umbral + frecuencia saturada

MANTENER SIN TOCAR:
- Ad set Crossfit - ganador, no tocar
- Ad set Running - dejar 7 días más

ESCALAR:
- Ad set Nutrición deportiva - subir presupuesto +20% (USD 55 → USD 66) el próximo lunes
- Ad set Crossfit - mismo aumento una semana después si sostiene performance

CREAR:
- Testear 1 ad set nuevo con interés más nichado (ej: "Powerlifting" o "Maratonistas") con el presupuesto liberado de Gimnasio general
```

Próxima revisión: 7 días.

**Insight**

Los intereses amplios como "Gimnasio" suelen perder contra nichos específicos (Crossfit, Running). Cuando tenés audiencias definidas por comportamiento real, el interés genérico no agrega, fragmenta.

---

## Caso 6: WhatsApp/Mensajes puro (objetivo Conversaciones)

### Prompt del usuario

> Tengo un estudio de psicología online. Hago campañas de Mensajes para que me escriban por WhatsApp. 1 sola campaña con 1 ad set, objetivo Conversaciones. 21 días, USD 90 gastados.
>
> - 180 conversaciones iniciadas, costo/conv USD 0.50
> - CTR 3.8%, CPM USD 2.10, frecuencia 2.1
> - De esas 180, cerré 14 pacientes nuevos a USD 50 la primera sesión
>
> El pixel está instalado pero dice "0 conversiones" porque cobro por transferencia. ¿Va bien la campaña?

### Respuesta del skill

Veo que estás usando estrategia WhatsApp/Mensajes puro (objetivo Conversaciones). El pixel no aplica acá: la conversión real ocurre en la conversación, no en el sitio web. Los umbrales son propios de este objetivo.

**Dashboard**

| Métrica | Valor | Estado |
|---|---|---|
| Gasto | USD 90 | — |
| Conversaciones | 180 | — |
| Costo/conversación | USD 0.50 | Aceptable (umbral 0.35-0.65) |
| CTR | 3.8% | Aceptable (2-5%) |
| CPM | USD 2.10 | Aceptable |
| Frecuencia | 2.1 | Dentro de umbral manual (< 2.2) |
| Pacientes cerrados | 14 | — |
| CPA real (USD 90 / 14) | USD 6.43 | — |
| Tasa conversación→paciente | 7.8% | — |

**Diagnóstico**

La métrica que mira Meta (costo/conversación) está en zona aceptable. Pero la métrica que mira tu negocio (costo por paciente nuevo) es USD 6.43 contra un ticket primera sesión de USD 50 → ROAS aproximado 7.7x. Excelente.

El "0 conversiones" del pixel es esperable y no es problema: el pixel no puede ver transferencias bancarias ni cierres por WhatsApp. No perseguir ese número.

**Plan de acción**

```
MANTENER SIN TOCAR:
- La campaña completa. Sub-umbral en ambas capas (conv y paciente)

CONFIGURAR (acción estructural, no urgente):
- Audiencia personalizada con lista de pacientes actuales (necesitás 100+ contactos)
- Una vez cargada, crear lookalike 1% sobre esa audiencia para un ad set nuevo
- Considerar evento offline: subir CSV con teléfonos de pacientes cerrados y fechas, para que Meta atribuya conversiones reales

ESCALAR (si la operación lo soporta):
- Si podés atender más pacientes, subir presupuesto +20% (USD 90/21 días → USD 5.15/día → USD 6.20/día)
- Si la agenda ya está llena, NO escalar, cuidar el costo/conv actual
```

**Insight**

La tasa conversación→paciente del 7.8% es buena para psicología (rubro donde el cierre depende mucho de química y precio). Si bajás de 5%, el problema no es la campaña sino el primer mensaje que mandás por WhatsApp. Vale la pena revisar plantillas de respuesta antes de tocar la campaña.

Próxima revisión: 14 días o cuando termines de configurar la audiencia personalizada de pacientes.
