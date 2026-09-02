# AGENTS.md — Guía para agentes de código IA

## Visión general del proyecto

Este repositorio (`Org-Core-Filosofia`) contiene los **documentos fundacionales
del Altepetl**, una organización cuyo objetivo es crear una base económica y
social para la salud humana integral (física, mental, emocional, espiritual y
ambiental).

**No es un proyecto de software.** No hay código fuente, dependencias, build ni
tests automatizados. Es un repositorio de **documentación normativa en
Markdown, en español**, que define principios, valores, gobernanza y marcos
legales. Es la fuente de autoridad para todos los demás proyectos de la
organización.

Los documentos se referencian entre sí y deben mantenerse **coherentemente
alineados**: un cambio en cualquiera debe revisarse contra los demás para
evitar contradicciones (ver diagrama de relaciones en `README.md`).

## Estructura del repositorio

```
Filosofia/
├── Filosofia.md                   # Documento fundacional (stable)
├── Especificacion.md              # Especificación técnica del Inicio (draft)
├── Gobernanza.md                  # Marco de gobernanza (draft)
├── MarcoLegalOrganizacional.md    # Arquitectura legal multi-entidad: A.C. + empresa (draft)
├── CapitalInicialNecesario.md     # Presupuesto de arranque por escenarios (draft)
├── LegalBlockchain.md             # Encuadre legal del token (Ley Fintech / IFPE) (draft)
├── README.md                      # Portada: qué es, tabla de documentos, estados
├── CHANGELOG.md                   # Keep a Changelog + SemVer
├── CONTRIBUTING.md                # Proceso de contribución y estilo
├── LICENSE                        # MIT
├── .gitignore
└── .github/
    ├── CODEOWNERS                 # Owners por documento (placeholders @altepetl/*)
    ├── pull_request_template.md   # Checklist de coherencia entre documentos
    ├── markdownlint.json          # Config de markdownlint
    └── ISSUE_TEMPLATE/            # inconsistency.md, correction.md, proposal.md, config.yml
```

Nota: el diagrama de estructura dentro de `README.md` omite
`MarcoLegalOrganizacional.md` y `CapitalInicialNecesario.md` (agregados
después). Los archivos listados arriba reflejan el estado real.

### Rol de cada documento

| Documento | Rol | Pregunta que responde |
|---|---|---|
| `Filosofia.md` | Fundacional | ¿Por qué existimos y qué buscamos? |
| `Especificacion.md` | Técnico | ¿Qué construimos primero y cómo? |
| `Gobernanza.md` | Operativo | ¿Cómo decidimos y operamos? |
| `MarcoLegalOrganizacional.md` | Legal | ¿Qué figuras jurídicas y cómo fluyen los fondos? |
| `CapitalInicialNecesario.md` | Financiero | ¿Cuánto cuesta arrancar? |
| `LegalBlockchain.md` | Legal | ¿Qué exige la ley mexicana para el token? |

Los documentos técnicos se materializan en repositorios hermanos:
`../Org-Core-DataCenter`, `../Org-Core-Payments`, `../Org-Core-Blockchain`
(referenciados con rutas relativas desde los documentos).

## Convenciones de los documentos

### Frontmatter YAML

Cada documento principal abre con frontmatter:

