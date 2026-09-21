---
title: Consulta pública de donaciones del Altepetl
status: draft
version: 0.1.0
created: 2026-09-21
updated: 2026-09-21
---

# Consulta pública de donaciones del Altepetl

Este documento define cómo el Altepetl cumple su compromiso de transparencia en
la captación de donativos. La Filosofía lo establece como principio: **el
Altepetl no prohíbe, documenta** (Filosofía, sección "Registro en lugar de
prohibición"). La misma lógica aplica al dinero: cada donativo recibido se
registra, se concilia y se pone a disposición del público.

**Estado actual: el registro público de donaciones está en construcción.**
No existe aún un sistema automatizado de consulta. Mientras tanto, la
transparencia opera por **conciliación manual mensual** de los depósitos
recibidos (sección 1). La sección 2 define todo lo necesario para construir el
sistema automatizado de consulta.

**Advertencia importante:** el Altepetl **aún no tiene registro legal**. No
existe la A.C. donataria prevista en el [Marco Legal
Organizacional](./MarcoLegalOrganizacional.md); el RFC, la autorización del SAT
como donataria y la contabilidad formal son pasos posteriores. Eso condiciona
el alcance de las obligaciones legales (sección 3): hoy la publicación es un
**compromiso voluntario**, no un mandato de ley.

Este documento es informativo y no constituye asesoría legal. Las obligaciones
descritas en la sección 3 deben validarse con asesoría jurídica especializada
cuando se constituya la organización.

---

## 1. Primera etapa — Conciliación manual mensual

Mientras no exista sistema automatizado, la transparencia se garantiza con un
proceso manual, simple y verificable, ejecutado **una vez al mes**.

### 1.1 Qué se concilia

Todos los depósitos recibidos en las cuentas y canales de captación definidos
en el sitio público (transferencia SPEI en México, ACH/Wire en Estados Unidos,
SEPA en Europa):

```
  Depósitos del mes  ──►  Estado de cuenta bancario
        │                        │
        │                        ▼
        │               Registro manual de donativos
        │               (fecha, monto, canal, referencia)
        ▼                        ▼
  Comprobantes del donante ──►  Conciliación
                                (¿cada depósito tiene
                                 registro y viceversa?)
                                     │
                                     ▼
                          Publicación mensual consolidada
```

### 1.2 Procedimiento mensual

1. **Descargar los estados de cuenta** de todas las cuentas y canales al cierre
   de cada mes.
2. **Registrar cada depósito** en la tabla de donativos con: fecha, monto,
   moneda, canal (SPEI / ACH / SEPA / otro), referencia o concepto del
   depósito, y un identificador consecutivo único.
3. **Cotejar contra los comprobantes** que los donantes hayan enviado por los
   medios de contacto públicos, cuando existan.
4. **Conciliar**: verificar que cada depósito del estado de cuenta tenga su
   fila en el registro y que cada fila del registro corresponda a un depósito
   real. Todo depósito sin origen identificado se marca como **pendiente de
   aclaración** y se reporta así —no se oculta ni se descarta.
5. **Publicar el consolidado del mes** en el sitio público del Altepetl:
   número de donativos, monto total por canal, monto acumulado del ejercicio y
   la lista de depósitos con fecha, monto y referencia. Por defecto la lista
   **no publica datos personales** del donante (ver 1.3).
6. **Resguardar la evidencia**: los estados de cuenta y la tabla de conciliación
   se conservan en el repositorio interno del Altepetl, listos para su consulta
   y para la futura contabilidad formal.

### 1.3 Privacidad del donante

- La publicación es **por defecto anónima**: fecha, monto, canal y referencia.
- Si el donante desea aparecer con su nombre, se publica **solo con su
  consentimiento expreso**, registrando ese consentimiento por escrito.
- Los datos de contacto o identificación del donante nunca se publican.

### 1.4 Responsable y periodicidad

- **Frecuencia:** mensual, dentro de los primeros 10 días naturales del mes
  siguiente al periodo conciliado.
- **Responsable:** la persona que la gobernanza asigne a la tesorería del
  Altepetl mientras no exista la entidad legal.
- **Rendición:** el consolidado publicado indica fecha de conciliación y
  responsable que la ejecutó.

### 1.5 Límites de esta etapa

- La conciliación manual **no expide comprobantes fiscales** (CFDI por
  donativos): eso solo es posible una vez constituida la A.C. donataria con su
  RFC y autorización. La política de comprobantes se define en
  [Política de comprobantes de donación](./PoliticasComprobanteDonacion.md).
- Los donativos recibidos hoy **no son deducibles de impuestos** para el
  donante, porque no existe la donataria autorizada. El sitio público debe
  decirlo explícitamente.
- El registro manual es insumo, no sustituto, de la contabilidad formal que
  exigirá la ley una vez constituida la organización (sección 3).

---

## 2. Segunda etapa — Sistema automatizado de consulta

El objetivo final es que cualquier persona pueda consultar, en línea y en
cualquier momento, las donaciones recibidas. Esta sección inventaría lo
necesario para construirlo.

### 2.1 Requisitos de datos y procesos

| # | Requisito | Descripción |
|---|---|---|
| 1 | Captación con identificador único | Cada donativo genera un identificador desde el momento del depósito (referencia de pago asignada por canal o folio generado al donar) |
| 2 | Descarga automática de estados de cuenta | Conexión con los bancos (API bancaria, open finance, o exportación programada de estados de cuenta) para los tres canales: México, EU, Europa |
| 3 | Conciliación automática | Software que cruce depósitos bancarios contra el registro de donativos sin intervención manual, con reglas para depósitos sin referencia |
| 4 | Base de datos central | Registro normalizado: fecha, monto, moneda, canal, referencia, estatus (conciliado / pendiente de aclaración), destino del recurso |
| 5 | Registro del uso y destino | Además del ingreso, registrar en qué se gasta cada peso, para cumplir la obligación de publicar uso y destino (sección 3.2) |
| 6 | Resguardo y respaldo | Historial íntegro, respaldado y auditable; sin borrado silencioso |
| 7 | Verificabilidad | Firma digital o hash de cada publicación mensual, para que el historial público sea verificable contra alteraciones |

### 2.2 Requisitos de la interfaz pública

- **Portal de consulta en el sitio público** (ES y EN, como todo el contenido
  del Altepetl) con: total del ejercicio, desglose por mes y por canal, y
  lista de depósitos con fecha, monto y referencia.
- **Consulta por referencia:** que el donante pueda buscar su propio depósito
  con la referencia con la que donó, sin exponer datos personales.
- **Descarga abierta:** los datos consolidados en formatos abiertos (CSV/JSON).
- **Publicación por defecto anónima**, igual que la etapa manual (1.3).

### 2.3 Requisitos técnicos de infraestructura

El sistema debe alojarse en la infraestructura propia definida en la
[Especificación del Inicio](./Especificacion.md):

- Alojamiento en el **centro de datos** del Altepetl (o en infraestructura
  provisional mientras este existe).
- Integración con el **gateway de pagos** para la captación con identificador
  único desde el origen.
- A futuro, anclaje en la **blockchain + oráculo financiero** como capa de
  verificación pública, sujeto al encuadre legal del token
  ([Marco Legal de la Blockchain](./LegalBlockchain.md)).

### 2.4 Requisitos legales y de protección de datos

Antes de publicar datos de donativos en un sistema en línea:

1. **Fundamento legal de la publicación.** Con la A.C. constituida, la
   publicación del uso y destino de los donativos pasa de compromiso
   voluntario a **obligación legal** (art. 82, fracción III, LISR; sección
   3.2 de este documento). El sistema debe satisfacer esa obligación por
   diseño.
2. **Protección de datos personales.** Cualquier dato del donante que se
   almacene queda sujeto a la Ley Federal de Protección de Datos Personales en
   Posesión de los Particulares: aviso de privacidad, mínimo dato necesario,
   consentimiento para publicar nombres.
3. **Antilavado (LFPIORPI).** La recepción de donativos es actividad
   vulnerable; los montos y umbrales de reporte deben validarse con asesoría
   legal y reflejarse en los controles del sistema.
4. **Comprobantes fiscales.** El sistema debe poder expedir CFDI con
   complemento de donativos una vez exista la donataria autorizada.

### 2.5 Requisitos organizativos previos

Este sistema no puede operar en su forma completa sin:

- La **constitución de la A.C. donataria** (RFC, e.firma, autorización del
  SAT) — ver [Marco Legal Organizacional](./MarcoLegalOrganizacional.md),
  Fase 0.
- Una **política formal de privacidad** aprobada por la gobernanza.
- Un **responsable designado** de la integridad del sistema y de la
  conciliación mensual automática.

### 2.6 Criterio de migración

La migración de la etapa manual a la automatizada no borra la etapa 1: los
registros conciliados manualmente se importan al sistema automatizado como
historial base, con su estatus de origen documentado.

---

## 3. Marco legal: a qué estamos obligados

### 3.1 Situación actual: sin registro legal

El Altepetl **no existe todavía como persona jurídica**. Consecuencias:

- **No hay obligación legal vigente** de publicar donativos: las obligaciones
  de transparencia fiscal aplican a la donataria autorizada, que no existe.
- La publicación mensual descrita en la sección 1 es un **compromiso
  voluntario** del Altepetl, coherente con su Filosofía, y la mejor prueba de
  seriedad frente a los donantes.
- Los donativos actuales los reciben **personas físicas fundadoras** en cuentas
  personales, y no son deducibles. El Marco Legal Organizacional prevé que la
  A.C. se constituye con aportaciones y donativos iniciales (Capital Inicial
  Necesario, sección 1); el registro manual de la sección 1 es precisamente el
  historial que permitirá documentar ese origen de recursos al constituirse.
- Por prudencia, los fondos recibidos antes de la constitución deben
  registrarse con especial rigor: son el antecedente que la futura
  contabilidad y el SAT revisarán.

### 3.2 Obligaciones al constituir la A.C. donataria autorizada

Una vez constituida y autorizada la donataria, estas son las obligaciones
identificadas. **Todas requieren validación de asesoría legal especializada**;
esta tabla es un mapa, no asesoría definitiva.

| Obligación | Fundamento | Plazo / periodicidad |
|---|---|---|
| Expedir CFDI con complemento de donativos por cada donativo | LISR art. 82; CFF arts. 29 y 29-A | Al recibir cada donativo |
| Declaración anual de ingresos y erogaciones | LISR (donatarias autorizadas) | A más tardar el 15 de febrero de cada año |
| Declaración informativa de transparencia: uso y destino de los donativos y patrimonio | LISR art. 82, fracción III | Anual, en mayo |
| **Mantener a disposición del público**: la autorización, el uso y destino de los donativos y el cumplimiento de obligaciones fiscales | LISR art. 82, fracción III | Permanente |
| Informar donativos recibidos en efectivo, oro o plata superiores a $100,000 MXN | LISR / RMF (declaración informativa) | A más tardar el día 17 del mes siguiente |
| Informar operaciones con partes relacionadas y bienes/servicios recibidos de donantes | LISR art. 82, fracción VIII; regla 3.10.1.15 RMF | Mensual, sin importar monto |
| Informar cambios de estatutos, domicilio, representante, etc. | LISR (donatarias autorizadas) | Dentro de los 10 días siguientes al evento |
| Destinar donativos y rendimientos exclusivamente al objeto social | LISR art. 82; Reglamento LISR art. 138 | Permanente |

Notas adicionales:

- Si la organización se inscribe en el Registro Federal de OSC (CLUNI, INDESOL)
  o recibe apoyos públicos, aplican además las obligaciones de la **Ley
  Federal de Fomento a las Actividades Realizadas por OSC** (informe anual a la
  Comisión, enero de cada año).
- Si se reciben **donativos del extranjero**, aplican disposiciones fiscales y
  de tratados, y la autorización específica si se buscan donativos deducibles
  de EE. UU.
- Las obligaciones de la **Ley General de Transparencia** solo aplican a OSC
  que reciban y administren **recursos públicos**; hoy no es el caso.

### 3.3 Qué significa esto para este documento

- El registro manual mensual (sección 1) **es el antecedente directo** de la
  obligación de "mantener a disposición del público el uso y destino de los
  donativos": cuando la ley lo exija, el Altepetl ya lo estará cumpliendo.
- El sistema automatizado (sección 2) debe diseñarse para satisfacer por
  construcción la tabla de la sección 3.2 — en particular la publicación
  permanente del uso y destino, y la exportación de datos para las
  declaraciones anual y de transparencia.

---

## 4. Relación con los otros documentos

- [Filosofía](./Filosofia.md): el principio "registro, no prohibición"
  aplicado al dinero.
- [Marco Legal Organizacional](./MarcoLegalOrganizacional.md): define la A.C.
  donataria cuyas obligaciones se listan en la sección 3.
- [Política de comprobantes de donación](./PoliticasComprobanteDonacion.md):
  cómo se expide el comprobante de cada donativo y qué se advierte al donante.
- [Capital Inicial Necesario](./CapitalInicialNecesario.md): los donativos
  previos a la constitución financian el arranque; este documento es su
  registro.
- [Especificación del Inicio](./Especificacion.md): la infraestructura que
  alojará el sistema automatizado (sección 2.3).
- [Gobernanza](./Gobernanza.md): el nivel que designa al responsable de la
  conciliación y aprueba la política de privacidad.

---

## Notas de versión

**0.1.0 (2026-09-21):** Versión inicial. Declara el registro público de
donaciones en construcción y define las dos etapas: conciliación manual mensual
de depósitos (procedimiento, privacidad del donante, responsable, límites) y
requisitos del futuro sistema automatizado de consulta (datos, interfaz,
infraestructura, legal, organizativos). Incluye el mapa de obligaciones legales
actuales (ninguna vigente, sin registro legal) y futuras (donataria
autorizada, LISR art. 82). Requiere validación de asesoría legal.
