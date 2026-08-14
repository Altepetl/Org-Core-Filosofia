---
title: Marco legal organizacional del Altepetl
status: draft
version: 0.1.0
created: 2026-08-13
updated: 2026-08-13
---

# Marco legal organizacional del Altepetl

Este documento define la **arquitectura legal multi-entidad** del Altepetl: qué
figuras jurídicas se constituyen, quién es dueña de qué, cómo fluyen los fondos
entre ellas y cómo se mantiene la autorización fiscal de la organización sin
fines de lucro. Es el complemento natural del [Marco Legal de la
Blockchain](./LegalBlockchain.md): ese documento acota **qué exige la ley para
operar el token**; este acota **qué exige la ley para captar donativos, construir
y vender sin perder el carácter no lucrativo**.

La conclusión central: el Altepetl no puede operar como una sola entidad. Necesita
al menos **dos figuras coordinadas** —una donataria autorizada que capta donativos
y genera conocimiento de propósito civil, y una empresa comercial que productiza
y vende— unidas por contratos de licencia y una regla estricta de división de
activos.

Este documento es un análisis informativo, no asesoría legal. Antes de constituir
cualquier figura, el Altepetl debe contratar asesoría jurídica especializada en
derecho corporativo y fiscal de organizaciones civiles en México.

---

## 1. El problema que esta arquitectura resuelve

La [Filosofía](./Filosofia.md) define un objetivo amplio: crear una base
económica y social para la salud humana integral. Para alcanzarlo, la
organización necesita, desde el primer día, **un ciclo de captación, construcción
y venta**: recibir fondos, construir infraestructura técnica (centro de datos,
software, gateway de pagos) y monetizar parte de lo construido para sostener el
ciclo.

El obstáculo legal es directo: una **organización sin fines de lucro** (donataria
autorizada) **no puede vender productos o servicios comerciales** sin comprometer
su autorización. Y a la inversa, una **empresa comercial** no puede recibir
donativos deducibles de impuestos. Ninguna de las dos figuras por sí sola
resuelve el ciclo completo.

Este documento define cómo se combinan ambas para que el Altepetl pueda, de forma
legal y sostenible:

1. **Captar donativos deducibles** que financien la obra civil.
2. **Construir infraestructura técnica** con esos recursos.
3. **Vender productos y servicios de TI** derivados de esa obra.
4. **Reinvertir** los ingresos en el ciclo.

### Relación con los otros documentos

- La [Filosofía](./Filosofia.md) prevé crear múltiples instituciones: "El
  Altepetl creará las instituciones necesarias... Organizaciones, Empresas,
  Cooperativas, Sociedad civil, Asociación civil, Partido político" (sección
  Instituciones). Este documento opera esa previsión.
- La [Especificación del Inicio](./Especificacion.md) define los tres proyectos
  técnicos iniciales (centro de datos, gateway de pagos, blockchain). Este
  documento establece **en qué entidad jurídica vive cada activo** de esos
  proyectos.
- El [Marco Legal de la Blockchain](./LegalBlockchain.md) define el encuadre del
  token como fondo de pago electrónico. Este documento es **independiente y
  previo**: la arquitectura organizacional existe desde el día 0; la autorización
  financiera de la IFPE llega mucho después.

---

## 2. Las dos entidades del inicio

```
                         DONANTES
                            │
                            │ donativos deducibles
                            ▼
        ┌──────────────────────────────────────────────┐
        │  A.C. DONATARIA (capta fondos)              │
        │  Objeto: desarrollo social mediante          │
        │  tecnología de infraestructura civil         │
        │  NO factura servicios comerciales            │
        │  Genera: conocimiento, software, diseños,   │
        │  prototipos de propósito civil               │
        └────────────┬─────────────────────────────────┘
                     │ licencia de tecnología (regalías)
                     │ a valor de mercado
                     ▼
        ┌──────────────────────────────────────────────┐
        │  EMPRESA COMERCIAL TI (vende)                │
        │  S. de R.L. de C.V. — régimen general       │
        │  Toma el conocimiento de la A.C. y lo        │
        │  productiza:                                 │
        │   • Servicios de TI al mercado              │
        │   • Licenciamiento de software              │
        │   • Hosting / computación                   │
        │  Es dueña del hardware físico                │
        │  Genera: ingresos comerciales reales        │
        └──────────────────────────────────────────────┘
```

