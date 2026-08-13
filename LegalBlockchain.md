---
title: Marco legal de la blockchain del Altepetl
status: draft
version: 0.1.0
created: 2026-08-13
updated: 2026-08-13
---

# Marco legal de la blockchain del Altepetl

Este documento analiza el encuadre legal de la blockchain del Altepetl bajo la
legislación mexicana vigente. Su conclusión central: **el token nativo del
Altepetl es, por sustancia económica y por definición legal, un fondo de pago
electrónico**, y por tanto la organización solo puede operarlo dentro del marco
de la Ley para Regular las Instituciones de Tecnología Financiera (LRITF o
"Ley Fintech").

Este documento es un análisis informativo, no asesoría legal. Antes de cualquier
operación con recursos reales, el Altepetl debe contratar asesoría jurídica
especializada en regulación financiera mexicana.

---

## 1. Antecedente histórico

### Antes de 2018: el vacío

Antes de 2018, México no tenía un marco jurídico específico para el dinero
electrónico emitido por no bancos. Las billeteras digitales, los agregadores de
pago y las primeras plataformas de criptoactivos operaban en zonas grises: unas
como comisionistas mercantiles, otras bajo figuras que no correspondían a su
actividad real. El Banco de México (Banxico) emitía criterios parciales, pero
no existía una figura legal que cubriera la emisión de valor monetario
electrónico contra recepción de dinero.

### 2018: la Ley Fintech

El 9 de marzo de 2018 se publicó en el Diario Oficial de la Federación la
**Ley para Regular las Instituciones de Tecnología Financiera (LRITF)**. La ley
crea la figura paraguas de Institución de Tecnología Financiera (ITF), con dos
tipos:

- **IFPE** — Institución de Fondos de Pago Electrónico: billeteras digitales,
  medios de pago, transferencias.
- **IFC** — Institución de Financiamiento Colectivo: crowdfunding.

El artículo 22 reserva a las IFPE autorizadas los servicios de **emisión,
administración, redención y transmisión de fondos de pago electrónico**, y el
artículo 23 define qué es un fondo de pago electrónico (ver sección 2). En
septiembre de 2018 la CNBV publicó la regulación secundaria (Disposiciones de
carácter general aplicables a las ITF), que fija capitales mínimos, gobierno
corporativo y requisitos de operación.

### 2018–2019: Banxico fija las reglas operativas

- **Circular 12/2018** (diciembre de 2018): regula las operaciones de las IFPE.
  Entre otras cosas, exige que la emisión de fondos de pago electrónico se
  realice en los **tres segundos** siguientes a la recepción de los recursos,
  con consentimiento expreso del cliente.
- **Circular 4/2019** (marzo de 2019, modificada por la Circular 37/2020):
  resuelve la facultad que la LRITF da a Banxico para determinar con qué
  activos virtuales pueden operar las instituciones financieras. La resolución
  fue restrictiva: **las instituciones financieras no pueden celebrar ni
  ofrecer operaciones con activos virtuales al público**; solo operaciones
  internas, con autorización previa de Banxico.

### 2021: el comunicado conjunto

En junio de 2021, la SHCP, la CNBV y Banxico emitieron un comunicado conjunto
que reiteró la posición: los activos virtuales **no son moneda de curso legal**
en México y las instituciones financieras **no están autorizadas** a realizar
ni ofrecer al público operaciones con ellos.

### Lo que la práctica ha confirmado

- Banxico **nunca ha autorizado un solo activo virtual** para operar dentro del
  sistema financiero regulado. La puerta del artículo 31 de la LRITF existe en
  el papel, pero en siete años no se ha abierto.
- Las ITF autorizadas son pocas (alrededor de una veintena a 2026) y el proceso
  de autorización toma en la práctica **más de un año**.
- En 2026 la CNBV reforzó los requisitos: ciberseguridad obligatoria y
  capitales mínimos al alza en varias figuras.

---