```yaml
---
title: <título del documento>
status: stable | draft
version: <semver, independiente por documento>
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

- **El frontmatter es la fuente de verdad** para versión y estado de cada
  documento. La tabla de "Estado de los documentos" en `README.md` puede ir
  con retraso (p. ej. `Filosofia.md` está en 1.4.0 mientras el README dice
  1.3.0): al editar un documento, actualiza su frontmatter **y** el README.
- `updated` debe reflejar la fecha del último cambio al documento.

### Estilo de redacción

- **Español neutro**, consistente con el resto de los documentos.
- Términos propios del Altepetl con mayúscula inicial cuando son sustantivos:
  `Calpulli`, `Kinam`, `Tlahtocan`, `Colectivo`, `Comunidad`. `Altepetl`
  siempre con mayúscula (nombre propio).
- Se usa `meshica` (no `azteca`) para referirse al pueblo; es una decisión
  deliberada documentada en la Filosofía ("Sobre el nombre"). No abrir debate
  sobre esto.
- Formato Markdown existente: encabezados, tablas, bloques de cita y
  diagramas ASCII dentro de bloques de código. Los diagramas ASCII deben ser
  legibles en terminal: **máximo 72–80 caracteres de ancho**.
- Calidad argumentativa: sin falacias, sin afirmaciones categóricas sin
  sustento, sin extrapolaciones indebidas de referencias intelectuales.

### Lint

- Configuración en `.github/markdownlint.json`: reglas por defecto activas,
  con `MD013` (longitud de línea), `MD033` (HTML), `MD041` (primer encabezado)
  y `MD034` (URLs peladas) desactivadas, y `MD024` solo entre hermanos.
- Se puede validar con cualquier runner de `markdownlint` apuntando a esa
  config; no hay scripts ni CI configurados en el repo.

## Flujo de trabajo (contribución)

No hay build ni tests: la "verificación" es editorial y de coherencia.

1. **Abrir issue antes de cambios grandes** (plantillas en
   `.github/ISSUE_TEMPLATE/`: inconsistencia, corrección, propuesta).
2. Rama descriptiva: `git checkout -b corrige/inconsistencia-termino-calpulli`.
3. **Commits atómicos**, un cambio por commit, siguiendo *Conventional
   Commits* en español: `corrige:`, `añade:`, `cambia:`, `docs:`.
4. Si el cambio afecta a más de un documento (se referencian entre sí),
   **actualizar todos** para mantener la coherencia.
5. Actualizar `CHANGELOG.md` bajo `[Unreleased]` (formato Keep a Changelog,
   versionado SemVer por documento).
6. PR contra la rama principal usando la plantilla (`.github/pull_request_template.md`),
   que exige un checklist de coherencia Filosofía ↔ Especificación ↔ Gobernanza.

Revisión: se evalúa consistencia interna, coherencia con los valores, calidad
argumentativa y trazabilidad (CHANGELOG + issue referenciado). Los CODEOWNERS
(`.github/CODEOWNERS`) asignan revisores por documento; los handles
`@altepetl/*` son **placeholders** pendientes de reemplazar por equipos reales.

## Restricciones y consideraciones sensibles

- **Documentos normativos sensibles**: cualquier cambio afecta a toda la
  organización. Cambios que **rompan principios fundacionales** no se aceptan
  por PR directo; requieren el proceso de enmienda constitucional
  (`Gobernanza.md`, sección 5.3).
- **No contradecir** los valores fundacionales (La vida, El ser humano, El
  amor, La Bondad) ni la regla "comercio sí, capital como inyección no".
- Los documentos legales (`MarcoLegalOrganizacional.md`, `LegalBlockchain.md`,
  `CapitalInicialNecesario.md`) están en draft y **requieren validación de
  asesoría legal / cotizaciones formales**; no tratarlos como asesoría
  definitiva.
- No renombrar `meshica` por `azteca` ni abrir debate sobre el nombre.
- `.gitignore` excluye borradores y trabajo en curso: `drafts/`, `wip/`,
  `work-in-progress/`, `*-draft.md`, `*-private.md` y `.zcode/` (archivos
  internos de herramienta). No commitear archivos que caigan en esos patrones.

## Repositorios relacionados

- `../Org-Core-DataCenter`, `../Org-Core-Payments`, `../Org-Core-Blockchain` —
  los tres proyectos técnicos del Inicio (definidos en `Especificacion.md`).
- [Org-Core-CriticalThinking](https://github.com/Altepetl/Org-Core-CriticalThinking) —
  marco de Pensamiento Crítico usado para sustentar propuestas.
- `../../Org-Web` — sitio público que comunica estos documentos.