### 2.1 A.C. Donataria Autorizada

**Figura:** Asociación Civil (A.C.) sin fines de lucro, autorizada por el SAT
para recibir donativos deducibles del ISR conforme al Título III de la LISR
(artículos 79 y 82).

**Rol en el ciclo:** capta donativos y los destina a su actividad misional: el
diseño, desarrollo y construcción de tecnología de infraestructura civil de
propósito social.

**Qué genera:** conocimiento —software, arquitecturas, diseños, protocolos,
prototipos, know-how—. Todo ese conocimiento es **patrimonio de la A.C.** y se
destina a su objeto social.

**Qué NO hace:** no factura servicios comerciales, no vende hosting, no opera el
centro de datos como proveedor, no persigue lucro.

**Régimen fiscal:** no contribuyente del ISR (Título III, art. 79 LISR). Los
donativos que recibe son deducibles para el donante. Aplican las restricciones de
las donatarias autorizadas (sección 4).

### 2.2 Empresa Comercial de TI

**Figura:** Sociedad de Responsabilidad Limitada de Capital Variable (S. de R.L.
de C.V.) con régimen general de personas morales.

**Rol en el ciclo:** toma el conocimiento generado por la A.C. —licenciado bajo
contrato— y lo convierte en **productos y servicios vendibles** al mercado.

**Qué genera:** ingresos comerciales reales por venta de servicios de TI,
licenciamiento de software y, cuando aplique, hosting y computación.

**Qué es dueña:** del **hardware físico** del centro de datos (servidores, racks,
equipos de red) y de los activos comerciales derivados de su operación.

**Régimen fiscal:** régimen general, paga ISR a tasa corporativa, puede distribuir
utilidades a sus socios.

### 2.3 Por qué dos figuras y no una

Una sola entidad no puede cumplir el ciclo porque las dos naturalezas son
incompatibles en una misma persona moral:

| Naturaleza | Donataria autorizada | Empresa comercial |
|---|---|---|
| Finalidad | No lucrativa, objeto social autorizado | Lucrativa |
| Donativos deducibles | Sí | No |
| Venta de productos/servicios | No (compromete la autorización) | Sí |
| ISR | No contribuyente (Título III) | Régimen general |

Combinarlas en una sola entidad destruye una de las dos naturalezas: si la
donataria vende, pierde la autorización; si la empresa recibe donativos, estos
son ingreso acumulable. La arquitectura de dos entidades es **la única forma
coherente** de tener ambas capacidades.

---

## 3. División de activos: software vs. hardware

La regla más importante de esta arquitectura, y la que sostiene todo el modelo:

> **La A.C. genera conocimiento; la empresa comercial posee y opera el metal.**

Esta separación no es estética: es lo que mantiene a la donataria limpia de
cualquier apariencia de operación comercial. La razón es que licenciar software y
prestar servicios de infraestructura **no son lo mismo** para el SAT.

| Concepto | Software | Centro de datos / hosting |
|---|---|---|
| Naturaleza | Activo **intelectual** | Activo **físico + servicio continuo** |
| Licenciar / cobrar | Regalía (tratamiento fiscal limpio) | Servicio comercial típico |
| La A.C. "vende" algo | Licencia de uso | Servicios de infraestructura |
| Riesgo de verse como actividad comercial | Bajo | **Alto** |

### 3.1 Activos de la A.C. donataria

- Software propietario (código fuente, binarios).
- Diseños de arquitectura del centro de datos.
- Protocolos, especificaciones técnicas y know-how.
- Prototipos de referencia.
- Patentes y registros de propiedad industrial/intelectual, si los hubiera.