## 2. Los dos caminos legales

La LRITF contiene dos definiciones que a simple vista parecen lo mismo —"valor
registrado electrónicamente"— pero que viven en regímenes regulatorios
opuestos. Toda la arquitectura legal del proyecto depende de bajo cuál de las
dos cae el token.

### Camino A: Fondo de pago electrónico (art. 23 LRITF)

Un fondo de pago electrónico es un recurso contabilizado en un registro
electrónico de cuentas transaccionales que cumple tres elementos:

1. Se refiere a un **valor monetario a la par** con una cantidad determinada de
   dinero en moneda nacional (o, con autorización de Banxico, moneda extranjera).
2. Constituye una **obligación de pago del emisor** por la misma cantidad.
3. Se emite **contra la recepción de dinero**, con el propósito de abonar,
   transferir o retirar los fondos electrónicamente.

Jurídicamente, un fondo de pago electrónico **es pesos**: el emisor le debe
pesos al cliente. Operarlo requiere autorización como IFPE, con todas sus
obligaciones (sección 4), pero el camino existe y es transitable: hay banca,
hay custodia regulada, hay redención legal a la par.

**Ejemplos de este camino:**

- **Mercado Pago** — autorizada como IFPE en mayo de 2022 por CNBV, SHCP y
  Banxico. Recibe pesos, emite saldo a la par, permite transferirlo y retirarlo.
- **Clip** — IFPE enfocada en adquirencia y pagos a comercios.
- **Klar** — opera su cuenta de pago bajo figura regulada.

### Camino B: Activo virtual (art. 30 LRITF)

Un activo virtual es una "representación de valor registrada electrónicamente y
utilizada entre el público como medio de pago, **pero que no es moneda de curso
legal**". Jurídicamente no es pesos: es *otra cosa* cuyo valor flota.

Para las instituciones financieras reguladas, este camino está **cerrado**:
la Circular 4/2019 les prohíbe ofrecer activos virtuales al público y Banxico
nunca ha autorizado ninguno. Fuera del sistema regulado, comprar, vender y
custodiar criptoactivos es legal para particulares y empresas, pero como simple
**actividad vulnerable** ante la LFPIORPI (art. 17, fracción XVI), es decir:

- Sin licencia financiera: no hay supervisión prudencial, pero tampoco hay
  acceso institucional al sistema financiero.
- **Sin banca confiable**: ningún banco mexicano puede dar servicio a un
  esquema que ofrece activos virtuales al público, porque la Circular 4/2019
  también los cubre a ellos.
- Sin SPEI, sin fideicomiso de custodia regulado, sin protección al usuario
  financiero.

**Ejemplos de este camino:**

- **Bitso** — opera el intercambio de criptoactivos fuera del perímetro de la
  LRITF, como actividad vulnerable ante la LFPIORPI (con obligaciones de aviso
  a la UIF desde umbrales bajos: 210 UMA por cliente). Su lado en pesos depende
  de estructuras y socios separados del negocio cripto.
- Cualquier exchange que sirva a mexicanos opera bajo esta misma fragilidad:
  legal, pero **desconectado del sistema bancario institucional**.

### Tabla comparativa

| | FPE (Camino A) | Activo virtual (Camino B) |
|---|---|---|
| Naturaleza | Pesos (obligación de pago a la par) | Valor flotante, no es moneda |
| Figura | IFPE autorizada (LRITF) | Actividad vulnerable (LFPIORPI) |
| Acceso a banca / SPEI | Sí | No (bloqueado por Circular 4/2019) |
| Redención 1:1 garantizable | Sí, regulada | No dentro del sistema regulado |
| Licencia posible | Sí (proceso de 1+ año) | No existe licencia financiera |
| Protección al usuario | CONDUSEF, LPDUSF | Ninguna |

### La regla que decide: sustancia sobre forma

