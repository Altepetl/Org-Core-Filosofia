---
title: Especificación técnica del Inicio
status: draft
version: 0.2.0
created: 2026-08-12
updated: 2026-08-13
---

# Especificación técnica del Inicio

## 1. Contexto

Este documento especifica arquitecturalmente los tres proyectos vitales que el documento de [Filosofía](./Filosofia.md) define como **base mínima necesaria** para comenzar la operación del Altepetl. Sin estos tres proyectos no hay captación de recursos, ni administración pública de los mismos, ni trazabilidad financiera. Todo lo demás del Altepetl —Calpullis, organismos, gobernanza, distribución— presupone que esta base técnica existe.

La sección "El Inicio" de la Filosofía establece:

> Para iniciar se requiere de una serie de proyectos vitales:
> - Centro de datos
> - Gateway de pagos
> - Blockchain de Capa 1, con token nativo y mecanismo de consenso verde, que se define técnicamente como una **Blockchain Privada de Consorcio Único con Arquitectura de Oráculo Financiero**.

Este documento convierte esa lista en una especificación arquitectural: define objetivos, componentes, dependencias, fases y criterios de aceptación, sin llegar al nivel de implementación de código (eso corresponde a los repositorios de cada proyecto).

### Priorización por restricción legal

La Filosofía (sección "Restricción legal del Inicio") establece una jerarquía que esta especificación adopta:

1. **Prioridad 1: Centro de datos y Gateway de pagos.** El único ingreso inicial de la organización es el uso del Gateway de pagos como servicio.
2. **Sin prioridad 1: la Blockchain + Oráculo.** Se desarrolla en paralelo, pero su operación con recursos reales está bloqueada por ley hasta obtener la autorización de la CNBV como IFPE: el token es un fondo de pago electrónico por sustancia y el trámite toma alrededor de un año. El análisis completo está en el [Marco legal de la blockchain del Altepetl](./LegalBlockchain.md).
3. **Contingencia comercial.** Si los proyectos de prioridad 1 terminan antes que el trámite legal, el esfuerzo continúa en desarrollos de uso comercial que generen ganancias: app de pagos, terminal física de pagos y el Punto de Venta como Core de una plataforma de aplicaciones comerciales (ver sección 5.7).

Mientras no exista la autorización de IFPE, la blockchain y el token operan únicamente en entornos de desarrollo y prueba, sin fondos reales; los proyectos comerciales se venden como tecnología (licencia y operación), no como servicio de movimiento de dinero de terceros.

### Por qué estos tres proyectos y no otros

Los tres proyectos cubren las tres necesidades técnicas bloqueantes del Altepetl:

1. **Centro de datos** — dónde se aloja todo. Sin infraestructura propia, no hay soberanía.
2. **Gateway de pagos** — cómo entra el dinero al Altepetl. Sin captación, no hay recursos.
3. **Blockchain + Oráculo** — cómo se registra y distribuye el valor. Sin trazabilidad inmutable, no hay administración pública confiable.

Cualquier otra capacidad del Altepetl (red social, marketplace, herramientas de gestión de Calpullis, etc.) se construye sobre esta base y no forma parte del Inicio.

---

## 2. Visión arquitectónica general

### Diagrama de componentes

```
                EXTERIOR (clientes privados, usuarios, bancos)
                              │
                              ▼
                    ┌──────────────────┐
                    │  GATEWAY DE PAGOS│
                    │                  │
                    │  - Adquirencia   │
                    │  - Conciliación  │
                    │  - Tesorería     │
                    └────────┬─────────┘
                             │
                             │  cada transacción
                             │  se registra on-chain
                             ▼
    ECONOMÍA REAL     ┌──────────────────┐
    (bancos, ERPs)──▶ │   BLOCKCHAIN     │
           │          │   PRIVADA (PoA)  │
           │          │                  │
           ▼          │  - Token nativo  │
    ┌──────────────┐  │  - Smart contr.  │
    │   ORÁCULO    │  │  - Registro      │
    │ FINANCIERO   │──▶  inmutable       │
    │              │  │                  │
    │ - Validación │  └────────┬─────────┘
    │ - Firma      │           │
    │ - Consenso   │           │  distribución
    │   de datos   │           │  automática
    └──────────────┘           │
                               ▼
                    ┌──────────────────┐
                    │  SMART CONTRACTS │
                    │  (40/30/20/10)   │
                    └────────┬─────────┘
                             │
               ┌─────────────┼─────────────┐
               ▼             ▼             ▼
          Tesorería    Calpullis      Reinversión
                       (recompensas)     + Reserva
```