Estos activos son **intangibles** y **licenciables**: la A.C. puede autorizar su
uso a terceros —incluida la empresa comercial— mediante regalías, sin que eso
constituya actividad comercial. El licenciamiento de propiedad intelectual es un
ingreso compatible con el carácter no lucrativo, siempre que esté alineado con el
objeto social y se pacte a valor de mercado.

### 3.2 Activos de la empresa comercial

- Hardware físico del centro de datos (servidores, racks, equipos de red).
- Equipos de cómputo para el equipo técnico de la empresa.
- Contratos de servicios (internet, energía) para la operación del centro de
  datos.
- Activos comerciales derivados de la operación: cartera de clientes, contratos
  comerciales, marca comercial.

La empresa comercial **opera** el centro de datos físico y vende servicios de
hosting, computación y TI al mercado. Esa operación es por definición actividad
comercial y vive, por eso, en la figura que paga ISR en régimen general.

### 3.3 El contrato que las une: licencia de tecnología

La A.C. y la empresa comercial se vinculan mediante un **contrato de licencia de
tecnología**: la A.C. autoriza a la empresa a usar su software, diseños y
know-how, a cambio de una regalía.

Para que este contrato sostenga la arquitectura y no sea recalcificado por el
SAT como simulación, debe cumplir:

1. **Valor de mercado.** La regalía refleja lo que un tercero independiente
   pagaría por la misma tecnología. Precios de transferencia entre partes
   relacionadas (art. 76 LISR).
2. **No exclusividad.** La licencia no es exclusiva: la A.C. puede licenciar la
   misma tecnología a otras partes, y de hecho la usa para su propio objeto social
   (los Calpullis, los proyectos civiles).
3. **Alineación con el objeto social.** El licenciamiento es un medio de escalar
   el impacto de la tecnología civil, no un mecanismo para bombear utilidad
   comercial hacia la donataria.
4. **Documentación rigurosa.** Contrato formal, facturación, registros
   contables separados y reporte de operaciones con partes vinculadas (regla
   3.10.1.15 de la RMF, informe mensual sin importar monto).

---

## 4. Régimen fiscal de la donataria: restricciones que el diseño debe respetar

La A.C. donataria opera bajo un régimen restrictivo. Cualquier desviación
compromete la autorización y, con ella, toda la arquitectura. Estos son los
límites que el diseño organizacional respeta por construcción.

### 4.1 Límite del 5% de gastos de administración

Las donatarias pueden destinar a gastos de administración **como máximo el 5%**
de los donativos y sus rendimientos (art. 138 del Reglamento de la LISR). Son
gastos de administración los que se efectúan en relación directa con las oficinas
o actividades administrativas.

**No** se consideran gastos de administración —y por tanto **no** consumen el
5%— los gastos **directamente destinados al cumplimiento del objeto social**.
Esta es la distinción que sostiene el modelo:

| Gasto | ¿Entra en el 5%? | Por qué |
|---|---|---|
| Sueldos del equipo técnico que construye software e infraestructura | No | Actividad misional directa |
| Sueldos del equipo administrativo (contabilidad, legal, dirección no técnica) | Sí | Back-office |
| Equipo de cómputo para el equipo técnico | No | Insumo operativo misional |
| Equipo de cómputo para administración | Sí | Administración |
| Internet para el centro de datos / servidores | No | Insumo de la infraestructura misional |
| Internet de la oficina administrativa | Sí | Administración |
| Renta del espacio físico del centro de datos | No | Es la obra misional misma |
| Renta de oficina administrativa | Sí | Administración |

La inmensa mayoría del gasto inicial de la A.C. —sueldos técnicos, equipos,
infraestructura— queda **fuera** del 5%, porque es actividad misional directa.
El 5% solo consume contabilidad, legal y administración real.

**Condición crítica:** para que el SAT clasifique los sueldos técnicos como
misionales y no como administración, el **objeto social del acta constitutiva**
 debe decir explícitamente que diseñar, desarrollar y construir tecnología de
 infraestructura civil **es la actividad misional** de la organización.

### 4.2 Límite del 50% de ingresos por actividades no relacionadas