Los reguladores y los jueces evalúan la **sustancia económica** de la
operación, no el nombre del instrumento ni la tecnología que lo registra.
Llamar "token" a un fondo de pago electrónico no lo convierte en activo
virtual, igual que llamar "activo virtual" a un pasivo redimible a la par en
pesos no lo saca de la definición del art. 23. Un "criptoactivo" que el emisor
se obliga a redimir siempre a la par contra pesos depositados es, por
definición jurídica y económica, dinero electrónico.

---

## 3. Por qué la blockchain del Altepetl es un FPE

El modelo del Altepetl, según la [Especificación del Inicio](./Especificacion.md)
(sección 5.4, modelo de doble entrada fiat ↔ token), es:

> Un cliente paga $100 → el Gateway emite 100 tokens (1 token = $1, respaldado)
> → el token circula dentro del Altepetl entre Calpullis → alguien canjea el
> token por $ → el Gateway paga $ desde tesorería fiat.

Contrastado contra los tres elementos del art. 23 de la LRITF:

1. **Valor monetario a la par.** El token está definido como "1 token = $1,
   respaldado 1:1 por los fondos fiat en tesorería". No flota, no especula.
   Cumple el elemento.
2. **Obligación de pago del emisor.** El canje desde tesorería es exactamente
   una obligación de pago del emisor por la misma cantidad: quien presenta el
   token recibe pesos. Cumple el elemento.
3. **Emitido contra recepción de dinero, para transferir o retirar.** El
   Gateway emite el token únicamente contra depósito verificado, y su propósito
   declarado es que circule entre Calpullis y se canjee. Cumple el elemento.

Los tres elementos se cumplen literalmente. Además, las cuatro operaciones que
la especificación describe son exactamente los cuatro servicios que el art. 22
reserva a las IFPE autorizadas:

| Servicio reservado (art. 22) | Dónde ocurre en el Altepetl |
|---|---|
| **Emisión** | Gateway emite tokens contra depósito fiat verificado |
| **Administración** | Tesorería custodia fondos y mantiene cuentas de Calpullis |
| **Redención** | Canje de token por pesos desde tesorería |
| **Transmisión** | Transferencias de tokens entre Calpullis y personas |

### Ejemplos concretos dentro del modelo Altepetl

- **Emisión:** el Calpulli Chapulines 5 de Mayo vende su aplicación a un
  cliente privado; el cliente paga $500,000 por el Gateway; el Gateway emite
  500,000 tokens al Calpulli. Eso es emisión de FPE.
- **Transmisión:** el Calpulli paga 80,000 tokens al organismo de Amas de casa
  por la remuneración del trabajo del hogar. Eso es transmisión de FPE.
- **Redención:** una persona del Calpulli canjea 5,000 tokens para pagar su
  renta en pesos; tesorería le transfiere $5,000. Eso es redención de FPE.
- **Distribución automática:** el smart contract 40/30/20/10 distribuye los
  fondos de pago electrónico entre tesorería, recompensas, reinversión y
  reserva. La regla también opera sobre FPE y hereda toda la regulación.

### Lo que NO es FPE: la blockchain de gobernanza

La separación es importante. La blockchain del Altepetl registra dos cosas
distintas:

- **Valor redimible** (el token) → es FPE, regulado por la LRITF.
- **Registros de gobernanza** (historiales de trabajo, votaciones, decisiones
  del Tlahtocan, marcas, registro de proyectos) → no mueven valor redimible,
  no son medio de pago, **no son activos virtuales en el sentido del art. 30**
  y quedan fuera de la Ley Fintech.

Esta segunda función se puede construir y operar libremente hoy. La regla
práctica es: **registros sí, dinero solo por la vía regulada**.

### La consecuencia inevitable

Dado que el token es un FPE por sustancia, el Altepetl tiene solo tres
opciones coherentes con la ley:

1. **Ser IFPE**: constituir la sociedad, juntar el capital y obtener la
   autorización (sección 4).