### Flujo de datos entre componentes

1. Un cliente (interno o privado) realiza un pago a través del **Gateway de Pagos**.
2. El Gateway registra cada transacción en la **Blockchain** (on-chain).
3. Cuando hay datos económicos del exterior que la blockchain no conoce por sí sola (ingresos reales, precios, conciliaciones bancarias), el **Oráculo Financiero** los valida, firma e introduce en la blockchain.
4. Los **Smart Contracts** de la blockchain ejecutan automáticamente la distribución de los recursos según las reglas definidas (por ejemplo, 40/30/20/10).
5. Todo este flujo se aloja y procesa en el **Centro de Datos** propio del Altepetl.

### Tabla de responsabilidades

| Componente | Responsabilidad principal | ¿Alojado en? |
|---|---|---|
| Centro de Datos | Proveer infraestructura física y virtual para todos los servicios | Propio (bare-metal) |
| Gateway de Pagos | Captar recursos del exterior, procesar transacciones, conciliar | Centro de Datos |
| Blockchain | Registrar transacciones de forma inmutable y ejecutar smart contracts | Centro de Datos |
| Oráculo Financiero | Introducir datos verificables del exterior a la blockchain | Centro de Datos |

---

## 3. Principios rectores

Estos principios se heredan del documento de Filosofía y rigen todas las decisiones técnicas de esta especificación.

### 3.1 Soberanía técnica

> *"La red pertenece a la organización y no a un proveedor externo."* — Filosofía, sección Blockchain del Altepetl.

La infraestructura debe ser **propia desde el día 1**. No se depende de cloud comercial para los servicios críticos. Esto es coherente con el rechazo al capital privado como inyección: depender de un proveedor cloud es una forma de dependencia financiera y técnica que contradice la soberanía de la organización.

El cloud comercial solo se considera para servicios auxiliares no críticos o como respaldo temporal, nunca como alojamiento principal de la blockchain, el gateway de pagos o los datos sensibles.

### 3.2 Comercio sí, capital como inyección no

> *"La frontera es clara: comercio sí, capital como inyección no."* — Filosofía, sección Capital financiero privado.

Los tres proyectos pueden vender servicios al sector privado (computo, procesamiento de pagos, acceso a la blockchain), pero ninguno acepta capital como inversión a cambio de control. Esta distinción se refleja técnicamente en que los servicios externos se facturan y se cobran, pero no otorgan al cliente ningún derecho de gobierno sobre la infraestructura.

### 3.3 Trazabilidad como condición de planificación

> *"Sin registro detallado no puede haber planificación seria; con él, sí."* — Filosofía, sección El camino.

La blockchain no es un adorno tecnológico: es la condición técnica que hace posible la planificación económica. Toda transacción relevante debe quedar registrada on-chain de forma inmutable. La trazabilidad no es opcional ni un extra; es el núcleo del sistema.

### 3.4 Registro público y transparencia

> *"Cualquiera, dentro o fuera de la organización, puede consultar los números en detalle."* — Filosofía, sección Blockchain del Altepetl.

Los datos de la blockchain son consultables públicamente. Lo privado es el control de la red (quién valida, quién emite), no la visibilidad de las transacciones. Esto refuerza la confianza y facilita la auditoría externa.

---

## 4. Centro de Datos

### 4.1 Objetivo

Proveer la infraestructura física y virtual sobre la que se alojan todos los servicios del Altepetl, con soberanía plena sobre el hardware, los datos y las comunicaciones.

### 4.2 Componentes

```
┌─────────────────────────────────────────────┐
│              CENTRO DE DATOS                │
│                                             │
│  ┌─────────────┐   ┌──────────────────┐    │
│  │  CÓMPUTO    │   │  ALMACENAMIENTO  │    │
│  │  (servidores│   │  (discos, NAS,   │    │
│  │   bare-metal)│  │   respaldos)     │    │
│  └─────────────┘   └──────────────────┘    │
│                                             │
│  ┌─────────────┐   ┌──────────────────┐    │
│  │    RED      │   │     ENERGÍA      │    │
│  │ (ruteo,     │   │ (UPS, generador, │    │
│  │  firewall,  │   │  respaldo)       │    │
│  │  ancho de   │   │                  │    │
│  │  banda)     │   │                  │    │
│  └─────────────┘   └──────────────────┘    │
│                                             │
└─────────────────────────────────────────────┘
```

