---
title: Capital inicial necesario del Altepetl
status: draft
version: 0.1.0
created: 2026-08-13
updated: 2026-08-13
---

# Capital inicial necesario del Altepetl

Este documento detalla **qué requiere dinero** para que el Altepetl arranque de
manera formal: constituir sus figuras jurídicas, cubrir los trámites y la
asesoría legal, montar la infraestructura técnica inicial y sostener la
operación hasta que el ciclo de captación, construcción y venta se
autosostenga.

Es el complemento financiero del [Marco Legal
Organizacional](./MarcoLegalOrganizacional.md): ese documento define **cuáles
figuras se constituyen y cómo se relacionan**; este define **cuánto cuesta
constituirlas y operarlas antes de que generen ingresos**.

La conclusión central: el capital inicial no es una sola bolsa, sino **dos** —
una para la A.C. donataria, financiada con donativos, y una para la empresa
comercial, financiada con capital social— y la categoría de gasto más grande no
es la constitución legal, sino la **infraestructura técnica y los sueldos del
runway inicial**.

Este documento es una estimación referencial basada en costos de mercado en
México (2025–2026), no una cotización formal. Las cifras deben validarse con
proveedores y despachos reales antes de tomar decisiones.

---

## 1. El orden de constitución define el flujo del dinero

Las dos entidades del Altepetl no se constituyen en paralelo: el dinero tiene
que entrar por alguna entidad primero, y solo la A.C. donataria puede recibir
donativos deducibles. La secuencia es:

```
1. A.C. donataria (entra primero: recibe donativos)
        │
        │  contrata / paga / financia
        ▼
2. Empresa comercial (se constituye después, Fase 2 del ciclo)
```

Antes de que la A.C. exista, los gastos los asumen los **fundadores** con
aportaciones personales (asesoría legal inicial, viáticos). Una vez constituida
la A.C. y obtenida su autorización como donataria, esta capta donativos y
financia el resto del arranque, incluida —cuando toque la Fase 2— la
constitución de la empresa comercial.

---

## 2. Presupuesto de constitución — A.C. donataria

La A.C. es la primera entidad y la más delicada: un error en sus estatutos
cuesta reformas caras. La asesoría legal para redactarlos es el gasto más
importante de toda esta fase.

| Concepto | Rango (MXN) | Nota |
|---|---|---|
| Asesoría legal para redactar estatutos compatibles con donataria | 15,000 – 40,000 | La asesoría más cara y crítica; define el objeto social, cláusulas del art. 82 LISR |
| Honorarios notariales (acta constitutiva) | 8,000 – 20,000 | Varía por estado y notaría |
| Derechos del Registro Público de la Propiedad | 2,000 – 5,000 | Inscripción del acta |
| Trámite de RFC + e.firma + CIEC (SAT) | 0 | Gratuito ante el SAT |
| Solicitud de autorización como donataria (Ficha 19/ISR) | 0 | El trámite del SAT es gratuito; el costo es la asesoría para prepararlo |
| **Subtotal constitución A.C.** | **25,000 – 65,000** | Sin contar CLUNI ni operación |

A partir de este punto, la A.C. puede **recibir donativos deducibles** y
financiar el resto del arranque.

---

## 3. Presupuesto de constitución — empresa comercial (S. de R.L. de C.V.)

La empresa comercial se constituye en la Fase 2, cuando el equipo técnico de la
A.C. ya ha generado el conocimiento que se va a productizar. Sus estatutos
requieren la **cláusula de propósito** (purpose lock) que la ata a la misión
del Altepetl, por lo que la asesoría legal no es trivial.

| Concepto | Rango (MXN) | Nota |
|---|---|---|
| Asesoría legal para estatutos con cláusula de propósito | 10,000 – 30,000 | Más barata que la A.C., pero necesita el purpose lock |
| Honorarios notariales | 8,000 – 18,000 | |
| Derechos del Registro Público de Comercio | ~2,500 | |
| Capital social mínimo (requisito legal) | 3,000+ | No hay mínimo legal fijo; debe ser "suficiente para los fines" |
| RFC + e.firma (SAT) | 0 | Gratuito |
| **Subtotal constitución empresa** | **20,000 – 50,000** | Sin contar el capital social real para operar |

### El capital social real no es el mínimo legal

El mínimo legal (~$3,000) no compra ni un servidor. La empresa necesita capital
real para comprar el hardware del centro de datos desde el día 1 y sostener su
operación hasta el primer cliente. Este capital social real es una categoría
aparte (sección 6).

---

## 4. Contratos y asesorías entre las dos entidades

Estos gastos no son de constitución, pero son **condición de operación** de la
arquitectura definida en el Marco Legal Organizacional. Sin ellos, la relación
entre la A.C. y la empresa es indefinida y vulnerable ante el SAT.