2. **Montarse sobre una IFPE existente**: un socio autorizado custodia los
   fondos y emite los FPE; el Altepetl opera la plataforma y la blockchain
   como capa de registro. Más rápido, a costa de dependencia del socio —en
   tensión con el principio de soberanía, que debe decidirse conscientemente.
3. **No mover dinero**: operar únicamente la blockchain de gobernanza y los
   proyectos productivos sin token redimible, hasta cumplir 1 o 2.

Lo que **no** existe es una cuarta opción: operar el token redimible sin
autorización, declarándolo "cripto" o "token de gobernanza". Eso es emitir
fondos de pago electrónico sin ser IFPE, con las consecuencias de la sección 5.

---

## 4. Lo que el Altepetl debe cumplir para operar una blockchain FPE

### 4.1 Figura societaria y autorización

La IFPE debe ser una **sociedad anónima** mexicana constituida
expresamente para este objeto. La autorización la otorga la **CNBV**, con
opinión favorable de la **Comisión Interinstitucional** integrada por SHCP,
CNBV y Banxico. En la práctica el proceso toma más de un año (~416 días en
promedio reportado por despachos especializados).

Nota sobre la estructura institucional del Altepetl: la Filosofía prevé crear
organizaciones, empresas, cooperativas y asociaciones civiles. La IFPE sería
una más de esas instituciones —una S.A. regulada dentro del ecosistema—, no la
organización entera.

### 4.2 Capital mínimo

- **500,000 UDIS** (~$4.4 MDP, variable con la UDI) para una IFPE que opera
  solo en moneda nacional y sin operaciones adicionales.
- **700,000 UDIS** si la autorización contempla operaciones adicionales
  (moneda extranjera, activos virtuales internos, derivados).
- Advertencia: la CNBV elevó capitales mínimos en 2026 para otras figuras
  (las IFC de deuda pasaron a 1,500,000 UDIS). La cifra vigente debe
  verificarse al momento de solicitar.

### 4.3 Expediente de autorización

- Plan operativo y de negocios.
- Manuales de operación y de seguridad de la información (la ciberseguridad es
  requisito reforzado desde 2026).
- Estructura de gobierno corporativo.
- Acreditación de **honorabilidad y solvencia** de accionistas, consejeros y
  funcionarios relevantes —con información adicional para participaciones
  mayores al 5–10% del capital.
- Sistema de prevención de lavado (PLD) completo.

### 4.4 Obligaciones operativas permanentes

- **PLD/KYC (art. 58 LRITF):** identificación de clientes por niveles,
  monitoreo de operaciones, y reporte de operaciones relevantes, inusuales e
  internas preocupantes a la UIF. No es opcional ni gradual: es condición de
  operación.
- **Circular 12/2018 de Banxico:** emisión de los fondos en los **3 segundos**
  siguientes a recibir los recursos, con consentimiento expreso del cliente;
  reglas de administración de las cuentas transaccionales.
- **Efectivo:** recibir o entregar efectivo requiere autorización adicional de
  la CNBV, con límites.
- **SPEI:** la participación en el SPEI requiere convenio separado con
  Banxico; no viene incluido en la autorización de IFPE.
- **Segregación:** los recursos de los clientes deben mantenerse separados del
  patrimonio de la institución.
- **Transparencia obligatoria:** informar expresamente al cliente que los
  fondos de pago electrónico **no son depósitos bancarios y no están
  protegidos por el IPAB**.
- **CONDUSEF:** registro de contratos de adhesión y sujeción a la Ley de
  Protección y Defensa al Usuario de Servicios Financieros.
- **Auditoría y supervisión continua** por CNBV y Banxico.

### 4.5 Prohibiciones que el diseño del Altepetl debe respetar

- **No pagar intereses ni rendimientos.** Esto impacta directamente la regla
  40/30/20/10: el "30% de recompensas al Calpulli" **no puede estructurarse
  como rendimiento sobre fondos depositados**. Debe documentarse como pago por
  trabajo, productos o servicios reales, o la distribución corre sobre
  utilidades de la sociedad —nunca como retorno del saldo del cliente.