**Cómputo:** servidores bare-metal (no instancias virtuales de terceros). Se prioriza hardware refurbishado o de segunda mano en buen estado para reducir costo inicial sin sacrificar soberanía.

**Almacenamiento:** discos locales en los servidores más almacenamiento NAS/SAN para datos compartidos y respaldos. Política de respaldos: 3-2-1 (3 copias, 2 medios distintos, 1 fuera de sitio).

**Red:** conexión redundante a internet (al menos dos proveedores), firewall perimetral, segmentación interna por VLAN. Ancho de banda simétrico suficiente para tráfico blockchain y de pagos.

**Energía:** UPS para cortes breves, generador para cortes prolongados. Se evalúa energía solar u otra fuente renovable como diferenciador ("consenso verde" aplicado a toda la infraestructura, no solo a la blockchain).

### 4.3 Restricciones

| Restricción | Implicación |
|---|---|
| Soberanía innegociable | No se usa cloud comercial para servicios críticos |
| Costo inicial acotado | Empezar con hardware refurbishado, escalar conforme entren recursos |
| Ubicación física | Debe estar en una jurisdicción donde la organización pueda operar legalmente |
| Conectividad | Mínimo dos enlaces a internet de proveedores distintos |
| Seguridad física | Acceso restringido, registro de entradas, protección contra fuego y agua |

### 4.4 Fases

**Fase 0 — Mínimo viable (MVP):**
- 2 servidores bare-metal (1 principal, 1 de respaldo).
- Almacenamiento local + 1 NAS para respaldos.
- 2 enlaces a internet.
- UPS.
- Ubicación: oficina o espacio arrendado con condiciones mínimas de seguridad física.

**Fase 1 — Rack propio:**
- 1 rack completo en un sitio adecuado (espacio arrendado o propio).
- 4-8 servidores.
- Almacenamiento NAS/SAN dedicado.
- Generador eléctrico.
- Sistema de monitoreo 24/7.

**Fase 2 — Multi-sitio:**
- 2 ubicaciones geográficas para alta disponibilidad.
- Replicación entre sitios.
- Capacidad de conmutación ante fallas.

### 4.5 Decisiones pendientes

- **Ubicación geográfica inicial** (país, ciudad, sitio específico).
- **Modelo energético** (red eléctrica + generador, vs. solar + baterías, vs. híbrido).
- **Política de adquisición de hardware** (refurbishado vs. nuevo, proveedores).
- **Stack de virtualización / orquestación** (Proxmox, Kubernetes, etc.) — se decide en la fase de implementación, no arquitectural.

---

## 5. Gateway de Pagos

### 5.1 Objetivo

Procesar pagos del exterior hacia el Altepetl y entre los participantes de la organización, registrar cada transacción on-chain, y mantener el puente entre dinero fiat (de afuera) y el token nativo (de adentro).

### 5.2 Componentes

```
┌─────────────────────────────────────────────┐
│            GATEWAY DE PAGOS                 │
│                                             │
│  ┌──────────────┐    ┌──────────────────┐  │
│  │ ADQUIRENCIA  │    │   TOKENIZACIÓN   │  │
│  │ (recibir     │    │  (sustituir datos│  │
│  │  pagos: tar- │    │   sensibles por  │  │
│  │  jetas, SPEI,│    │   tokens)        │  │
│  │  transferen- │    │                  │  │
│  │  cias)       │    │                  │  │
│  └──────┬───────┘    └────────┬─────────┘  │
│         │                     │            │
│         ▼                     ▼            │
│  ┌──────────────────────────────────────┐  │
│  │            CONCILIACIÓN              │  │
│  │ (verificar que lo que se cobró       │  │
│  │  coincide con lo que llegó al banco) │  │
│  └──────────────────┬───────────────────┘  │
│                     │                      │
│                     ▼                      │
│  ┌──────────────────────────────────────┐  │
│  │             TESORERÍA                │  │
│  │ (custodia de fondos fiat, pagos a    │  │
│  │  Calpullis, proveedores, etc.)       │  │
│  └──────────────────────────────────────┘  │
└─────────────────────────────────────────────┘
```