| Concepto | Rango (MXN) | Nota |
|---|---|---|
| Contrato de licencia de tecnología (A.C. → empresa) | 15,000 – 40,000 | Redacción cuidadosa: regalías a valor de mercado, no exclusividad, alineación con objeto social |
| Estudio de precios de transferencia | 20,000 – 60,000 | Sustenta que la regalía es a valor de mercado; defensa ante el SAT (art. 76 LISR) |
| Registro de marca ante el IMPI (opcional, recomendado) | 2,500 – 6,000 | Protege el nombre "Altepetl" en ambas figuras |
| CLUNI ante INDESOL (opcional) | 0 | Trámite gratuito; requiere asesoría si se busca acceso a programas federales |
| **Subtotal contratos y asesorías** | **37,500 – 106,000** | |

---

## 5. Operación inicial — sueldos y costos recurrentes

El runway inicial (cuántos meses de operación puede cubrir el capital antes de
que haya ingresos comerciales) es la categoría que más comúnmente se
subestima. Cada entidad paga su propia operación con su propia fuente.

### 5.1 La regla de las dos bolsas

| Entidad | Con qué paga su operación inicial |
|---|---|
| **A.C. donataria** | Con **donativos** (su fuente natural de ingresos) |
| **Empresa comercial** | Con su **capital social** (hasta que venda) y luego con sus ingresos |

No es un solo fondo: cada entidad tiene su propia tesorería y su propia
contabilidad.

### 5.2 Sueldos — la distinción administrativo vs. misional aplica desde el día 1

En la A.C., los sueldos del equipo técnico son **misionales** (fuera del 5% de
administración), pero los sueldos del contador, el abogado y la administración
**consumen el 5%**. Como los donativos iniciales probablemente sean modestos, el
5% puede ser un techo angosto. Se gestiona:

- **Externalizando contabilidad y legal** (pago por servicio, no nómina),
  documentado como gasto necesario.
- **Manteniendo la administración mínima viable**: un responsable administrativo
  a tiempo parcial, no un equipo completo.

### 5.3 Costos recurrentes estimados (mensual)

| Concepto | Rango (MXN/mes) | Entidad |
|---|---|---|
| Sueldos del equipo técnico (desarrollo) | 80,000 – 300,000+ | A.C. (misional, fuera del 5%) |
| Contador y legal externos | 5,000 – 15,000 | A.C. (administración, dentro del 5%) |
| Equipos de cómputo (amortización / reposición) | 5,000 – 15,000 | A.C. / empresa |
| Internet / servicios para desarrollo | 2,000 – 8,000 | A.C. (misional si es del centro de datos) |
| Espacio físico (si no es remoto) | 10,000 – 40,000 | A.C. / empresa |
| Sueldos del equipo comercial / operativo | 40,000 – 150,000+ | Empresa (cuando exista) |
| **Total recurrente mensual** | **142,000 – 528,000+** | Suma de ambas |

### 5.4 El runway

Si la empresa comercial tarda **6–12 meses** en tener su primer cliente, el
capital inicial debe cubrir los sueldos y costos de **ambas entidades** durante
todo ese período. Este es el componente más grande del capital inicial y el que
define la viabilidad del arranque.

---

## 6. Infraestructura técnica inicial — la categoría más grande

La `Especificacion.md` define tres proyectos técnicos iniciales. Cada uno tiene
costos, y el hardware es **lo que más dinero consume** en el arranque.

| Proyecto (según Especificación) | Rango (MXN, Fase 0) | En qué entidad vive |
|---|---|---|
| **Centro de datos** (hardware) | 100,000 – 1,000,000+ | Empresa comercial (dueña del hardware) |
| **Gateway de pagos** (desarrollo) | sueldos | A.C. (desarrollo misional) → empresa (operación) |
| **Blockchain + oráculo** (desarrollo) | sueldos | A.C. (desarrollo misional, solo gobernanza al inicio) |

El rango del centro de datos es enorme porque depende de la escala inicial:

- **Mínimo viable**: 2–3 servidores en rack propio, sin redundancia elaborada.
- **Serio**: racks completos, UPS, redundancia eléctrica, conexión de alta
  capacidad, climatización.

La regla de la arquitectura organizacional es clara: el **hardware** lo compra
la **empresa comercial** con su capital social; la A.C. solo aporta el
**conocimiento** (diseños, software, protocolos). Por eso el capital social real
de la empresa (sección 3) tiene que ser sustancial, no el mínimo legal.

---

## 7. Presupuesto consolidado

### 7.1 Por escenario

| Escenario | Constitución (A.C. + empresa) | Contratos + asesorías | Operación inicial (6 meses) | Hardware | **Total estimado** |
|---|---|---|---|---|---|
| **Mínimo viable** | ~$60,000 | ~$50,000 | ~$852,000 | ~$100,000 | **~$1,062,000** |
| **Medio** | ~$120,000 | ~$120,000 | ~$2,400,000 | ~$300,000 | **~$2,940,000** |
| **Ambicioso** | ~$150,000 | ~$150,000 | ~$4,800,000+ | ~$1,000,000+ | **~$6,100,000+** |

> Nota: los rangos de operación inicial (6 meses) se calculan del total
> recurrente mensual de la sección 5.3. La variabilidad es muy alta porque
> depende del tamaño del equipo y de la escala del centro de datos. Estas
> cifras son **referencias de orden de magnitud**, no cotizaciones formales.

