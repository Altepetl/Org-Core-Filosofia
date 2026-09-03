# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- [Capital inicial necesario](./CapitalInicialNecesario.md), v0.1.0 draft:
  presupuesto de arranque formal del Altepetl. Detalla los costos de
  constitución de la A.C. donataria y de la empresa comercial, los contratos y
  asesorías entre ambas, la operación inicial (sueldos y costos recurrentes) y
  la infraestructura técnica (centro de datos). Establece la regla de las dos
  bolsas (A.C. financiada con donativos, empresa con capital social), la
  distinción administrativo vs. misional aplicada desde el día 1 y el
  presupuesto consolidado por escenario. Estimación referencial basada en
  costos de mercado 2025–2026.
- [Marco legal organizacional](./MarcoLegalOrganizacional.md), v0.1.0 draft:
  arquitectura legal multi-entidad del Altepetl. Define la A.C. donataria
  (capta donativos, genera conocimiento civil) y la empresa comercial de TI
  (productiza y vende), unidas por un contrato de licencia de tecnología.
  Establece la regla de división de activos (software en la A.C., hardware en
  la empresa), los límites fiscales que el diseño respeta (5% de
  administración, 50% de actividades no relacionadas, destino exclusivo de
  activos), el objeto social sugerido (Desarrollo Social), las opciones de
  propiedad entre las dos entidades (Opción C, participación minoritaria,
  recomendada) y el ciclo completo de captación, construcción y venta en cinco
  fases. Complementa al Marco Legal de la Blockchain.
- [Marco legal de la blockchain](./LegalBlockchain.md), v0.1.0 draft:
  antecedente histórico de la regulación mexicana de dinero electrónico, los
  dos caminos legales (fondo de pago electrónico vs. activo virtual), la
  argumentación de por qué el token del Altepetl es un fondo de pago
  electrónico por sustancia, y la lista de requisitos legales para operarlo
  (autorización CNBV como IFPE, capital mínimo, PLD, Circular 12/2018 y
  4/2019 de Banxico, LFPDPPP).

### Changed
- [Filosofía](./Filosofia.md), v1.7.0: la red social propia entra a la
  secuencia del Inicio como el paso siguiente al Gateway de pagos y anterior
  a la blockchain ("Mientras concluye el trámite legal"): no requiere
  autorización legal, corre sobre el Centro de datos y construye la comunidad
  que adoptará el token. En "Cambio de paradigma" (Financiamiento) se
  declara su función estratégica —medios de comunicación realmente libres y
  canal para popularizar el Ficonsumo— con implementación inicial simple al
  estilo de X (texto, fotos, videos), y la advertencia honesta: poblar una
  red social es el mercado más difícil que existe; la red nace como el medio
  de la Causa y crece desde ese núcleo, de modo que la consolidación del
  mercado es consecuencia, no prerrequisito.