**Adquirencia:** capacidad de recibir pagos. En la fase inicial puede integrar métodos locales (SPEI en México, transferencias bancarias, tarjetas vía procesadores). El objetivo a largo plazo es reducir dependencia de procesadores externos.

**Tokenización:** los datos sensibles (números de tarjeta, cuentas bancarias) nunca se almacenan en claro; se sustituyen por tokens. Esto reduce el riesgo y el alcance de compliance PCI-DSS.

**Conciliación:** verifica que cada transacción cobrada coincida con el depósito bancario real. Discrepancias se marcan y se investigan. La conciliación es insumo directo del Oráculo Financiero.

**Tesorería:** custodia los fondos fiat, ejecuta pagos salientes (a Calpullis, proveedores, etc.) y mantiene el registro contable.

### 5.3 Integración con la blockchain

Cada transacción procesada por el Gateway se registra on-chain con:

- Identificador único de la transacción.
- Monto (en fiat y equivalente en token nativo).
- Origen y destino (anonimizados si es necesario).
- Timestamp.
- Hash de la conciliación bancaria correspondiente.

Esto hace que el flujo financiero completo sea trazable de extremo a extremo: desde que el cliente paga, hasta que el smart contract distribuye los recursos.

### 5.4 Modelo de doble entrada: fiat ↔ token

El Gateway actúa como puente entre el mundo fiat y el mundo on-chain:

```
    DINERO FIAT                       TOKEN NATIVO
    (exterior)                        (interior)
        │                                 │
        │    Cliente paga $100            │
        ▼────────────────────────────────▶│
        │                                 │
        │    Gateway emite 100 tokens     │
        │    (1 token = $1, respaldado)   │
        │◀────────────────────────────────│
        │                                 │
        │    Token circula dentro del     │
        │    Altepetl entre Calpullis     │
        │                                 │
        │    Alguien canjea token por $   │
        │◀────────────────────────────────│
        │    Gateway paga $ desde         │
        │    tesorería fiat               │
        ▼────────────────────────────────▶│
```

El token nativo está **respaldado 1:1** por los fondos fiat en tesorería, al menos en la fase inicial. Esto evita la especulación y mantiene el token como herramienta operativa, no financiera. El modelo de respaldo puede evolucionar en fases posteriores (ver decisiones pendientes).

### 5.5 Fases

**Fase 0 — Pagos internos (MVP):**
- Recepción de transferencias bancarias y SPEI.
- Conciliación manual asistida por herramientas.
- Emisión manual de tokens contra depósito verificado.
- Sin procesamiento de tarjetas todavía.

**Fase 1 — Integración bancaria completa:**
- APIs bancarias para conciliación automática.
- Procesamiento de tarjetas vía procesador externo.
- Emisión y canje de tokens automatizado.

**Fase 2 — APIs públicas:**
- Otros Calpullis y aplicaciones pueden integrar el gateway vía API.
- Posibilidad de ofrecer servicios de pago a clientes privados externos (consolidación, según Filosofía).

### 5.6 Decisiones pendientes

- **Jurisdicción bancaria** de las cuentas del Altepetl (afecta regulación y compliance).
- **Compliance KYC/AML** (conoce-a-tu-cliente / anti-lavado): qué nivel se aplica y cuándo.
- **Procesador de tarjetas** externo inicial (antes de tener adquirencia propia).
- **Política del modelo de respaldo del token** (1:1 fiat, respaldo parcial, u otro) y si evoluciona en el tiempo.
- **Comisiones** por uso del gateway (internas vs. externas).

### 5.7 Proyectos comerciales de contingencia

Si el Centro de datos y el Gateway quedan completos antes de que concluya el trámite de autorización ante la CNBV, el desarrollo no se detiene: continúa con productos comerciales que monetizan la infraestructura ya construida. En orden de adaptación natural:

1. **App de pagos.** Aplicación de pagos construida sobre el Gateway propio. Es el producto que más directamente aprovecha la adquirencia y la conciliación ya implementadas.
2. **Terminal física de pagos.** Terminal de cobro para comercios, conectada al Gateway. Extiende la captación del mundo digital al físico.
3. **Punto de Venta (Core).** No un punto de venta completo: el núcleo de una plataforma de aplicaciones. Sobre ese Core se construyen después los servicios de venta de productos: tiendas físicas (mini super) y tienda en línea (a la manera de Amazon o Walmart).

