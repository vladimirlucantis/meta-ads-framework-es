# Instalación

Este skill puede usarse en tres contextos: Claude.ai (web/mobile/desktop), Claude Code y la API de Anthropic.

## Opción 1: Claude.ai (web, mobile o desktop)

**Requiere**: plan Pro, Max, Team o Enterprise.

### Pasos

1. Descargá este repositorio como ZIP (botón verde "Code" → "Download ZIP") o cloná con git
2. Comprimí la carpeta `skill/` en un ZIP llamado `meta-ads-framework-es.zip`
   - Importante: el ZIP debe contener la carpeta `skill/` en su raíz, no los archivos sueltos
3. En Claude.ai abrí **Settings** → **Capabilities** → **Skills**
4. Click en **Upload Skill**
5. Seleccioná el ZIP
6. Activá el skill

### Verificar que funciona

Mandale a Claude este mensaje de prueba:

> "Analizá esta campaña de Meta Ads: FRIA gastó USD 30 con 90 conversaciones a USD 0.33/conv, frecuencia 1.8. ¿Qué hago?"

Si el skill está activo, Claude debería responder usando el formato de dashboard + diagnóstico + plan de acción.

## Opción 2: Claude Code

### Instalación global (disponible en todos los proyectos)

```bash
cd ~/.claude/skills
git clone https://github.com/vladimirlucantis/meta-ads-framework-es.git
mv meta-ads-framework-es/skill meta-ads-framework-es-skill
rm -rf meta-ads-framework-es
mv meta-ads-framework-es-skill meta-ads-framework-es
```

### Instalación por proyecto

Dentro del proyecto donde lo querés usar:

```bash
mkdir -p .claude/skills
cd .claude/skills
git clone https://github.com/vladimirlucantis/meta-ads-framework-es.git
```

### Verificar

Abrí Claude Code en el proyecto y mandale un mensaje relacionado con Meta Ads. Debería activarse el skill automáticamente.

## Opción 3: API de Anthropic

Los skills también funcionan a través de la API pero requieren configuración vía el endpoint de Skills. Consultar la [documentación oficial de Skills API](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/using-skills-api) para detalles.

## Troubleshooting

### El skill no se activa

Posibles causas:

- El ZIP no tenía la estructura correcta (la carpeta `skill/` debe estar en la raíz del ZIP)
- La descripción del skill no matchea con lo que pediste. Probar con palabras clave explícitas como "Meta Ads", "costo por conversación", "FRIA CALIENTE", "pixel"
- El plan de Claude.ai no soporta skills (plan Free no los tiene)

### Claude activa el skill pero la respuesta no sigue el formato

Si Claude no usa el formato de dashboard + diagnóstico + plan:

1. Verificar que el SKILL.md se haya cargado correctamente (en Claude.ai, revisar el detalle del skill en Settings)
2. Ser más explícito: "Usá el framework meta-ads para analizar esto"
3. Reportar el caso como issue en este repo con el prompt que usaste

### Quiero modificar el skill para mi cuenta

Forkeá el repo, editá los archivos según tus umbrales y volvé a subir el ZIP con los cambios. Si los cambios son útiles para otros, mandá un PR.

## Requisitos técnicos

- Plan Claude.ai Pro/Max/Team/Enterprise (para usar via Claude.ai)
- Claude Code instalado (para uso via terminal)
- Ninguna dependencia externa, API key ni librería