- **No captar ahorro** ni ofrecer productos de inversión.
- **No otorgar crédito** con recursos de los clientes.

### 4.6 Diseño del token bajo el marco FPE

La tecnología no cambia —la blockchain PoA es precisamente el "registro
electrónico de cuentas transaccionales" que el art. 23 exige, y de hecho lo
supera en auditabilidad—. Lo que debe cumplir el diseño jurídico del token:

- Denominado **en pesos, siempre a la par**, sin mercado secundario ni precio
  flotante.
- Obligación expresa del emisor de redimir 1:1.
- Circulación **solo entre clientes identificados** (KYC), nunca anónima —
  coherente con el registro de trayectorias que la Gobernanza ya exige.
- El canje opera como **redención regulada**, no como intercambio de activos.

### 4.7 Datos personales: LFPDPPP

La Ley Federal de Protección de Datos Personales garantiza los derechos ARCO,
incluida la **cancelación**. Un historial personal inmutable con "marcas
permanentes que nunca se borran, ni al salir de la organización" (Gobernanza,
secciones 4 y 8) es contrario al derecho de cancelación. La solución de diseño:

- **On-chain:** datos financieros y de gobernanza seudonimizados o
  anonimizados (como la Especificación ya prevé para origen y destino).
- **Off-chain:** datos personales identificables, con la llave de vinculación
  destruible para hacer efectiva la cancelación.

### 4.8 Fiscal

- La emisión y redención de tokens tiene tratamiento de IVA e ISR que debe
  definirse con el SAT desde el diseño.
- Las "aportaciones voluntarias" solo son donativos deducibles si el receptor
  es donataria autorizada; de lo contrario son ingreso acumulable.

### 4.9 Sanciones por operar sin autorización

Emitir fondos de pago electrónico sin ser IFPE autorizada implica:

- **Suspensión inmediata y clausura** del establecimiento por la CNBV.
- **Multas** de 5,000 a 150,000 UMA.
- Potencial **responsabilidad penal** por captación ilegal de recursos del
  público.

Para una organización cuyo activo principal es la credibilidad pública, este
escenario no es un riesgo aceptable: es un riesgo terminal.

---

## 5. Lista de requisitos

Checklist consolidado para que el Altepetl opere legalmente su blockchain
como FPE. Los items marcados **[Bloqueante Fase 0]** impiden recibir el primer
peso; los demás son condiciones de operación continua.

### Societario y autorización

- [ ] **[Bloqueante Fase 0]** Constituir una sociedad anónima mexicana con
  objeto de IFPE (o firmar alianza con una IFPE autorizada existente).
- [ ] **[Bloqueante Fase 0]** Capital mínimo pagado: 500,000 UDIS (verificar
  cifra vigente al momento de la solicitud).
- [ ] **[Bloqueante Fase 0]** Autorización de la CNBV con opinión favorable de
  la Comisión Interinstitucional (SHCP, CNBV, Banxico).
- [ ] Expediente completo: plan operativo, manuales, gobierno corporativo,
  honorabilidad y solvencia de accionistas y funcionarios.

### Prevención de lavado

- [ ] **[Bloqueante Fase 0]** Sistema PLD/KYC conforme al art. 58 LRITF y sus
  disposiciones: identificación por niveles, monitoreo, reportes a la UIF.
- [ ] Oficial de cumplimiento designado.

### Operación del token

- [ ] **[Bloqueante Fase 0]** Token denominado en pesos a la par, sin mercado
  secundario, redimible 1:1 por obligación expresa del emisor.
- [ ] **[Bloqueante Fase 0]** Circulación solo entre clientes identificados.
- [ ] Emisión en 3 segundos tras recepción de recursos (Circular 12/2018),
  con consentimiento expreso del cliente.
