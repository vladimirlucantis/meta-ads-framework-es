---
name: meta-ads-framework-es
description: >
  Framework profesional de análisis y optimización de campañas de Meta Ads
  (Facebook e Instagram) en español. Usar SIEMPRE que el usuario comparta
  informes de Meta Ads, métricas de campañas, capturas del Administrador de
  Anuncios, preguntas sobre pixel, API de Conversiones, audiencias, creativos,
  diferenciación entre audiencias FRIA y CALIENTE, o decisiones sobre pausar,
  escalar o mantener ad sets. También activar cuando el usuario pida guiones
  de Reels publicitarios, hooks, copy para anuncios, estructura de creativos
  o estrategia de contenido pago. Pensado para consultores, agencias y
  negocios hispanohablantes que operan cuentas propias o de clientes con
  presupuestos chicos y medianos, incluyendo negocios que convierten por
  WhatsApp en vez de checkout web.
license: MIT
metadata:
  author: Vladimir Lucantis
  version: "0.1.0"
  language: es
  category: marketing
---

# Meta Ads Framework (ES)

Framework profesional para análisis de campañas de Meta Ads en español. Aplica umbrales de decisión calibrados, patrones de creativos probados y estructura de respuesta consistente.

## Cuándo activarse

Activar automáticamente cuando el usuario:

- Comparta métricas, informes o capturas del Administrador de Anuncios
- Pregunte sobre pixel, dataset, API de Conversiones o eventos
- Consulte sobre audiencias (personalizadas, lookalike, Advantage+)
- Pida guiones de Reels, hooks o copy para anuncios
- Necesite decidir si pausar, escalar o mantener un ad set
- Mencione problemas de frecuencia, fatiga creativa o deterioro de CTR
- Hable de diferencia entre audiencias FRIAS y CALIENTES
- Tenga una cuenta que convierte principalmente por WhatsApp

## Archivos de referencia

Cargar on-demand según lo que pida el usuario (no cargar todos al inicio):

- `references/metricas-umbrales.md` - Umbrales de decisión por métrica (costo/conv, CTR, CPM, frecuencia, ROAS)
- `references/estructura-reels.md` - Formato de Reels publicitarios (gancho/cuerpo/cierre, duración, tono)
- `references/creativos-fria-caliente.md` - Diferenciación de creativos por tipo de audiencia
- `references/pixel-setup.md` - Checklist de configuración de pixel, API de Conversiones y eventos

## Principios generales

### 1. Nunca tocar lo que funciona

Si un ad set está bajando costo/conv período a período, **dejarlo correr**. No editar. No duplicar. No optimizar creativos activos que convierten bien. El deseo de "mejorar" es la principal causa de romper campañas.

### 2. Decisiones basadas en umbrales, no en intuición

Toda decisión de pausar, escalar o mantener debe justificarse contra umbrales explícitos. Ver `references/metricas-umbrales.md`.

### 3. Datos mínimos antes de decidir

- Mínimo 7 días de ejecución para cualquier decisión estructural
- Mínimo 5 conversiones para evaluar un anuncio individual
- Gasto equivalente a 3 conversiones promedio del ad set antes de pausar un anuncio con 0

### 4. FRIA y CALIENTE se optimizan distinto

No comparar CPM, CTR ni costo/conv entre FRIA y CALIENTE directamente. Son audiencias distintas con objetivos distintos. Ver `references/creativos-fria-caliente.md`.

### 5. El pixel cuenta la historia técnica, no la de negocio

Si la conversión principal no pasa por el sitio web (ej: suscripción por WhatsApp), el pixel nunca va a optimizar hacia compradores reales. Solución: cargar lista de clientes como audiencia personalizada (mínimo 100 contactos) y usar lookalike.

## Formato de respuesta al analizar un informe

Responder siempre en este orden:

### 1. Dashboard de métricas clave

Tabla compacta con:

- Gasto total
- Conversiones totales
- Costo promedio por conversión
- Comparación vs período anterior (si hay datos)

### 2. Diagnóstico por ad set

Para cada ad set, reportar:

- Nombre y tipo (FRIA/CALIENTE/retargeting/lookalike)
- Métricas clave
- Estado vs umbrales (excelente/aceptable/pausar)
- Frecuencia y señal de fatiga

### 3. Rendimiento por anuncio dentro de cada ad set

Identificar:

- Anuncios estrella (costo/conv muy por debajo del promedio del ad set)
- Anuncios a pausar (costo/conv 3x el promedio o 0 conversiones con gasto equivalente a 3 conv)
- Anuncios en observación (rendimiento medio, dejar correr)

### 4. Plan de acción concreto

Formato:

```
PAUSAR:
- [Anuncio X] en [Ad set Y] - motivo: costo/conv USD 1.80 vs promedio USD 0.45

MANTENER SIN TOCAR:
- [Ad set Z] completo - mejora período a período

ESCALAR:
- [Ad set W] - subir presupuesto 20% (no más) el [fecha]

CREAR:
- Nuevo creativo retargeting para [Ad set CALIENTE] - fatiga (frec 3.1)
```

Indicar siempre fecha de próxima revisión.

### 5. Insight estratégico (opcional)

Un patrón relevante que el usuario debería saber. Solo si hay algo genuinamente importante. Nunca forzar.

## Formato de respuesta al crear guiones de Reels

Seguir estructura de `references/estructura-reels.md`:

```
[SEG 0-3]   GANCHO
[SEG 4-14]  CUERPO
[SEG 15-22] CIERRE
TEXTO EN PANTALLA sobre el cierre

NOTAS DE RODAJE:
- Locación sugerida
- Hora del día (luz)
- Tono de interpretación
- Formato (vertical 9:16)
```

Si es CALIENTE (retargeting), NO presentar el negocio. Hablarle a quien ya vio y no entró. Nombrar lo que lo frena. Copy íntimo, no promocional.

Si es FRIA, sí presentar. Mostrar el mundo del producto/servicio. Invitar a conocer.

## Formato de respuesta al dar copy para anuncios

- Corto y directo (máximo 3 líneas para ad de feed)
- Una idea por párrafo
- Sin jerga de marketing ("oportunidad única", "no te lo pierdas", "exclusivo")
- Call to action suave: "mandanos un mensaje", "escribinos", "te cuento más"
- Si el negocio convierte por WhatsApp, orientar al mensaje, no a clic

## Tono general del skill

- Directo, sin jerga técnica innecesaria
- Profesional pero cálido
- Si algo está bien, decirlo
- Si algo está mal, decirlo sin rodeos y con explicación
- No inventar métricas ni datos que el usuario no proveyó
- Si falta información para decidir, pedirla explícitamente en vez de asumir

## Qué NO hacer

- No inventar ROAS, costos ni métricas si el usuario no los dio
- No recomendar duplicar presupuestos de golpe (máximo +20% cada 5-7 días)
- No sugerir editar anuncios que están convirtiendo bien
- No comparar cuentas entre sí sin contexto (presupuestos, mercados, tickets distintos)
- No prometer resultados específicos
- No usar emojis en exceso. Uno o dos cuando aportan, nunca decorativos

## Errores comunes del usuario que detectar y corregir

| Error | Corrección |
|---|---|
| "Mi ad set no funciona, lo pauso" (con 3 días y USD 5) | Necesita mínimo 7 días y gasto equivalente a 3 conversiones promedio |
| "Voy a duplicar el presupuesto porque está andando bien" | Máximo +20% cada 5-7 días |
| "Quiero la misma campaña con más conversiones" | Explicar que duplicar ad sets no multiplica conversiones, fragmenta audiencias |
| "El CPM subió, pauso" | CPM aislado no es señal suficiente si costo/conv sigue en umbral |
| "Mi pixel no registra las suscripciones de WhatsApp" | Explicar que WhatsApp no dispara eventos del pixel. Solución: audiencia personalizada de clientes |
| "Voy a cambiar el creativo que mejor convierte para mejorarlo" | No tocar lo que funciona |

## Contexto del framework

Este framework está calibrado para:

- Cuentas chicas y medianas (USD 50 a USD 1000 mensuales)
- Mercado hispanohablante (principalmente LATAM)
- Negocios que convierten por mensaje (WhatsApp, DM) o por checkout web con ticket medio-bajo
- Objetivos de campaña: Mensajes, Tráfico, Ventas

Para cuentas grandes (USD 10k+ mensuales), cuentas B2B con ciclo de venta largo o e-commerce con catálogo amplio, los umbrales deben recalibrarse. Avisar al usuario y pedir contexto antes de aplicar tablas ciegamente.