Mientras no exista la autorización de IFPE, estos proyectos se comercializan como **tecnología** (licencia y operación de software y hardware), no como servicio de movimiento de dinero de terceros. Su función es doble: generar los ingresos que sostienen a la organización durante el trámite, y ejercitar la infraestructura del Gateway y del Centro de datos sobre casos de uso reales, de modo que la blockchain y el token se monten al final sobre una base ya operada y probada.

---

## 6. Blockchain + Oráculo Financiero

### 6.1 Objetivo

Proveer un registro inmutable de todas las transacciones relevantes del Altepetl, un token nativo como mecanismo de intercambio interno, y smart contracts que automaticen la distribución de recursos según reglas aprobadas por la organización.

### 6.2 Capa 1 — Blockchain

#### Mecanismo de consenso: Proof of Authority (PoA)

**Decisión:** PoA.

**Justificación:**
- La Filosofía define la red como "Privada de Consorcio Único" — hay una entidad coordinadora (el Altepetl) que controla quién participa.
- PoA es eficiente en energía ("consenso verde"): no requiere cómputo masivo como PoW, ni capital en stake como PoS.
- La confianza recae en la organización, no en minería anónima ni en acumulación de capital. Esto es coherente con el rechazo al capital privado: PoS introduciría una dinámica de capital no deseada.
- Los validadores son aprobados por el Altepetl a través de su proceso de gobernanza.

**Trade-off aceptado:** PoA es menos descentralizado que PoW/PoS. Para el Altepetl esto no es un defecto, es una característica: la organización tiene soberanía sobre su propia red.

#### Nodos validadores

```
                ┌──────────────────────┐
                │      ALTEPETL        │
                │  (gobernanza)        │
                └──────────┬───────────┘
                           │  aprueba
                           ▼
            ┌──────────────┼──────────────┐
            ▼              ▼              ▼
        Validador 1   Validador 2   Validador 3
        (sitio A)     (sitio A)     (sitio B)
            │              │              │
            └──────────────┼──────────────┘
                           │
                           ▼
                    BLOCKCHAIN PÚBLICA
                    (datos visibles,
                     control privado)
```

- En la **Fase 0 (MVP)** puede operar con 1 validador (desarrollo y prueba).
- En **Fase 1** se requiere mínimo 3 validadores para tolerancia a fallas (BFT).
- En **Fase 2** los validadores se distribuyen entre múltiples sitios para alta disponibilidad.
- Los validadores son gestionados por el Altepetl; en el futuro, Calpullis o Colectivos autorizados podrían operar validadores, siempre bajo la gobernanza de la organización.

#### Token nativo

**Propósito:** mecanismo de intercambio dentro de la organización. No es especulativo.

**Características técnicas:**
- Emitido por el Gateway de Pagos contra depósito fiat (modelo 1:1 en fase inicial).
- Transferible entre participantes del Altepetl (Calpullis, organismos, personas).
- Todas las transferencias quedan registradas on-chain.
- La política de emisión y canje es definida por la gobernanza del Altepetl.

**Lo que NO es el token:**
- No es una criptomoneda de mercado abierto para especulación.
- No otorga derechos de gobierno (eso va por reputación, no por tenencia).
- No se mina ni se staked.

### 6.3 Oráculo Financiero

El oráculo es el puente entre la economía real (bancos, ERPs, ingresos) y la blockchain. La Filosofía detalla sus mecanismos de verificación; aquí se especifica su arquitectura.

#### Fuentes de datos

```
┌──────────────────────────────────────────────┐
│              FUENTES EXTERNAS                │
│                                              │
│  ┌─────────┐  ┌─────────┐  ┌─────────────┐ │
│  │ BANCOS  │  │  ERPs   │  │ CONCILIACIÓN│ │
│  │ ( APIs, │  │ (sistemas│  │ (del gateway│ │
│  │ estados │  │ contables│  │ de pagos)   │ │
│  │ de      │  │ de       │  │             │ │
│  │ cuenta) │  │ Calpullis│  │             │ │
│  └────┬────┘  └────┬────┘  └──────┬──────┘ │
│       │            │              │         │
└───────┼────────────┼──────────────┼─────────┘
        │            │              │
        ▼            ▼              ▼
   ┌──────────────────────────────────────┐
   │         RECOLECCIÓN DE DATOS         │
   │   (múltiples fuentes por cada dato)  │
   └──────────────────┬───────────────────┘
                      │
                      ▼
   ┌──────────────────────────────────────┐
   │         VALIDACIÓN CRUZADA           │
   │  (comparación entre fuentes,         │
   │   límites de variación, firmas)      │
   └──────────────────┬───────────────────┘
                      │
                      ▼
   ┌──────────────────────────────────────┐
   │           FIRMA Y ENVÍO              │
   │   (datos firmados se introducen      │
   │    en la blockchain)                 │
   └──────────────────────────────────────┘
```

