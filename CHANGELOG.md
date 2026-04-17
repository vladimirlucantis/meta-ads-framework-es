# Changelog

Todas las novedades relevantes de este proyecto se documentan acá.

Formato basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/).
Este proyecto usa [Versionado Semántico](https://semver.org/lang/es/).

## [0.2.1] - 2026-04-17

### Corregido

- Link roto en `references/estructura-reels.md` que apuntaba a `creativos-fria-caliente.md` (archivo eliminado en v0.2.0). Ahora apunta a `creativos-por-estrategia.md`
- Frontmatter de `SKILL.md`: descripción reducida de ~800 a ~400 caracteres para mejorar matching de activación. Removido lenguaje imperativo ("Usar SIEMPRE")
- Frontmatter de `SKILL.md`: eliminado bloque `metadata:` no estándar en spec de Agent Skills (author/version/language/category). Información preservada en el body como blockquote

### Añadido

- 2 casos nuevos en `examples/analisis-campania.md`:
  - Caso 5: Segmentación manual por intereses (4 ad sets por interés, diagnóstico individual, pausa del perdedor y escalado del ganador)
  - Caso 6: WhatsApp/Mensajes puro (objetivo Conversaciones, distingue capa Meta vs capa negocio, aborda "pixel 0 conversiones" como esperable)
- 2 casos nuevos en `examples/guion-reel.md`:
  - Caso 2: Guión FRIA (prospecting) para consultoría contable, mismo negocio del Caso 1 para comparación directa
  - Caso 3: Creative testing con 3 variantes de hook (dolor / solución / testimonio), cuerpo y cierre compartidos
- Blockquote en `SKILL.md` con autor, versión, idioma y categoría (reemplaza metadata de frontmatter)

### Notas

- Sin breaking changes. Cambios solo de forma (frontmatter) y cobertura de ejemplos
- Los 6 casos de análisis + 3 casos de guión ahora cubren las 5 estrategias del skill

## [0.2.0] - 2026-04-17

### Añadido

- Nueva referencia `estrategias-campania.md` con las 5 estrategias más comunes de Meta Ads (Advantage+, segmentación manual, FRIA+CALIENTE, creative testing, WhatsApp/Mensajes)
- Sección "Paso 0: Detectar estrategia" en SKILL.md que obliga a identificar la estrategia del usuario antes de diagnosticar
- Umbrales de decisión específicos por estrategia en `metricas-umbrales.md` (frecuencia distinta para Advantage+ vs manual vs retargeting)
- Umbrales para objetivo "Leads" (formularios)
- Nuevo ejemplo `analisis-campania.md` con 4 casos distintos: FRIA+CALIENTE, Advantage+ puro, estrategia ambigua (el skill pregunta), creative testing

### Cambiado

- Renombrado `creativos-fria-caliente.md` a `creativos-por-estrategia.md` con adaptación de creativos para las 5 estrategias
- SKILL.md refactorizado para ser agnóstico de estrategia. Ya no asume FRIA+CALIENTE como universal
- Descripción del frontmatter actualizada para reflejar soporte multi-estrategia
- Principios generales reformulados: "FRIA y CALIENTE se optimizan distinto" reemplazado por "Cada estrategia se evalúa con su propia vara"
- Ejemplo de análisis de campaña ampliado de 1 caso a 4 casos cubriendo distintas estrategias
- Formato de respuesta: la primera línea ahora identifica la estrategia detectada

### Deprecado

- Nada. Es un breaking change en estructura pero retrocompatible en comportamiento: el skill sigue funcionando bien con casos FRIA+CALIENTE, solo que ahora también funciona con otras estrategias

### Motivación

Feedback de un usuario real (y co-autor) del skill:

> "El tema de las audiencias FRIA/CALIENTE es personalmente algo que hago yo, hay quienes van a utilizar otra estrategia, por lo tanto necesito que la skill se pueda adapte a las diferentes estrategias de campañas en meta ads"

El skill v0.1.0 reflejaba la estrategia personal del autor. v0.2.0 lo convierte en una herramienta agnóstica de estrategia que sirve a cualquier media buyer.

## [0.1.0] - 2026-04-17

### Añadido

- Skill inicial `meta-ads-framework-es` con instrucciones en español
- Referencia `metricas-umbrales.md` con umbrales de decisión por métrica
- Referencia `estructura-reels.md` con formato de Reels publicitarios (gancho/cuerpo/cierre)
- Referencia `creativos-fria-caliente.md` con diferenciación por tipo de audiencia (reemplazada en v0.2.0)
- Referencia `pixel-setup.md` con checklist de configuración de pixel y API de Conversiones
- Ejemplo `analisis-campania.md` mostrando diagnóstico completo de campaña de mensajes
- Ejemplo `guion-reel.md` mostrando estructura de Reel retargeting
- Documentación de instalación para Claude.ai, Claude Code y API
- README, LICENSE (MIT), CONTRIBUTING, CHANGELOG

### Notas

- Primera versión pública. Umbrales y patrones calibrados para mercado argentino, presupuestos chicos y medianos, y negocios que convierten por WhatsApp.
- Feedback bienvenido vía issues para iterar en versiones siguientes.
