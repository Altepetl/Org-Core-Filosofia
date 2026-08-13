# Contribuir a Filosofía

Gracias por tu interés en mejorar este proyecto. Este documento describe cómo
proponer cambios a los documentos fundacionales del Altepetl: la Filosofía, la
Especificación técnica del Inicio y el Marco de Gobernanza.

## Alcance de las contribuciones

Este repositorio contiene los **documentos fundacionales** del Altepetl. No es
código ni infraestructura: es la definición de los principios, los valores, los
objetivos y los mecanismos de operación de la organización. Las contribuciones
pueden ser:

- **Correcciones de consistencia interna:** inconsistencias entre secciones,
  contradicciones, referencias rotas, o términos usados de forma distinta en
  distintas partes.
- **Correcciones de forma:** ortografía, tipografía, puntuación, mayúsculas
  inconsistentes (como `Calpulli` / `calpulli`).
- **Aclaraciones:** ampliar o detallar puntos que quedaron implícitos, siempre
  que **no rompan** lo ya definido.
- **Correcciones factuales:** datos históricos, referencias intelectuales
  mal aplicadas, afirmaciones categóricas no sustentadas.
- **Nuevos documentos derivados:** cuando surja la necesidad (por ejemplo, una
  Constitución formal, un documento del Calpulli, etc.).

## Lo que este repositorio NO acepta

- Cambios que rompan los principios fundacionales sin un proceso deliberado de
  enmienda constitucional (descrito en el
  [Marco de Gobernanza](./Gobernanza.md), sección 5.3).
- Cambios que introduzcan afirmaciones categóricas sin sustento, falacias, o
  extrapolaciones indebidas de referencias intelectuales.
- Cambios que contradigan los valores fundacionales (La vida, El ser humano,
  El amor, La Bondad) o la regla de "comercio sí, capital como inyección no".

## Antes de empezar

1. **Abre un issue** describiendo el cambio propuesto antes de reescribir
   secciones enteras. Los cambios a documentos fundacionales tienen impacto
   amplio; conviene alinear antes de invertir tiempo.
2. Comprueba que no existe ya un issue o PR abierto sobre el mismo tema.
3. Revisa los tres documentos completos para asegurarte de que tu propuesta no
   introduce contradicciones en otra parte:
   - [Filosofía](./Filosofia.md)
   - [Especificación técnica del Inicio](./Especificacion.md)
   - [Marco de Gobernanza](./Gobernanza.md)

## Cómo contribuir

1. Haz *fork* del repositorio y crea una rama descriptiva:
   ```
   git checkout -b corrige/inconsistencia-termino-calpulli
   ```
2. Realiza tus cambios con **commits atómicos y claros**. Cada commit debe
   hacer una sola cosa.
3. Si tu cambio afecta a más de un documento (porque, por ejemplo, la
   Filosofía y la Gobernanza se referencian), actualiza ambos para mantener la
   coherencia.
4. Actualiza el `CHANGELOG.md` bajo `[Unreleased]`.
5. Abre un *Pull Request* contra la rama principal y enlaza el issue original.
   La plantilla de PR te guiará con un checklist específico para documentos
   fundacionales.

## Estilo

- Escribe en español neutro, consistente con el resto de los documentos.
- Respeta el formato Markdown existente (encabezados, tablas, bloques de cita,
  diagramas ASCII en bloques de código).
- Los términos técnicos propios del Altepetl van en mayúscula inicial cuando
  son sustantivos: `Calpulli`, `Kinam`, `Tlahtocan`, `Colectivo`, `Comunidad`.
  La excepción es `Altepetl`, que va siempre con mayúscula inicial por ser
  nombre propio.
- Usa `meshica` (no `azteca`) cuando se refiera al pueblo; ver la nota "Sobre
  el nombre" en la sección Marco Histórico de la Filosofía.
- Mantén los diagramas ASCII legibles en terminal y en GitHub (máximo 72-80
  caracteres de ancho).

## Convención de commits

Sugerimos el formato *Conventional Commits*, en español:

- `corrige: inconsistencia entre peso y jerarquía de criterios`
- `añade: definición de_oráculo financiero en especificación`
- `cambia: sección de prohibiciones por registro en lugar de prohibición`
- `docs: amplía marco histórico del Cem Anahuac`

## Revisión

Los *Pull Requests* son revisados buscando:

1. **Consistencia interna** entre los tres documentos fundacionales.
2. **Coherencia con los valores** del Altepetl.
3. **Calidad argumentativa:** ausencia de falacias, afirmaciones categóricas
   sin sustento, o extrapolaciones indebidas.
4. **Trazabilidad:** el `CHANGELOG.md` refleja el cambio, y se referencia el
   issue que lo originó.

Una propuesta de cambio a este repositorio se beneficia —no es obligatorio,
pero se agradece— de seguir su propio [Pensamiento Crítico](https://github.com/Altepetl/Org-Core-CriticalThinking):
definir el problema, aportar evidencia de la inconsistencia o del hueco que se
corrige, y considerar alternativas antes de proponer la solución.

## Código de conducta

Se espera de toda persona participante un trato respetuoso y profesional. No se
toleran mensajes denigrantes, acosos ni sabotaje de las discusiones o del
material. Las violaciones pueden motivar el rechazo de contribuciones y, si
procede, la expulsión del espacio del proyecto.

## Licencia

Al contribuir, aceptas que tus aportes se publican bajo la misma licencia del
proyecto: [MIT](LICENSE).