#### Mecanismos de verificación (heredados de la Filosofía)

El documento de Filosofía (sección "Integridad del oráculo") exige:

1. **Múltiples fuentes independientes** — cada dato relevante debe confirmarse con más de una fuente.
2. **Firmas digitales** — cada validador del oráculo firma los datos que aprueba.
3. **Auditoría** — registro de cada dato y su validación, consultable.
4. **Pruebas criptográficas** cuando sean posibles.
5. **Conciliación bancaria** — los datos económicos se confrontan con los estados de cuenta bancarios.
6. **Límites de variación y detección de anomalías** — si un dato difiere más de lo esperado del histórico o de otras fuentes, se marca para revisión.
7. **Múltiples validadores** — no basta con un validador; se requiere consenso entre varios.
8. **Trazabilidad de cada dato** — de la fuente al registro on-chain.
9. **Mecanismos de disputa** — si dos fuentes legítimas entran en conflicto, hay un proceso para resolverlo.
10. **Separación estricta entre quien produce el dato y quien lo valida** — el Calpulli que reporta un ingreso no puede ser el mismo que lo valida.

#### Separación productor/validador

Este punto es crítico. El flujo debe ser:

```
Calpulli A reporta:   "generé $500,000"
                          │
                          ▼
Validador independiente 1  ──┐
Validador independiente 2  ──┼──▶  si coinciden,
Validador independiente 3  ──┘     dato firmado
                                    y enviado on-chain
                          │
                          ▼
                si no coinciden:
                se inicia disputa,
                no se registra el dato
```

Un Calpulli nunca valida sus propios datos. Esta separación es la defensa principal contra reportes falsos.

### 6.4 Smart Contracts de distribución

#### Regla 40/30/20/10

La Filosofía (sección Oráculo Financiero) propone como ejemplo:

```
Beneficio = $500,000
  40% → Tesorería del Altepetl
  30% → Recompensas al Calpulli
  20% → Reinversión
  10% → Reserva
```

Esta regla se codifica como un smart contract que se ejecuta automáticamente cuando el oráculo introduce un dato de beneficio verificado. Nadie manipula la distribución manualmente; la regla es código ejecutable y auditable.

#### Mutabilidad y gobernanza de los contratos

- Los smart contracts **son inmutables** una vez desplegados, pero pueden ser reemplazados por nuevas versiones mediante un proceso de gobernanza aprobado por la organización.
- Las reglas de distribución (los porcentajes) son parámetros configurables a través de otro contrato de gobernanza, no están hardcoded en el contrato de distribución.
- Cualquier cambio a un contrato en producción requiere aprobación según el umbral constitucional del Altepetl (2/3 mínimo, meta 100%).
- Los contratos antiguos no se borran; permanecen en la blockchain como historial.

### 6.5 Fases

**Fase 0 — Red local (MVP):**
- 1 nodo validador en el centro de datos.
- Token nativo desplegado, sin valor especulativo.
- Smart contract de distribución básica (40/30/20/10).
- Oráculo simple con 1 fuente y 1 validador (suficiente para pruebas, no para producción con fondos reales).

**Fase 1 — Red con N validadores:**
- Mínimo 3 validadores en sitios distintos.
- Oráculo con múltiples fuentes y múltiples validadores.
- Smart contracts actualizados y auditados.
- Listo para operar con fondos reales.

**Fase 2 — Oráculo productivo y APIs:**
- Oráculo integrado con APIs bancarias en tiempo real.
- Smart contracts para múltiples tipos de distribución (no solo la regla base).
- Capacidad de que otros Calpullis interactúen con la blockchain vía API.

### 6.6 Decisiones pendientes

