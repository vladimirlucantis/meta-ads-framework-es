# Ejemplo: Análisis de campaña de mensajes

Este ejemplo muestra cómo responde el skill cuando un usuario comparte un informe de campaña y pide diagnóstico.

## Prompt del usuario

> Hola, te comparto los datos de mi campaña de mensajes que lleva 14 días corriendo. Es para un negocio de clases de yoga online. Presupuesto total USD 60.
>
> **AD SET FRIA - Advantage+** (USD 40 gastados)
>
> - 105 conversaciones
> - Costo/conv USD 0.38
> - CTR 3.2%
> - CPM USD 1.40
> - Frecuencia 1.7
>
> Anuncios dentro:
>
> - "Testimonio Ana" - 50 conv, costo/conv USD 0.30
> - "Mundo del yoga" - 40 conv, costo/conv USD 0.42
> - "Beneficios" - 15 conv, costo/conv USD 0.85
>
> **AD SET CALIENTE - IG engagers 365d + web visitors 90d** (USD 20 gastados)
>
> - 12 conversaciones
> - Costo/conv USD 1.66
> - CTR 1.8%
> - CPM USD 3.20
> - Frecuencia 3.4
>
> Anuncios dentro:
>
> - "Venite a probar" - 8 conv, costo/conv USD 1.50
> - "Última clase del mes" - 4 conv, costo/conv USD 2.00
>
> ¿Qué hago?

## Respuesta del skill

### Dashboard de métricas

| Métrica | FRIA | CALIENTE | Total |
|---|---|---|---|
| Gasto | USD 40 | USD 20 | USD 60 |
| Conversaciones | 105 | 12 | 117 |
| Costo/conv | USD 0.38 | USD 1.66 | USD 0.51 |
| Frecuencia | 1.7 | 3.4 | - |

### Diagnóstico por ad set

**FRIA - Advantage+** → **MANTENER SIN TOCAR**

- Costo/conv USD 0.38 está en zona aceptable (umbral < 0.65)
- Frecuencia 1.7 todavía sana (umbral < 2.0)
- CTR 3.2% excelente
- El ad set está aprendiendo bien, no hay razón para intervenir

**CALIENTE - Engagers + web visitors** → **PROBLEMAS GRAVES**

- Costo/conv USD 1.66 está en zona de pausa (umbral > USD 1.00)
- Frecuencia 3.4 supera el umbral CALIENTE (> 3.0)
- CTR 1.8% cayó por debajo del piso aceptable para CALIENTE
- La audiencia está saturada

### Rendimiento por anuncio

**Dentro de FRIA:**

- "Testimonio Ana" - ESTRELLA: USD 0.30 vs promedio USD 0.38. Dejarlo correr sin tocar
- "Mundo del yoga" - OK: USD 0.42, cerca del promedio
- "Beneficios" - PAUSAR: USD 0.85 es más de 2x el promedio del ad set

**Dentro de CALIENTE:**

- Ambos anuncios están muy por encima del umbral
- El problema no es de creativo puntual, es del ad set completo
- Fatigado (frec 3.4) y con creativos que probablemente son los mismos que usaste en FRIA

### Plan de acción

```
INMEDIATO (hoy):

PAUSAR:
- Anuncio "Beneficios" en FRIA (costo/conv 2x el promedio del ad set)
- AD SET CALIENTE COMPLETO (frecuencia saturada + costo/conv fuera de umbral)

MANTENER SIN TOCAR:
- Ad set FRIA entero
- Anuncios "Testimonio Ana" y "Mundo del yoga" dentro de FRIA

CREAR (esta semana):

- Un Reel nuevo ESPECIFICO para retargeting CALIENTE
  (no reutilizar los creativos de FRIA)

  Ver estructura de CALIENTE en
  references/creativos-fria-caliente.md

PROXIMA REVISION: en 7 días
```

### Insight estratégico

Tu problema principal es que el ad set CALIENTE probablemente tiene los mismos creativos que FRIA. Eso garantiza fatiga rápida: los usuarios que ya vieron el ad una vez en FRIA lo vuelven a ver en CALIENTE con el mismo mensaje.

Cuando filmes el Reel nuevo de retargeting, acordate: a la CALIENTE **no le presentás**, le **hablás directo**. Ya te conoce. Lo que la frena no es falta de información, es otra cosa (tiempo, duda, plata, "más adelante"). Ese otra cosa es lo que tiene que nombrar el creativo.

Si querés, te puedo pasar un guión base adaptado a clases de yoga. Decime y lo armamos.