- [ ] Autorización adicional de la CNBV si se recibe o entrega efectivo.
- [ ] Convenio con Banxico si se participa en el SPEI.
- [ ] Recursos de clientes segregados del patrimonio de la institución.

### Protección al usuario y transparencia

- [ ] Aviso expreso: los fondos no son depósitos ni están protegidos por el
  IPAB.
- [ ] Contratos de adhesión registrados ante CONDUSEF.
- [ ] Canales de atención y solución de controversias conforme a la LPDUSF.

### Restricciones de producto

- [ ] Las "recompensas" de la regla 40/30/20/10 estructuradas como pago por
  trabajo/servicios reales, nunca como rendimiento sobre saldos.
- [ ] Ningún producto de ahorro, inversión o crédito con recursos de clientes.

### Datos y tecnología

- [ ] Datos personales identificables off-chain con llave destruible
  (cumplimiento ARCO/LFPDPPP); on-chain solo datos seudonimizados.
- [ ] Programa de seguridad de la información conforme a las disposiciones
  CNBV vigentes.
- [ ] Definición fiscal (IVA/ISR) de emisión, transferencia y redención del
  token.

### Gobernanza del cumplimiento

- [ ] Asesoría legal especializada en regulación financiera contratada antes
  de iniciar el trámite.
- [ ] Auditoría externa del flujo completo (ya prevista en los criterios de
  aceptación del MVP de la Especificación) extendida a cumplimiento legal.

---

## 6. Referencias

- [Ley para Regular las Instituciones de Tecnología Financiera (texto
  vigente)](https://www.gob.mx/cms/uploads/attachment/file/834380/Ley_para_Regular_las_Instituciones_de_Tecnologia_Financiera.PDF)
  — arts. 22, 23, 30, 31, 58.
- [Circular 12/2018 del Banco de
  México](https://www.banxico.org.mx/marco-normativo/normativa-emitida-por-el-banco-de-mexico/circular-12-2018/{A6023AE0-8135-44ED-04DA-2068117ED5FD}.pdf)
  — operaciones de las IFPE, emisión en 3 segundos.
- Circular 4/2019 del Banco de México (modificada por Circular 37/2020) —
  prohibición de operaciones con activos virtuales al público para
  instituciones financieras.
- Comunicado conjunto SHCP/CNBV/Banxico (junio 2021) — los activos virtuales
  no son moneda de curso legal.
- [Disposiciones de carácter general aplicables a las ITF — análisis
  Deloitte](https://www2.deloitte.com/content/dam/Deloitte/mx/Documents/legal/2018/disposiciones-a-instituciones-de-tecnologia-financiera.pdf)
  — capitales mínimos (arts. 7 y 8 de las DCG).
- [Investigación y estudio de regulación comparada Fintech
  (BID)](https://publications.iadb.org/publications/spanish/document/Investigacion-y-estudio-de-regulacion-comparada---Fintech.pdf)
  — definición de fondos de pago electrónico y capitales mínimos.
- Documentos internos:
  - [Especificación del Inicio](./Especificacion.md) — secciones 5 (Gateway de
    Pagos) y 6 (Blockchain + Oráculo Financiero). La decisión pendiente #6
    ("Compliance KYC/AML, Fase 1") queda reclasificada por este documento como
    bloqueante previo a Fase 0.
  - [Marco de Gobernanza](./Gobernanza.md) — secciones 4 (registro inmutable)
    y 6 (marcas históricas), sujetas a la adaptación LFPDPPP descrita en 4.7.

---

## Notas de versión

**0.1.0 (2026-08-13):** Versión inicial. Establece el antecedente histórico de
la regulación mexicana de dinero electrónico, los dos caminos legales (fondo
de pago electrónico vs. activo virtual), la argumentación de por qué el token
del Altepetl es un fondo de pago electrónico por sustancia, y la lista de
requisitos legales para operarlo. Documento informativo; no sustituye asesoría
legal especializada.