- **Stack tecnológico de la blockchain** (ej: Hyperledger Besu, Quorum, Substrate, Geth con PoA, etc.) — se decide en implementación según madurez, gobernanza del proyecto, y licencia.
- **Modelo de emisión del token** (1:1 respaldado, suministro fijo, u otro).
- **Política de privacidad de transacciones** (todas públicas vs. algunas cifradas vs. selectividad).
- **Modelo de tarifas por transacción** (¿se cobra gas interno?).
- **Número y distribución inicial de validadores.**
- **Proceso formal de actualización de smart contracts.**

---

## 7. Dependencias cruzadas

### Tabla de dependencias

| Componente | Depende de | Bloquea a |
|---|---|---|
| Centro de Datos | (nada — base física) | Gateway, Blockchain, Oráculo |
| Gateway de Pagos | Centro de Datos, Blockchain | Captación de recursos, Tesorería |
| Blockchain (Capa 1) | Centro de Datos | Gateway, Oráculo, Smart Contracts |
| Oráculo Financiero | Blockchain, Gateway (conciliación) | Smart Contracts de distribución |
| Smart Contracts | Blockchain, Oráculo | Distribución automática |
| Token Nativo | Blockchain, Gateway | Intercambio interno |

### Orden crítico de construcción

```
1. Centro de Datos (Fase 0)
       │
       ▼
2. Blockchain (Fase 0 — 1 validador, sin oráculo)
       │
       ▼
3. Gateway de Pagos (Fase 0 — registro manual on-chain)
       │
       ▼
4. Oráculo Financiero (Fase 0 — 1 fuente, 1 validador)
       │
       ▼
5. Smart Contracts de distribución (Fase 0)
       │
       ▼
   MVP COMPLETO
```

### Punto de bloqueo mínimo para "salir a producción"

Salir a producción con fondos reales tiene **dos puertas**: una legal y una técnica. La legal va primero:

0. **Puerta legal (bloqueante):** autorización de la CNBV como IFPE, o alianza vigente con una IFPE existente que emita y custodie los fondos. Sin ella, ningún componente opera con dinero de terceros, sin importar su madurez técnica. Ver [Marco legal de la blockchain del Altepetl](./LegalBlockchain.md).

Cumplida la puerta legal, para que el Inicio se considere funcional —es decir, para que el Altepetl pueda captar, registrar y distribuir recursos— deben estar operativos:

1. Centro de Datos Fase 0.
2. Blockchain Fase 0 con token nativo desplegado.
3. Gateway de Pagos Fase 0 (al menos recepción de transferencias y emisión manual de tokens).
4. Smart contract de distribución 40/30/20/10 desplegado.

El Oráculo Financiero Fase 0 puede operar de forma asistida (validación humana) mientras se automatiza en Fase 1.

---

## 8. Decisiones de diseño pendientes

Consolidación de todas las decisiones que esta especificación deja abiertas. Cada una se marca con el responsable y el momento de resolución.

| # | Decisión | Responsable | Resolución |
|---|---|---|---|
| 1 | Ubicación geográfica inicial del centro de datos | Organización Altepetl | Antes de Fase 0 |
| 2 | Modelo energético del centro de datos | Equipo de infraestructura | Fase 0 |
| 3 | Política de adquisición de hardware | Equipo de infraestructura | Fase 0 |
| 4 | Stack de virtualización / orquestación | Equipo de infraestructura | Fase 0 |
| 5 | Jurisdicción bancaria de las cuentas | Organización Altepetl | Antes de Fase 0 |
| 6 | Compliance KYC/AML | Equipo legal / financiero | Antes de Fase 0 |
| 7 | Procesador de tarjetas externo inicial | Equipo de pagos | Fase 1 |
| 8 | Política de respaldo del token | Organización Altepetl | Antes de Fase 0 |
| 9 | Comisiones del gateway | Organización Altepetl | Fase 1 |
| 10 | Stack tecnológico de la blockchain | Equipo de blockchain | Fase 0 (implementación) |
| 11 | Modelo de emisión del token | Organización Altepetl | Antes de Fase 0 |
| 12 | Política de privacidad de transacciones | Organización Altepetl | Fase 1 |
| 13 | Modelo de tarifas (gas) | Equipo de blockchain | Fase 1 |
| 14 | Número y distribución inicial de validadores | Organización Altepetl | Fase 1 |
| 15 | Proceso formal de actualización de smart contracts | Organización Altepetl | Fase 1 |
| 16 | Ruta legal del token: autorización IFPE propia vs. alianza con una IFPE existente | Organización Altepetl | Antes de Fase 0 |
| 17 | Alcance comercial de los proyectos de contingencia (app de pagos, terminal física, Punto de Venta Core) | Organización Altepetl | Fase 0 |

