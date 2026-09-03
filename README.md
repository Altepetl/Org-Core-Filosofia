---
title: Filosofía del Altepetl
status: stable
version: 1.0.0
created: 2026-08-12
updated: 2026-08-12
---

# Filosofía del Altepetl

Este repositorio contiene los **documentos fundacionales** del Altepetl: la
definición de los principios, valores, objetivos y mecanismos de operación de
la organización. Es el punto de partida y la referencia última para todo lo
demás que se construya bajo el nombre Altepetl.

> **Altepetl** es una organización cuyo objetivo es crear una base económica y
> social para la salud humana. Salud entendida en sentido integral: física,
> mental, emocional, espiritual y ambiental.

## Documentos

Cada uno de estos documentos con un rol distinto:

| Documento | Rol | Pregunta que responde |
|---|---|---|
| [**Filosofía**](./Filosofia.md) | Fundacional | ¿Por qué existimos y qué buscamos? |
| [**Especificación del Inicio**](./Especificacion.md) | Técnico | ¿Qué construimos primero y cómo? |
| [**Marco de Gobernanza**](./Gobernanza.md) | Operativo | ¿Cómo decidimos y operamos? |
| [**Marco Legal Organizacional**](./MarcoLegalOrganizacional.md) | Legal | ¿Qué figuras jurídicas constituimos y cómo fluyen los fondos entre ellas? |
| [**Capital Inicial Necesario**](./CapitalInicialNecesario.md) | Financiero | ¿Cuánto cuesta arrancar y con qué se paga cada cosa? |
| [**Marco Legal de la Blockchain**](./LegalBlockchain.md) | Legal | ¿Qué exige la ley para operar la blockchain y el token? |

### Filosofía

Define los valores, la misión, la visión, el marco histórico, el camino hacia
el Kinam, el modelo de Calpulli, los principios rectores y las reglas
innegociables de la organización. Es la fuente de autoridad para todos los
demás documentos y proyectos del Altepetl.

### Especificación del Inicio

Define arquitecturalmente los tres proyectos técnicos vitales que deben
construirse a la par como base mínima del Altepetl:

- Centro de datos (aloja todo).
- Gateway de pagos (capta recursos del exterior).
- Blockchain + Oráculo financiero (registra y distribuye el valor).

Estos tres proyectos se materializan en repositorios separados:
[`Org-Core-DataCenter`](../Org-Core-DataCenter/README.md),
[`Org-Core-Payments`](../Org-Core-Payments/README.md),
[`Org-Core-Blockchain`](../Org-Core-Blockchain/README.md).

### Marco de Gobernanza

Opera los principios definidos en la Filosofía: los tres niveles de gobierno
(constitucional, gobernanza, elecciones), la pirámide organizacional
(Calpulli → Comunidad → Colectivo → Tlahtocan), los roles de participación,
los procedimientos clave (priorización, Tlahtocan, enmienda, elecciones,
disputas) y los límites de la automatización.

### Marco Legal de la Blockchain

Establece el encuadre legal del token bajo la legislación mexicana: el
antecedente histórico de la Ley Fintech, los dos caminos legales (fondo de
pago electrónico vs. activo virtual), por qué el token del Altepetl es un
fondo de pago electrónico por sustancia, y la lista de requisitos para
operarlo (autorización de la CNBV como IFPE, capital mínimo, PLD, reglas de
Banxico). Acota la Especificación: la blockchain opera con fondos reales solo
tras la autorización.

### Marco Legal Organizacional

Define la arquitectura legal multi-entidad del Altepetl: la A.C. donataria que
capta donativos deducibles y genera conocimiento civil, y la empresa comercial
que productiza y vende. Establece la regla de división de activos (software en
la A.C., hardware en la empresa), los límites fiscales que el diseño respeta
(5% de administración, 50% de actividades no relacionadas), el objeto social
sugerido (Desarrollo Social) y el ciclo completo en cinco fases. Complementa al
Marco Legal de la Blockchain: ese define el encuadre del token, este define el
encuadre de las figuras que lo alojan.

### Capital Inicial Necesario

Detalla qué requiere dinero para que el Altepetl arranque de manera formal:
constitución de las dos entidades, contratos y asesorías entre ambas, operación
inicial (sueldos y costos recurrentes) e infraestructura técnica. Establece la
regla de las dos bolsas (la A.C. se financia con donativos, la empresa con
capital social) y consolida el presupuesto por escenario (mínimo viable, medio,
ambicioso). Estimación referencial basada en costos de mercado 2025–2026.

## Relación entre los documentos

```
                  Filosofía (por qué / qué)
                       │
            ┌──────────┼──────────┐
            ▼          ▼          ▼
Especificación     Gobernanza   Marco Legal
(cómo técnico)   (cómo operativo)  Organizacional
            │          │       (figuras jurídicas
            ▼          ▼        y flujo de fondos)
    3 repos del   Plataforma          │
    Inicio        digital             │
    (DataCenter,  (registra           ▼
     Payments,    historiales,  Marco Legal de la
     Blockchain)   decisiones,  Blockchain
                  pesos)       (qué exige la ley
            ▲                  para el token)
            │  acota (qué permite la ley)
            └────────────────┘
```