Las donatarias pueden obtener ingresos por actividades distintas a su objeto
social, pero si estos superan el **50%** de sus ingresos totales en el ejercicio,
**pierden la autorización** (art. 80 LISR).

Hay un segundo umbral: si los ingresos por actividades no relacionadas superan el
**10%**, la donataria debe calcular y pagar ISR sobre el excedente, pero
**conserva la autorización**. Es decir:

| Umbral | Consecuencia |
|---|---|
| Ingresos no relacionados ≤ 10% | Sin ISR adicional, autorización intacta |
| Ingresos no relacionados entre 10% y 50% | ISR sobre el excedente, autorización intacta |
| Ingresos no relacionados > 50% | **Pérdida de la autorización** |

**Implicación para la arquitectura:** si la A.C. tuviera participación accionaria
en la empresa comercial, los dividendos que recibiera se computarían como
ingresos por actividades no relacionadas y alimentarían el umbral del 50%. La
participación, por tanto, debe ser **minoritaria y moderada** (sección 6).

### 4.3 Destino exclusivo de los activos

Las donatarias deben destinar sus activos **exclusivamente** a los fines propios
de su objeto social. No pueden otorgar beneficios sobre el remanente distribuible
a personas físicas o a sus propios integrantes, salvo pago real por servicios
recibidos. Al liquidarse o perder la autorización, deben transmitir la totalidad
de su patrimonio a otra donataria autorizada.

**Implicación:** la tecnología que la A.C. genera es patrimonio civil. No puede
ser transferida a la empresa comercial por debajo de su valor, ni cedida en
perjuicio del objeto social.

### 4.4 Lo que la donataria NO puede hacer con el centro de datos

Esta es la lista de opciones descartadas para el uso del centro de datos físico,
por orden de riesgo fiscal:

| Opción | Veredicto | Razón |
|---|---|---|
| La empresa es dueña del hardware y lo opera | ✅ Recomendada | La A.C. nunca opera infraestructura como servicio |
| La A.C. es dueña del hardware y lo arrienda a la empresa | 🟡 Posible, con riesgo medio | Requiere valuación a valor de mercado; riesgo de recalcificación |
| La A.C. cobra "cuota de recuperación" a la empresa | ❌ Descartada | La reforma 2023 limita las cuotas a los beneficiarios del objeto social, no a empresas comerciales |
| La A.C. presta "servicios de hosting" a la empresa | ❌ Descartada | Actividad comercial por definición; causal directa de revocación (art. 82 Quater LISR) |
| Tercera entidad (fideicomiso o segunda empresa) | 🔵 Futuro | Solo cuando la escala lo justifique |

La arquitectura definida en este documento usa la **opción recomendada**: la
empresa comercial es dueña del hardware y lo opera. La A.C. aporta solo el
conocimiento, que es limpio de licenciar.

### 4.5 Cuotas de recuperación: la reforma 2023

Las cuotas de recuperación son montos que una donataria puede cobrar **sin** que
se consideren ingresos por actividades no relacionadas. Pero desde la reforma
fiscal 2023, están expresamente limitadas:

> No se considerarán cuotas de recuperación los montos que cobren por la
> enajenación de bienes o la prestación de servicios a las personas o grupos
> distintos a los señalados en su objeto social autorizado.

La empresa comercial **no es** un beneficiario del objeto social asistencial de
la A.C. Cobrarle cuota de recuperación al brazo comercial propio es exactamente el
escenario que el SAT cerró. Por eso esta opción está descartada.

---

## 5. Objeto social sugerido para la A.C. donataria

El objeto social del acta constitutiva es prácticamente inamovible una vez
protocolizado. Redactarlo bien desde el inicio es la decisión más importante de
todo el proceso de constitución.

El objeto social debe lograr tres cosas simultáneamente:

1. **Encajar en una fracción autorizable** del art. 82 LISR (para que el SAT
   conceda la autorización de donativos deducibles).
2. **Convertir la construcción de tecnología en actividad misional** (para que
   los sueldos técnicos queden fuera del 5% de administración).
3. **Cerrar la puerta a actividades comerciales** (para que la venta de servicios
   quede claramente fuera de la donataria y viva en la empresa).