Las decisiones marcadas "Antes de Fase 0" son bloqueantes para iniciar la construcción. Las de "Fase 0" pueden tomarse durante el desarrollo inicial. Las de "Fase 1" pueden posponerse sin bloquear el MVP.

---

## 9. Criterios de aceptación del MVP

El Inicio se considera completo cuando se cumplen **todos** los siguientes criterios. Los criterios técnicos se verifican en entorno de desarrollo o pruebas; la operación con fondos reales exige además el criterio legal.

### Centro de Datos

- [ ] Al menos 2 servidores bare-metal operativos.
- [ ] Almacenamiento con política de respaldo 3-2-1 implementada.
- [ ] Conectividad redundante a internet (2 proveedores).
- [ ] UPS instalado y probado.
- [ ] Acceso físico restringido y registrado.

### Blockchain

- [ ] Red PoA operativa con al menos 1 validador.
- [ ] Token nativo desplegado y transferible.
- [ ] Al menos 1 smart contract de distribución (40/30/20/10) desplegado y funcional.
- [ ] Consulta pública de transacciones operativa (explorador de bloques, aunque sea básico).

### Gateway de Pagos

- [ ] Recepción de al menos 1 método de pago fiat (transferencia/SPEI).
- [ ] Conciliación implementada (aunque sea asistida).
- [ ] Emisión de tokens contra depósito verificado (aunque sea manual en Fase 0).
- [ ] Registro on-chain de cada transacción procesada.

### Oráculo Financiero

- [ ] Al menos 1 fuente de datos externa integrada.
- [ ] Al menos 1 validador operativo (puede ser humano en Fase 0).
- [ ] Mecanismo de disputa documentado (aunque no esté automatizado).

### Legal

- [ ] Autorización de la CNBV como IFPE obtenida, o alianza vigente con una IFPE existente, antes de operar cualquier componente con fondos reales de terceros.

### Integración

- [ ] Flujo completo probado de extremo a extremo en entorno de pruebas: pago → registro on-chain → distribución automática por smart contract.
- [ ] Documentación operativa del flujo completo.
- [ ] Al menos una auditoría externa (incluso informal) del flujo.

---

## 10. Referencias

- [Filosofía del Altepetl](./Filosofia.md) — fuente de los principios y definiciones de los proyectos del Inicio, incluida la priorización por restricción legal.
- [Marco legal de la blockchain del Altepetl](./LegalBlockchain.md) — por qué el token es un fondo de pago electrónico y qué exige la ley mexicana para operarlo; fuente de la puerta legal de la sección 7.
- [Pensamiento Crítico](https://github.com/Altepetl/Org-Core-CriticalThinking) — marco de análisis que rige la toma de decisiones del Altepetl.
- Estándares de gestión referenciados en la Filosofía: ISO 27001 (seguridad de la información), ISO 20000 (gestión de servicios de TI), COBIT (gobierno de TI), ITIL (gestión de servicios).

---

## Notas de versión

**0.2.0 (2026-08-13):** Alineación con la restricción legal definida en la Filosofía y el documento [Marco legal de la blockchain del Altepetl](./LegalBlockchain.md). Se establece la priorización del Inicio (Centro de datos y Gateway con prioridad 1; blockchain en paralelo sin prioridad 1, bloqueada para fondos reales hasta la autorización de la CNBV como IFPE). Se agrega la sección 5.7 con los proyectos comerciales de contingencia (app de pagos, terminal física, Punto de Venta Core). La salida a producción ahora tiene una puerta legal explícita (sección 7) y un criterio de aceptación legal (sección 9). La decisión #6 (KYC/AML) se reclasifica como bloqueante previa a Fase 0 y se agregan las decisiones #16 (ruta legal del token) y #17 (alcance de los proyectos de contingencia).

**0.1.0 (2026-08-12):** Versión inicial. Especifica arquitecturalmente los tres proyectos del Inicio (Centro de Datos, Gateway de Pagos, Blockchain + Oráculo Financiero) con fases, dependencias y criterios de aceptación del MVP. Las decisiones de implementación (lenguajes, frameworks, tecnologías concretas) se dejan abiertas para los repositorios de cada proyecto.