Los cinco documentos se referencian entre sí y deben mantenerse
**coherentemente alineados**. Un cambio en cualquiera debe revisarse contra
los otros cuatro para evitar contradicciones. El proceso de contribución (ver
[CONTRIBUTING.md](./CONTRIBUTING.md)) está diseñado para garantizar esa
coherencia.

## Cómo leer estos documentos

Si eres nuevo en el Altepetl:

1. **Empieza por la Filosofía.** Es el documento fundacional; sin entenderlo,
   los otros dos no tienen contexto.
2. **Luego la Especificación del Inicio** si tu interés es técnico (qué se
   construye, en qué orden, con qué dependencias).
3. **Después el Marco de Gobernanza** si tu interés es organizativo (cómo se
   decide, quién participa, qué rol tienes tú).

Si buscas una versión comunicativa más corta antes de entrar al documento
completo, el [sitio público del Altepetl](https://altepetl.kinam.org) resume
los puntos clave.

## Estado de los documentos

| Documento | Versión | Estado |
|---|---|---|
| Filosofía | 1.7.0 | stable — revisada, pulida, internamente coherente |
| Especificación del Inicio | 0.3.0 | draft — arquitectura definida, decisiones pendientes abiertas |
| Marco de Gobernanza | 0.1.0 | draft — marco definido, decisiones pendientes abiertas |
| Marco Legal Organizacional | 0.1.0 | draft — arquitectura definida, requiere validación de asesoría legal |
| Capital Inicial Necesario | 0.1.0 | draft — estimación definida, requiere cotización formal con proveedores |
| Marco Legal de la Blockchain | 0.1.0 | draft — análisis definido, requiere validación de asesoría legal |

El documento de Filosofía está estable: pasó por una revisión completa que
resolvió inconsistencias lógicas, errores factuales y de forma. La
Especificación, la Gobernanza y los dos Marcos Legales están en draft: definen
el marco pero dejan decisiones operativas abiertas, marcadas explícitamente en
cada documento.

## Cómo contribuir

Ver [CONTRIBUTING.md](./CONTRIBUTING.md). Los documentos fundacionales son
sensibles: cualquier cambio afecta a toda la organización, por lo que el
proceso de contribución es deliberado.

En particular, ten en cuenta:

- Los cambios que **rompen** principios fundacionales no se aceptan por PR
  directo; requieren el proceso de enmienda constitucional descrito en la
  [Gobernanza](./Gobernanza.md), sección 5.3.
- Las contribuciones se benefician de seguir el propio
  [Pensamiento Crítico](https://github.com/Altepetl/Org-Core-CriticalThinking)
  del Altepetl: definir el problema, aportar evidencia, considerar alternativas.
- Las convenciones de estilo (español neutro, mayúsculas consistentes para
  términos técnicos: `Calpulli`, `Kinam`, `Tlahtocan`; `meshica` no `azteca`)
  están documentadas en el CONTRIBUTING.

## Posición sobre el nombre y el marco cultural

La Filosofía toma como cultura de referencia a la **meshica** (no "azteca") —
ver la nota "Sobre el nombre" en la sección Marco Histórico. Este repositorio
asume esa posición como deliberada y no entra en debate sobre el nombre en sus
issues; la decisión está documentada en su lugar.

## Estructura del repositorio

```
Filosofia/
├── .github/
│   ├── ISSUE_TEMPLATE/        # Plantillas: inconsistencia, corrección, propuesta
│   ├── pull_request_template.md
│   ├── CODEOWNERS             # Responsables por documento
│   └── markdownlint.json
├── Filosofia.md               # Documento fundacional
├── Especificacion.md          # Especificación técnica del Inicio
├── Gobernanza.md              # Marco de gobernanza
├── LegalBlockchain.md         # Marco legal de la blockchain (IFPE / Ley Fintech)
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Referencias

- [Org-Core-DataCenter](../Org-Core-DataCenter/README.md) — repositorio
  derivado de la Especificación, sección 4.
- [Org-Core-Payments](../Org-Core-Payments/README.md) — repositorio derivado
  de la Especificación, sección 5.
- [Org-Core-Blockchain](../Org-Core-Blockchain/README.md) — repositorio
  derivado de la Especificación, sección 6.
- [Pensamiento Crítico](https://github.com/Altepetl/Org-Core-CriticalThinking)
  — marco de análisis que el Altepetl usa para tomar decisiones.
- [Org-Web](../../Org-Web/README.md) — sitio público que comunica estos
  documentos al mundo exterior.

## Licencia

[MIT](./LICENSE).