- [Especificación del Inicio](./Especificacion.md), v0.3.0: la red social
  propia se incorpora a la priorización (sección "Priorización por
  restricción legal") y como proyecto 4 de la sección 5.7, con su función
  estratégica declarada. La decisión #17 amplía su alcance a la red social.
- [Filosofía](./Filosofia.md), v1.6.0: nueva sección "Ficonsumo" dentro de
  "Financiamiento". Define el objeto social de la primera etapa (diseño,
  desarrollo, producción, distribución y comercialización de software y
  servicios tecnológicos), el modelo de financiamiento por consumo directo
  (suscripciones, pago por uso, licencias, publicidad integrada y alianzas
  estratégicas) y el neologismo Ficonsumo —fusión de "financiamiento" y
  "consumo"— como modelo de negocio central: el consumo de los productos y
  servicios de la organización financia la Causa. Nueva sección "Etapas
  posteriores": una vez alcanzada la madurez tecnológica y financiera, los
  servicios se ponen al disposición de la población para emprendimientos
  productivos, comenzando por la cadena de producción, distribución y
  comercialización de alimentos, que la organización busca consolidar. Se
  detalla la escalera de productos para operar la cadena completa (motor de
  pagos → punto de venta → control de almacén → logística): el punto de
  venta se ofrece gratuito desde su primera versión a todas las tiendas —
  subsidiado por el margen del procesamiento de pagos y, después, por los
  servicios de almacén y logística— hasta que la plataforma sea la misma que
  opere el almacén propio de la organización. Se hace explícita la secuencia
  temporal: la etapa gratuita del punto de venta inicia una vez obtenida la
  autorización de IFPE; mientras concluye el trámite, estos productos se
  comercializan como tecnología, etapa que financia y madura la plataforma
  antes de sembrar la red.
- [Filosofía](./Filosofia.md), v1.5.0: nueva sección independiente
  "Consolidación" que fija el término con precisión: definición del ciclo en
  cuatro fases (construcción, implantación, comercialización y apropiación de
  mercado), sus dos fronteras (venta de servicios, no captación de capital;
  la ventaja del trabajo voluntario cubre el desarrollo, no la operación) y
  dos ejemplos detallados: la nube propia del Altepetl y la red de
  producción, distribución y comercialización de alimentos, recorriendo el
  ciclo completo (en este segundo ejemplo, la implantación y la
  comercialización se funden: el punto de venta gratuito siembra la red
  tienda por tienda y la demanda agregada negocia directamente con los
  productores). Se declara que el mismo ciclo se aplicará al resto de los
  sectores y actividades productivas. Referencias cruzadas actualizadas en
  "Tecnología", "Captación de recursos" y "Etapas posteriores".
- [Filosofía](./Filosofia.md), v1.4.0: resolución de la controversia sobre
  proyectos contrarios a los valores. En "Registro, no prohibición" los
  proyectos contradictorios ya no caen al final de la lista: reciben peso
  negativo y no se atienden mientras su impacto negativo no se reduzca a un
  margen justo; el registro deja de describirse como marca permanente e
  inmutable y declara su propósito: identificar grupos y personas con malas
  intenciones. Nuevas subsecciones "Quién determina qué es contrario a los
  valores" (no hay juez central: lo determina la razón de las comunidades a
  través de sus organismos de gobierno, desde el Calpulli) y "Proyectos
  controversiales" (el proponente defiende su proyecto con investigación,
  datos y análisis robusto y debe conquistar los corazones de su oposición;
  la misión de los consejos es complementar el proyecto, no solo refutarlo;
  ejemplo del aborto). La priorización de proyectos se alinea con esta regla
  y se añade el paradigma de hacer que una Causa sea el promotor principal de
  venta de los productos y servicios de la organización.
- [Filosofía](./Filosofia.md), v1.3.0: precisión sobre la ventaja competitiva
  del trabajo comunitario —reduce el costo de desarrollo, no el de operación
  (disponibilidad 24/7, cumplimiento, seguridad, soporte y energía se pagan
  en efectivo)—. Nueva subsección "Los límites del trabajo voluntario": la
  estrategia no se apoya en ganar una guerra de precios sino en la ventaja
  estructural: el producto principal de la organización es una Causa. Se
  suaviza el pasaje "fácilmente alcanzable" de la sección Tecnología.
- [Filosofía](./Filosofia.md), v1.2.0: precisión del modelo económico por
  etapas —un Calpulli se integra cuando la plataforma ya está completa
  (recursos financieros, técnicos y administrativos); el cambio abrupto de
  condiciones materiales es el compromiso de la etapa madura, no del primer
  día; el proyecto inicia de buena fe—. Énfasis en el diferenciador de
  mercado: el producto principal de la organización es su objetivo final; no
  se compite de frente, servicio contra servicio, contra los gigantes
  comerciales (secciones "Kinam", "Captación de recursos" y "Cambio de
  paradigma").
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