### 5.1 Fracción autorizable recomendada: Desarrollo Social

La fracción que mejor encaja con el propósito del Altepetl es **Desarrollo
Social** (art. 82 LISR), por dos razones:

- Encaja con el objetivo filosófico de mejorar las condiciones materiales de la
  comunidad (Filosofía, sección Objetivo: "Mejorar las condiciones materiales del
  grupo social").
- No requiere autorización adicional de autoridades estatales (a diferencia de la
  fracción Asistencial, que requiere reconocimiento del SNDIF o la DGBCS).

La fracción **Asistencial** puede añadirse más adelante, cuando haya obra
asistencial directa en territorio (salud, alimentación, vivienda), alineada con
la prioridad filosófica "aire, agua, alimento" (Filosofía, sección Valores).

### 5.2 Borrador de objeto social

> Constituye su objeto social la realización de actividades de desarrollo social
> mediante el diseño, desarrollo, construcción y mantenimiento de infraestructura
> tecnológica civil —incluyendo software, redes, protocolos y sistemas de
> información— destinada al apoyo de comunidades y al cumplimiento de los fines
> de la organización; así como la captación de recursos y donativos para tal
> fin. La asociación no realiza actividades comerciales ni lucrativas y destinará
> la totalidad de su patrimonio al cumplimiento de su objeto.

Elementos clave de esta redacción:

- **"mediante el diseño, desarrollo, construcción y mantenimiento de
  infraestructura tecnológica civil"** — convierte la construcción técnica en obra
  misional, no administrativa.
- **"actividades de desarrollo social"** — la enmarca en una fracción autorizable.
- **"no realiza actividades comerciales ni lucrativas"** — cierra la puerta a la
  venta de servicios dentro de esta figura.

### 5.3 Cláusulas estatutarias obligatorias

El acta constitutiva debe incluir, además del objeto social, las cláusulas que
exige el art. 82, fracciones XIV y XV de la LISR:

- **No distribución de utilidades.** La asociación no distribuye remanentes entre
  sus asociados.
- **Destino del patrimonio en disolución.** En caso de liquidación o pérdida de
  la autorización, la totalidad del patrimonio se transmite a otra donataria
  autorizada.
- **Destino exclusivo al objeto social.** Todos los activos se destinan a los
  fines propios del objeto.

---

## 6. Propiedad y coordinación entre las dos entidades

La pregunta operativa es **quién es dueño de la empresa comercial** y cómo se
mantiene la alineación con la misión del Altepetl sin comprometer la autorización
de la donataria. Hay tres opciones, con perfiles distintos.

### 6.1 Opción A — La A.C. es accionista mayoritaria de la empresa

La A.C. controla la empresa comercial por mayoría de capital.

- ✅ Centraliza el control estratégico en la figura no lucrativa.
- ⚠️ Los dividendos que la empresa pague a la A.C. se computan como ingresos por
  actividades no relacionadas y alimentan el umbral del 50%. Si los dividendos
  son altos, comprometen la autorización.
- **Recomendada si** la utilidad de la empresa se reinvierte mayoritariamente en
  su propio crecimiento y solo sube dividendos moderados a la A.C.

### 6.2 Opción B — Propiedad separada

La A.C. y la empresa comercial tienen socios distintos, pero alineados por la
misión del Altepetl. Se coordinan por contratos.

- ✅ Cero riesgo de contaminar la autorización de la donataria.
- ✅ Máxima flexibilidad comercial.
- ⚠️ Requiere acuerdos de coordinación fuertes: contratos de licencia, servicios,
  transferencia tecnológica, gobernanza compartida.
- **Recomendada si** se quiere máxima libertad comercial y el control de la
  misión se hace por gobernanza y contratos, no por propiedad.

### 6.3 Opción C — Híbrido con participación minoritaria (recomendada)

La A.C. tiene una **participación minoritaria** en la empresa comercial (típicamente
20–30%), suficiente para influir en la dirección estratégica, pero los dividendos
que recibe se mantienen muy por debajo del umbral del 50%.

- ✅ Control estratégico sin riesgo fiscal.
- ✅ La empresa retiene la mayoría de su utilidad para crecer.
- ✅ Es el equilibrio entre misión y sostenibilidad; es el modelo que usan las
  OSC profesionales en México.
- **Recomendada para el Altepetl** como configuración inicial.

### 6.4 Cláusula de propósito ("purpose lock") en la empresa

Sea cual sea la opción de propiedad, los estatutos de la empresa comercial deben
incluir una **cláusula de propósito** que la ate a la misión del Altepetl e
impida su desvío. Esta cláusula define:

- El objeto de la empresa está subordinado al cumplimiento de la misión del
  Altepetl.
- La utilidad se reinvierte prioritariamente en crecimiento y en el apoyo a la
  A.C. donataria.
- Cualquier cambio de control o reforma del objeto requiere la aprobación de la
  A.C. (aunque sea minoritaria), como mecanismo de veto estratégico.

Esta cláusula es la **traducción legal** del principio filosófico de que el
Altepetl no persigue lucro como fin, sino como medio de sostenibilidad.

---

## 7. El ciclo completo, fase por fase

La arquitectura definida permite operar el ciclo de captación, construcción y
venta que el Altepetl necesita, en cinco fases.

### Fase 0 — Arranque

La A.C. donataria se constituye, obtiene su RFC, e.firma y la autorización del
SAT como donataria. Capta los donativos iniciales. Con esos recursos paga los
sueldos del equipo técnico —actividad misional, fuera del 5%— y adquiere los
equipos e insumos necesarios para diseñar la arquitectura del centro de datos y
desarrollar el software base.

### Fase 1 — Construcción

El equipo técnico, pagado por la A.C., desarrolla los activos intangibles:
software, protocolos, diseños del centro de datos, know-how. Todo ese
conocimiento es **patrimonio de la A.C.** y se destina a su objeto social.

### Fase 2 — Productización

Se constituye la **empresa comercial** (S. de R.L. de C.V.). La A.C. le licencia
su tecnología bajo contrato, a valor de mercado y con cláusula de no
exclusividad. La empresa compra el hardware físico con su capital y opera el
centro de datos.

### Fase 3 — Venta

La empresa comercial vende al mercado: servicios de TI, licenciamiento de
software, hosting y computación. Paga ISR en régimen general, como cualquier
empresa.

### Fase 4 — Reinversión

La utilidad de la empresa se reinvierte mayoritariamente en su crecimiento. Solo
sube dividendos moderados a la A.C. (por debajo del umbral del 50%, idealmente
≤10% para no pagar ISR adicional sobre el excedente).

### Fase 5 — Bucle

La A.C. usa los nuevos recursos —donativos + regalías + dividendos moderados—
para construir la siguiente ola de infraestructura y tecnología. La empresa
comercial la productiza y vende. El ciclo se autosostiene.

---

## 8. Lista de requisitos

Checklist consolidado para constituir y operar la arquitectura. Los items
marcados **[Bloqueante Fase 0]** impiden captar el primer donativo o constituir
la base; los demás son condiciones de operación continua.

### A.C. donataria

- [ ] **[Bloqueante Fase 0]** Validar con abogado corporativo y contador
  autorizado la viabilidad del objeto social y las cláusulas estatutarias antes
  de redactar el acta.
- [ ] **[Bloqueante Fase 0]** Redactar el acta constitutiva con objeto social
  autorizable (Desarrollo Social), cláusula de no distribución de utilidades y
  destino del patrimonio en disolución (art. 82 fr. XIV y XV LISR).
- [ ] **[Bloqueante Fase 0]** Constituir la A.C. ante notario e inscribirla en el
  Registro Público de la Propiedad.
- [ ] **[Bloqueante Fase 0]** Inscribir la A.C. en el RFC (ALSC del SAT) y
  obtener e.firma y Contraseña (CIEC) de la persona moral.
- [ ] **[Bloqueante Fase 0]** Activar el Buzón Tributario y emitir opinión de
  cumplimiento positiva.
- [ ] **[Bloqueante Fase 0]** Preparar el expediente de demostración de
  actividades reales (infraestructura tecnológica civil).
- [ ] **[Bloqueante Fase 0]** Presentar la solicitud de autorización como
  donataria (Ficha 19/ISR del Anexo 2 de la RMF) vía Buzón Tributario.
- [ ] **[Bloqueante Fase 0]** (Opcional, futuro) Inscripción al Registro Federal
  de OSC (INDESOL).
- [ ] Separación contable estricta entre gastos de administración (≤5%) y gastos
  misionales, desde el día 1.
- [ ] Documentación misional de cada gasto técnico (vínculo con proyecto de
  infraestructura, no "gestión general").

### Empresa comercial

- [ ] Constituir la S. de R.L. de C.V. con estatutos que incluyan la cláusula de
  propósito (purpose lock) atada a la misión del Altepetl.
- [ ] Definir la estructura de propiedad: Opción C (participación minoritaria de
  la A.C.) como configuración inicial recomendada.
- [ ] Inscribir la empresa en el RFC, obtener e.firma y CIEC.
- [ ] La empresa es dueña del hardware físico del centro de datos desde el
  inicio; la A.C. nunca adquiere hardware como activo suyo.

### Contrato de licencia entre A.C. y empresa

- [ ] **[Bloqueante para Fase 2]** Contrato de licencia de tecnología formal:
  regalías a valor de mercado, no exclusividad, alineación con el objeto social
  de la A.C.
- [ ] Estudio de precios de transferencia que sustente el valor de la regalía
  (art. 76 LISR).
- [ ] Reporte mensual de operaciones con partes vinculadas (regla 3.10.1.15 RMF).

### Gobernanza del cumplimiento

- [ ] Asesoría legal especializada en derecho corporativo y fiscal de OSC
  contratada antes de redactar el acta constitutiva.
- [ ] Contador público autorizado para la dictaminación fiscal anual.
- [ ] Auditoría interna periódica de la separación entre A.C. y empresa
  comercial.

---

## 9. Decisions pendientes

Este documento es draft y deja explícitamente abiertas las siguientes decisiones:

| # | Decisión | Contexto |
|---|---|---|
| 1 | Figura societaria exacta de la empresa comercial | S. de R.L. de C.V. recomendada; confirmar con asesoría legal |
| 2 | Porcentaje de participación de la A.C. en la empresa comercial | Opción C recomendada (20–30%); definir el tope exacto de dividendos para no acercarse al umbral del 50% |
| 3 | Fracción autorizable única o múltiple | Desarrollo Social como inicial; evaluar añadir Asistencial cuando haya obra en territorio |
| 4 | Modelo de licencia de tecnología | Regalía porcentual vs. tarifa fija; definir con estudio de precios de transferencia |
| 5 | Estructura del purpose lock en los estatutos de la empresa | Redacción exacta del veto estratégico de la A.C. |
| 6 | Si la A.C. entra al Registro Federal de OSC (INDESOL) | Beneficios (acceso a programas federales) vs. carga administrativa |

---

## 10. Referencias

- [Ley del Impuesto sobre la Renta — Título III
  (Justia)](https://mexico.justia.com/federales/leyes/ley-del-impuesto-sobre-la-renta/titulo-iii/)
  — arts. 79 (no contribuyentes), 80 (umbrales), 82 (requisitos de donatarias),
  82 Quater (causales de revocación).
- [Art. 79 LISR — SDV Compendio](https://sdv.com.mx/compendio/ley-isr/articulo-79/)
- [Reglamento de la LISR — art. 138 (gastos de administración)
  Cámara de Diputados](https://www.diputados.gob.mx/LeyesBiblio/regley/Reg_LISR_060516.doc)
- [Donatarias Autorizadas — Portal
  SAT](https://www.sat.gob.mx/minisitio/DonatariasAutorizadas/index.html)
- [Trámites y solicitudes — Donatarias (Ficha
  19/ISR)](https://www.sat.gob.mx/minisitio/DonatariasAutorizadas/tramites_solicitudes.html)
- [Ficha 43/CFF — Inscripción al RFC de Personas
  Morales](https://www.sat.gob.mx/gobmx/Paginas/Ficha_43_cff.html)
- [Actividades autorizables para recibir donativos
  deducibles — gob.mx/SAT](https://www.gob.mx/sat/acciones-y-programas/actividades-que-pueden-ser-autorizadas-para-recibir-donativos-deducibles)
- [Ingresos de las donatarias — Consultorio Fiscal
  UNAM](https://consultoriofiscal.unam.mx/articulo.php?id_articulo=1211)
- [Fiscalización de partes relacionadas en donatarias
  autorizadas — Veritas](https://www.veritas.org.mx/Impuestos/Fiscal/Fiscalizacion-de-partes-relacionadas-en-donatarias-autorizadas)
- [Donatarias Autorizadas y cuotas de recuperación
  2023 — JPA México](https://www.jpamexico.com/noticia.php?id=190)
- [Identifica correctamente los gastos administrativos
  — Ramtav](https://ramtav.com/identifica-correctamente-los-gastos-administrativos-para-no-rebasar-el-5-marcado-por-la-lisr-y-mantener-tu-organizacion-saludable)
- [Donatarias. Limitantes fiscales — El
  Conta](https://elconta.mx/limitantes-fiscales-funcionamiento-donatarias/)
- [Manual de Obligaciones de Donatarias — Chevez Ruiz Zamarripa
  (PDF)](https://www.chevez.com/CRZ_documents/ManualObligaciones.pdf)
- [Régimen Fiscal Donatarias — RSM México
  (PDF)](https://rsmmx.mx/docs/Regimen-Fiscal-Donatarias-Autorizadas.pdf)
- [Manual Fiscal de Donatarias Autorizadas — ProBono México 2022
  (PDF)](https://www.probono.mx/wp-content/uploads/2022/04/PROBONOMX-Manual_Fiscal_de_Donatarias_Autorizadas-06abr22_VF-3.pdf)
- [Obligaciones fiscales y antilavado de donatarias
  — Basham](https://basham.com.mx/obligaciones-fiscales-y-en-materia-de-antilavado-aplicables-a-donatarias-autorizadas/)
- [Reforma fiscal 2021 para donatarias (art. 80 LISR)
  — Samanos SC](https://www.samanosc.com.mx/post/reforma-fiscal-2021-para-donatarias-autorizadas-para-recibir-donativos-deducibles-del-isr)
- [Precios de transferencia: operaciones entre partes
  relacionadas — Auren México](https://auren.com/mx/blog/precios-de-transferencia-operaciones-entre-partes-relacionadas/)
- Documentos internos:
  - [Filosofía](./Filosofia.md) — sección Instituciones (creación de múltiples
    figuras) y sección Valores (prioridad aire, agua, alimento).
  - [Especificación del Inicio](./Especificacion.md) — los tres proyectos
    técnicos iniciales y la distribución de sus activos entre las dos entidades.
  - [Capital Inicial Necesario](./CapitalInicialNecesario.md) — presupuesto de
    arranque que este marco hace operable: cuánto cuesta constituir y operar las
    dos entidades antes de que el ciclo se autosostenga.
  - [Marco Legal de la Blockchain](./LegalBlockchain.md) — encuadre del token
    como fondo de pago electrónico; independiente y posterior a esta arquitectura.

---

## Notas de versión

**0.1.0 (2026-08-13):** Versión inicial. Define la arquitectura legal
multi-entidad del Altepetl: la A.C. donataria que capta donativos y genera
conocimiento civil, y la empresa comercial que productiza y vende. Establece la
regla de división de activos (software en la A.C., hardware en la empresa), los
límites fiscales que el diseño respeta (5% de administración, 50% de actividades
no relacionadas, destino exclusivo de activos), el objeto social sugerido
(Desarrollo Social), las opciones de propiedad entre las dos entidades (Opción C
recomendada), el ciclo completo en cinco fases y la lista de requisitos.
Documento informativo; no sustituye asesoría legal especializada.