### 7.2 Por entidad y fuente de financiamiento

| Entidad | Gasto inicial estimado | Fuente del dinero |
|---|---|---|
| **A.C. donataria** | Constitución + asesoría + sueldos técnicos + equipos + servicios | Donativos deducibles |
| **Empresa comercial** | Constitución + capital social real + hardware + sueldos comerciales | Capital social de los socios (y luego ingresos) |
| **Transversal** | Contratos entre ambas + estudio de precios de transferencia + marca | Se asigna según la fase (A.C. al inicio) |

---

## 8. Lo que NO requiere dinero (trámites gratuitos)

Para evitar sobreestimar, esto es lo que explícitamente **no cuesta**:

- Inscripción al RFC de cualquier persona moral (A.C. o empresa).
- Obtención de e.firma y CIEC ante el SAT.
- Solicitud de autorización como donataria (Ficha 19/ISR).
- Inscripción ante el IMSS.
- CLUNI ante INDESOL (trámite gratuito; el costo es la asesoría si se busca).

---

## 9. Supuestos y advertencias

- Los rangos son **referencias de mercado en México (2025–2026)**, verificadas
  en fuentes públicas pero no cotizadas con proveedores específicos.
- Los **sueldos** son el componente más variable y dependen del tamaño y
  seniority del equipo, y de si es remoto o presencial.
- El **hardware** del centro de datos es el segundo componente más variable y
  depende de la escala inicial.
- Los **honorarios notariales** varían por estado y notaría.
- Las **asesorías legales** varían drásticamente entre despachos generales y
  firmas especializadas en derecho fiscal y del tercer sector.
- Este documento **no sustituye** una cotización formal ni asesoría legal o
  contable. Es un marco de planeación.

---

## 10. Decisiones pendientes

| # | Decisión | Contexto |
|---|---|---|
| 1 | Escenario de arranque (mínimo viable / medio / ambicioso) | Define el monto total a captar |
| 2 | Tamaño y composición del equipo técnico inicial | Define el rubro más grande: sueldos |
| 3 | Escala del centro de datos en Fase 0 | Define el rubro de hardware |
| 4 | Remoto vs. presencial | Impacta costos de espacio físico |
| 5 | Runway objetivo (cuántos meses de operación cubre el capital inicial) | Típicamente 6–12 meses antes del primer cliente |
| 6 | Despacho legal / contador a contratar | Define el rango real dentro de los estimados |
| 7 | Si se busca CLUNI desde el inicio o se pospone | Impacta acceso a programas federales |

---

## 11. Referencias

- [Cómo constituir una asociación civil —
  Lawzana](https://lawzana.com/es/articles/mexico/como-constituir-una-asociacion-civil-en-mexico-paso-a-paso-515)
- [¿Cuánto cuesta un acta constitutiva? —
  EasyLex](https://contenido.easylex.com/cuanto-cuesta-un-acta-constitutiva)
- [Requisitos para crear una A.C. en México —
  Inicialove](https://www.inicialove.com/requisitos-para-crear-una-asociacion-civil-en-mexico/)
- [Donatarias Autorizadas — Trámites
  SAT](https://www.sat.gob.mx/minisitio/DonatariasAutorizadas/tramites_solicitudes.html)
- [Manual de Obligaciones de Donatarias — Chevez
  (PDF)](https://www.chevez.com/CRZ_documents/ManualObligaciones.pdf)
- [Sociedad mercantil — Ventanilla Única para
  Inversionistas](https://ventanillaunica.economia.gob.mx/procedure/555?l=es)
- [LISR Título II — Personas Morales
  (Justia)](https://mexico.justia.com/federales/leyes/ley-del-impuesto-sobre-la-renta/titulo-ii/)
- Documentos internos:
  - [Marco Legal Organizacional](./MarcoLegalOrganizacional.md) — define las dos
    entidades, la división de activos y los límites fiscales que este presupuesto
    respeta.
  - [Especificación del Inicio](./Especificacion.md) — los tres proyectos
    técnicos iniciales cuya infraestructura y desarrollo se presupuestan aquí.
  - [Marco Legal de la Blockchain](./LegalBlockchain.md) — encuadre del token;
    su autorización (CNBV/IFPE) es un costo posterior, no incluido en este
    presupuesto de arranque organizacional.

---

## Notas de versión

**0.1.0 (2026-08-13):** Versión inicial. Detalla el capital inicial necesario
para el arranque formal del Altepetl: constitución de la A.C. donataria y de la
empresa comercial, contratos y asesorías entre ambas, operación inicial
(sueldos y costos recurrentes), infraestructura técnica (centro de datos) y
presupuesto consolidado por escenario. Establece la regla de las dos bolsas
(A.C. financiada con donativos, empresa con capital social) y la distinción
administrativo vs. misional aplicada desde el día 1. Estimación referencial
basada en costos de mercado 2025–2026; no sustituye cotización formal ni
asesoría legal o contable.
