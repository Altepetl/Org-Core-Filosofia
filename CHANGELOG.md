# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- [Marco legal de la blockchain](./LegalBlockchain.md), v0.1.0 draft:
  antecedente histórico de la regulación mexicana de dinero electrónico, los
  dos caminos legales (fondo de pago electrónico vs. activo virtual), la
  argumentación de por qué el token del Altepetl es un fondo de pago
  electrónico por sustancia, y la lista de requisitos legales para operarlo
  (autorización CNBV como IFPE, capital mínimo, PLD, Circular 12/2018 y
  4/2019 de Banxico, LFPDPPP).

### Changed
- [Filosofía](./Filosofia.md), v1.1.0: la sección "El Inicio" incorpora la
  restricción legal (el token es un fondo de pago electrónico; el trámite de
  la CNBV tarda ~1 año). Nueva priorización: Centro de datos y Gateway de
  pagos con prioridad 1; blockchain en desarrollo paralelo sin prioridad 1.
  Nueva subsección "Mientras concluye el trámite legal" con los proyectos
  comerciales de contingencia (app de pagos, terminal física, Punto de Venta
  Core).
- [Especificación del Inicio](./Especificacion.md), v0.2.0: alineación con la
  restricción legal. Priorización del Inicio, sección 5.7 (proyectos
  comerciales de contingencia), puerta legal bloqueante para producción
  (sección 7), criterio de aceptación legal (sección 9), decisión #6
  (KYC/AML) reclasificada como bloqueante previa a Fase 0, nuevas decisiones
  #16 (ruta legal del token) y #17 (alcance de proyectos de contingencia).

### Estructura del repositorio (cambio previo)
- Estructura estándar de repositorio: LICENSE (MIT), .gitignore,
  CONTRIBUTING.md, README.md y plantillas de .github (issue templates:
  inconsistencia / corrección / propuesta; PR template; CODEOWNERS;
  markdownlint).
- CHANGELOG.md inicial.

## [1.0.0] — 2026-08-12

### Filosofía (`Filosofia.md`)

Documento fundacional estable. Define valores, misión, visión, marco
histórico, camino hacia el Kinam, modelo de Calpulli, principios rectores y
reglas innegociables del Altepetl.

#### Proceso de revisión

El documento fue revisado a fondo. Se resolvieron:

- **12 puntos de aclaración** que el documento original dejaba abiertos:
  1. Secuencia de financiamiento inicial.
  2. Relación con el capital privado (definida como: comercio sí, capital como
     inyección no).
  3. Distribución de ingresos entre niveles (asignación descentralizada +
     OKR).
  4. "Cambio radical" vs. "cambio progresivo" (dos tiempos distintos).
  5. Umbral de mayoría constitucional (2/3 mínimo, meta 100%) y definición de
     participante con derecho a voto (1 año + experiencia).
  6. Mecanismo de priorización (jerarquía de criterios: valores → peso →
     consenso → antigüedad).
  7. Rol del Tlahtocan frente al algoritmo (corazón, escala, diferencias
     pequeñas, disputas).
  8. Evaluación del historial para candidatos (filtro por reputación +
     votación).
  9. Blockchain + token + oráculo financiero (PoA, token operativo, oráculo
     con separación productor/validador).
  10. Proyecto Pensamiento Crítico (autónomo, listo, en desarrollo).
  11. Marco meshica y disputa historiográfica (posición deliberada asumida,
      nota sobre el nombre añadida).
  12. Alcance de la Salud y qué viene después del Kinam (Salud integral;
      Disfrutar → Saber → Crecer bajo la acción de Amar).

- **4 grupos de problemas** corregidos:
  - **Grupo A (contradicciones lógicas):** "no hay prohibiciones" → "registro
    en lugar de prohibición"; falacia del Kinam reformulada como argumento;
    "garantía de serendipia" → "crear las condiciones para que la serendipia
    ocurra".
  - **Grupo B (referencias intelectuales):** uso correcto de Thomas Kuhn como
    analogía; separación de trazabilidad (bitcoin) y planificación.
  - **Grupo C (afirmaciones categóricas):** empresa comunitaria vs. comercial
    suavizada a tendencia estructural.
  - **Grupo D (forma):** ~30 correcciones ortográficas y tipográficas;
    unificación de mayúsculas en `Calpulli`/`Calpullis`; unificación de
    `Tlahtocan`; correcciones de puntuación.

### Added
- [Filosofía](./Filosofia.md): documento fundacional, v1.0.0 stable.
- [Especificación del Inicio](./Especificacion.md), v0.1.0 draft: arquitectura
  de los tres proyectos vitales (centro de datos, gateway de pagos,
  blockchain + oráculo) con fases, dependencias y criterios de aceptación del
  MVP.
- [Marco de Gobernanza](./Gobernanza.md), v0.1.0 draft: tres niveles de
  gobierno, pirámide organizacional, roles de participación, procedimientos
  clave, peso de proyectos, límites de la automatización.
