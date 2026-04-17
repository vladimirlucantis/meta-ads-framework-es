# meta-ads-framework-es

> Skill de Claude para analizar y optimizar campañas de Meta Ads en español. Framework reutilizable basado en práctica real de consultoría.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-D97757)](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)
[![Idioma](https://img.shields.io/badge/Idioma-Espa%C3%B1ol-blue)](#)

## Qué es esto

Un skill de Claude que convierte informes de Meta Ads, métricas de campañas y preguntas sobre publicidad digital en análisis accionables, en español. Pensado para consultores, agencias y negocios que operan sus propias campañas en Facebook e Instagram.

No es un generador de copy genérico. Es un framework de diagnóstico que aplica umbrales de decisión, patrones de creativos FRÍA/CALIENTE y estructura de Reels publicitarios, destilados de campañas reales ejecutadas en el mercado argentino.

## Por qué existe

El 99% de los skills de marketing publicados en GitHub están en inglés y asumen un mercado, presupuestos y cultura muy distintos a los de LATAM. Este skill llena ese hueco con:

- Instrucciones en español (voseo argentino)
- Umbrales de costo por conversación/compra calibrados para cuentas chicas y medianas
- Estructura de Reels probada con presupuestos bajos
- Marco para negocios que convierten por WhatsApp, no por checkout

## Qué hace el skill

Activado automáticamente cuando le hablás a Claude de:

- Métricas de campañas de Meta Ads (ROAS, CPM, CTR, costo por conversación)
- Capturas del Administrador de Anuncios
- Configuración de pixel, API de Conversiones, audiencias
- Guiones de Reels publicitarios
- Copy para anuncios y hooks
- Cualquier estrategia de campaña: Advantage+, segmentación manual por intereses, FRIA+CALIENTE, creative testing, WhatsApp/Mensajes
- Decisiones de escalar, pausar o mantener ad sets

**Clave desde v0.2.0**: el skill es agnóstico de estrategia. Antes de diagnosticar identifica cuál de las 5 estrategias más comunes estás usando, y aplica umbrales y patrones específicos de esa estrategia. No impone una forma única de estructurar campañas.

Devuelve:

- Identificación de la estrategia detectada
- Diagnósticos por campaña y por ad set
- Planes de acción concretos (pausar X, escalar Y, esperar Z)
- Guiones de Reels estructurados según la estrategia
- Recomendaciones de audiencias y segmentación

## Instalación

Ver [docs/INSTALL.md](./docs/INSTALL.md) para instrucciones completas en Claude.ai, Claude Code y API.

Versión corta para Claude.ai (plan Pro o superior):

1. Descargá el contenido de `skill/` como ZIP
2. En Claude.ai: Settings → Capabilities → Skills → Upload Skill
3. Subí el ZIP y activalo

## Ejemplos de uso

### Input del usuario

> "Tengo una campaña de mensajes con 3 ad sets. FRIO gastó USD 45 con 120 conversaciones. CALIENTE gastó USD 20 con 15 conversaciones. Frecuencia CALIENTE 2.8. ¿Qué hago?"

### Output del skill

Ver [examples/analisis-campania.md](./examples/analisis-campania.md) para el diagnóstico completo.

### Otro input típico

> "Necesito un guión de Reel retargeting para mi servicio de consultoría contable."

Ver [examples/guion-reel.md](./examples/guion-reel.md).

## Qué hay adentro

```
skill/
├── SKILL.md                          # Instrucciones principales del skill
└── references/
    ├── estrategias-campania.md       # 5 estrategias de campaña y cómo diagnosticar cada una
    ├── metricas-umbrales.md          # Umbrales de decisión por métrica (con variantes por estrategia)
    ├── estructura-reels.md           # Formato de Reels publicitarios
    ├── creativos-por-estrategia.md   # Adaptación de creativos según estrategia
    └── pixel-setup.md                # Checklist de configuración de pixel
```

## Sobre el autor

Soy **Vladimir Lucantis**, consultor de marketing digital en Argentina. Trabajo con cuentas de Meta Ads, sitios WordPress/WooCommerce y estrategia de contenido para clientes hispanohablantes.

Soy nuevo publicando en GitHub y estoy aprendiendo el formato de Claude Skills al mismo tiempo que lo uso todos los días en trabajo real. Este repo es parte de ese proceso: compartir lo que funciona, iterar en público y sumar a una comunidad que recién arranca.

Si encontrás algo que se puede mejorar, abrí un issue o mandame un PR. Si te sirve, dame una star.

## Roadmap

El plan es evolucionar este repo con skills complementarios a medida que los pruebo en proyectos reales:

- [ ] `seo-audit-es` - Auditoría SEO técnica en español para sitios argentinos
- [ ] `woocommerce-optimize-es` - Optimización de performance para tiendas WooCommerce
- [ ] `n8n-patterns` - Patrones reutilizables de workflows n8n

Sin fechas. Cada skill se publica cuando está pulido, no antes.

## Contribuir

Ver [CONTRIBUTING.md](./CONTRIBUTING.md). Issues, PRs y feedback bienvenidos.

## Licencia

MIT. Ver [LICENSE](./LICENSE).

## Agradecimientos

- Anthropic por el formato de Agent Skills
- La comunidad de `travisvn/awesome-claude-skills` por documentar el ecosistema
- Mis clientes, que son los verdaderos autores de los aprendizajes destilados acá
