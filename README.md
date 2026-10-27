# legal-pages-check

> Encontrar los vacíos de tus páginas legales antes de llevarlas al abogado.

**Revisión de páginas legales** · Skill para agentes de código de la comunidad [nvvdev](https://github.com/nvv-dev). Funciona en Claude Code como plugin o como skill suelta, y en cualquier agente compatible con el formato abierto [`SKILL.md`](https://agentskills.io).

*English summary at the end.*

## Qué hace

Arma el inventario de datos que la app o el sitio recoge de verdad y lo compara con la política de privacidad, los términos, el aviso de cookies y lo declarado en las tiendas. Aplica una lista por país (Colombia, Ley 1581 de 2012, como ejemplo) con la fuente de cada requisito y marca lo que debe ver un abogado. Lo dice explícitamente: no es asesoría legal.

## Objetivo

Llegar al abogado con una lista corta de vacíos reales y preguntas precisas, en lugar de un "¿me revisas esto?".

## Cuándo usarla

- Antes de lanzar o de enviar una app a revisión
- Después de agregar formularios, analítica, pagos o un SDK que recoge datos

## Cuándo no

- Como reemplazo de un abogado: no aprueba ni certifica nada
- Contratos complejos o sectores regulados sin revisión profesional

## Ejemplo

```text
/legal-pages-check sobre la política de privacidad de kodaloom.com para Colombia.
```

## Cómo se activa

Esta skill **solo se activa a mano** (`disable-model-invocation: true`): no ocupa contexto en cada sesión y la invocas cuando la necesitas:

- Instalada como plugin: `/legal-pages-check:legal-pages-check`
- Copiada a `.claude/skills/`: `/legal-pages-check`

## Instalación

### Opción 1: Claude Code, como plugin (recomendada)

Dentro de Claude Code:

```text
/plugin marketplace add nvv-dev/claude-plugins
/plugin install legal-pages-check@nvvdev
```

La primera línea agrega el catálogo de nvvdev una sola vez; la segunda instala esta skill. Si prefieres el paquete completo, instala `growth-workflow@nvvdev` en su lugar (incluye esta skill y las demás de [growth-workflow](https://github.com/nvv-dev/growth-workflow)); no instales los dos a la vez.

### Opción 2: Claude Code, copiando la skill

Para un solo proyecto (se comparte con tu equipo por git):

```bash
git clone --depth 1 https://github.com/nvv-dev/legal-pages-check.git /tmp/legal-pages-check
mkdir -p .claude/skills
cp -R /tmp/legal-pages-check/skills/legal-pages-check .claude/skills/
```

Para todos tus proyectos, cópiala en `~/.claude/skills/` en lugar de `.claude/skills/`.

### Opción 3: otros agentes

Copia la carpeta `skills/legal-pages-check/` en la carpeta de skills de tu agente (cada agente documenta la suya). Con la CLI [skills](https://github.com/vercel-labs/skills) de Vercel Labs:

```bash
DISABLE_TELEMETRY=1 npx skills add nvv-dev/legal-pages-check
```

### Verificar

Abre una sesión nueva y pregunta "¿qué skills tienes disponibles?"; `legal-pages-check` debe aparecer. Con el plugin, `/plugin` la muestra como instalada.

### Actualizar o desinstalar

- Plugin: `/plugin marketplace update nvvdev` para actualizar; `/plugin uninstall legal-pages-check@nvvdev` para quitarla.
- Copia manual: repite la copia para actualizar, o borra la carpeta `.claude/skills/legal-pages-check`.

Antes de instalar cualquier skill, incluida esta, conviene leerla: es un solo archivo, [`skills/legal-pages-check/SKILL.md`](skills/legal-pages-check/SKILL.md). Ver [vetting-external-skills](https://github.com/nvv-dev/vetting-external-skills).

## Contenido

| Ruta | Qué es |
|---|---|
| `skills/legal-pages-check/SKILL.md` | La skill: instrucciones en inglés para que los escáneres de seguridad las analicen completas; el agente responde en tu idioma |
| `.claude-plugin/plugin.json` | Manifiesto para instalarla como plugin |
| `.github/workflows/` | Validación de estructura y escaneo con SkillSpector en cada cambio |

## Contribuir

Este repo se **genera** desde [nvv-dev/growth-workflow](https://github.com/nvv-dev/growth-workflow), donde vive la versión canónica. Abre issues y PRs allí. La mejor contribución es un caso real en la sección *Known failures* de la skill, con la regla que lo evita.

## Origen

Escrita desde cero por nvvdev. Inspirada en: [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) (legal: compliance-check); Colombia's Law 1581 of 2012 as the worked example.

## Licencia

MIT.

---

## English

**legal-pages-check** — Checks privacy policy, terms and cookie notice against a per-country checklist (Colombia's Law 1581 as example) and what the app declares; flags what a lawyer must see. Not legal advice.

Install in Claude Code with `/plugin marketplace add nvv-dev/claude-plugins` and `/plugin install legal-pages-check@nvvdev`, or copy `skills/legal-pages-check/` into `.claude/skills/` (project) or `~/.claude/skills/` (personal). Other agents: copy the folder into their skills directory, or run `DISABLE_TELEMETRY=1 npx skills add nvv-dev/legal-pages-check`. Manual-only skill: invoke it with `/legal-pages-check:legal-pages-check` (plugin) or `/legal-pages-check` (copied). Canonical source: [nvv-dev/growth-workflow](https://github.com/nvv-dev/growth-workflow). License: MIT.
