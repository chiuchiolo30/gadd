# Comparación técnica: GADD, ADD, SDD y ODD

**Estado:** borrador de investigación para GADD v0.1.0 (5 de noviembre de 2026).  
**Alcance:** comparación con implementaciones documentadas. Por **SDD** usamos principalmente como referencia [GitHub Spec Kit](https://github.github.com/spec-kit/): SDD es una familia de prácticas y no una única metodología propietaria. **ADD** designa [Agent Driven Development (getadd.dev)](https://getadd.dev/docs/), **ODD** designa [Organic Driven Development de Gentle AI](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/usage.md), y **GADD** es la propuesta descrita en este repositorio. Estas referencias pueden evolucionar.

## Resumen

GADD — *Governed Agent-Driven Development* — propone que el desarrollo asistido por agentes de IA se organice en torno a **autoridad explícita, políticas coherentes de proyecto, delegación delimitada, evidencia independiente y aceptación controlada**, con especial aplicación a **sistemas sensibles y críticos para el negocio**.

**No estamos afirmando haber inventado** el trabajo con agentes, SDD, TDD, aprobaciones, revisión independiente, validaciones arquitectónicas ni los checks de CI. Los enfoques analizados contienen mecanismos que se superponen con GADD.

La propuesta **se apoya en evidencia práctica previa**, no solamente en una hipótesis: una demostración pública de un mismo requerimiento implementado con dos gobernanzas arquitectónicas diferentes y experiencias de comprobaciones arquitectónicas automatizadas observadas en proyectos reales. Estas experiencias respaldan componentes esenciales del enfoque; **no constituyen por sí solas una medición comparativa de superioridad frente a SDD, ADD u ODD, ni prueban todos los niveles de enforcement de GADD**. La contribución que formalizamos es un contrato que permite describir y evaluar conjuntamente autoridad, políticas, ejecución, evidencia y aceptación.

## 1. Comparación

| Dimensión | SDD (referencia: Spec Kit) | ADD (getadd.dev) | ODD (Gentle AI) | GADD v0.1 (propuesta) |
|---|---|---|---|---|
| Pregunta rectora | ¿Qué debemos construir y cómo llevamos esa intención hasta la implementación? | ¿Cómo coordinamos agentes especializados para construir, probar y entregar software? | ¿Cómo adaptar el proceso al riesgo y comprensión de la tarea sin burocracia innecesaria? | ¿Quién autoriza, qué política manda y qué evidencia habilita la aceptación? |
| Unidad principal | Especificación, plan, tareas y convergencia | Equipos de agentes, especificaciones y ciclos TDD/verificación | Solicitud o documento de feature recuperable, según tamaño y riesgo | Cambio gobernado: mandato, políticas, evidencia y decisión |
| Arquitectura y reglas | Constitución del proyecto y análisis de consistencia entre artefactos | Configuración del proyecto, roles y reglas | Explora y respeta convenciones del repositorio | Exige jerarquía de autoridad de políticas y resolución de contradicciones |
| Intervención humana | Clarificaciones y revisión de artefactos | Modos de colaboración y aprobaciones | Autorización de cambios y decisiones proporcionales | Responsable humano identificado y gates en función del riesgo |
| Validación | Checklists, análisis, convergencia y pruebas configuradas | TDD y verificación independiente explícita | Comprobaciones proporcionales y revisión acotada opcional | Evidencia independiente de la declaración del agente, según propiedades exigibles |
| Proporcionalidad | Flujos abreviados y completos | Rigor según madurez y autonomía | Proporcionalidad como principio explícito | Distintos niveles de riesgo sin saltar controles obligatorios |
| Integración/PR | Puede integrarse con CI y políticas externas | Quality/ship gates; aplicación depende de configuración | Respeta gates existentes y reglas de entrega | Diferencia entre control **documentado**, **observado** y **exigible técnicamente** |
| Dependencia tecnológica | Diversos agentes y stacks | Método neutro con adaptadores concretos | Múltiples runtimes | No exige un modelo, lenguaje, IDE ni arquitectura particular |

**Importante:** hablamos de énfasis y mecanismos documentados, no de que las otras metodologías carezcan de gobernanza. ADD y ODD ya incluyen autorizaciones y verificación; Spec Kit ya cuenta con constitución y análisis de consistencia.

## 2. SDD: la intención que guía la implementación

La implementación de referencia de GitHub Spec Kit incluye constitución, especificación, clarificación, plan, checklists, tareas, análisis de consistencia, implementación y convergencia.

**Coincidencia:** GADD se beneficia del desarrollo guiado por especificaciones.

**Diferencia propuesta:** el objeto de evaluación de GADD es el **contrato de gobernanza completo** —desde la autoridad del agente hasta la evidencia y la integración—, no únicamente la consistencia entre especificación, plan, tareas y código.

**Afirmación incorrecta que evitamos:** “SDD no tiene gobernanza”. No sería fiel a la documentación de Spec Kit.

Fuente: [Quickstart oficial de Spec Kit](https://github.github.com/spec-kit/quickstart.html).

## 3. ADD: agentes coordinados, TDD y verificación

ADD trata a los agentes como integrantes especializados de un equipo, con límites de alcance, varios modos de participación humana, especificaciones, TDD y verificación independiente.

**Coincidencia:** es el vecino conceptual más próximo a GADD.

**Diferencia propuesta de enfoque:** GADD intenta describir un **contrato verificable de adopción** que también se pueda evaluar sobre cambios escritos por personas, con jerarquía de políticas, evidencias por control, excepciones, baselines y políticas de integración. No obliga a usar TDD ni una topología particular de agentes.

**Afirmación incorrecta que evitamos:** “ADD no controla a sus agentes”. Su documentación sí establece restricciones y controles. La utilidad **comparativa adicional** de GADD frente a ADD —por ejemplo, menos defectos o menor costo de revisión en proyectos equivalentes— requiere mediciones y evaluaciones independientes. Esto no invalida la evidencia práctica ya existente sobre gobernanza arquitectónica y validación automatizada.

Fuente: [Documentación oficial de ADD](https://getadd.dev/docs/).

## 4. ODD: proceso orgánico y proporcional

ODD propone autorizar, explorar, resolver incertidumbre, clasificar según riesgo y capacidad de retomar el trabajo, documentar trabajo sustancial y realizar verificaciones proporcionales. Su implementación también describe políticas de prueba, revisión y entrega.

**Coincidencia:** GADD valora proporcionalidad, autorización y resultados verificables.

**Diferencia propuesta de enfoque:** ODD se centra especialmente en la **organización adaptativa del trabajo**; GADD en las **condiciones de autoridad, consistencia normativa, evidencia y cumplimiento** que deben ser demostrables sin importar el tamaño de la tarea.

**Afirmación incorrecta que evitamos:** “ODD no usa specs ni validaciones”. Sí las usa cuando resultan pertinentes.

Fuente: [Protocolo ODD en Gentle AI](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/usage.md). Esta página sigue la rama principal y podría diferir de una versión publicada específica.

## 5. Propuesta de GADD y límites de su originalidad

La contribución candidata de GADD es la combinación y formalización de:

1. Niveles explícitos de evidencia: **Documentado / Observado / Exigido por un mecanismo independiente**.
2. Jerarquía de políticas y detección de contradicciones entre reglas del proyecto, agentes y artefactos.
3. Trazabilidad del mandato a los cambios, resultados de checks, excepciones y decisión de aceptación.
4. Verificación arquitectónica aplicable a cambios de personas y de agentes.
5. Arquitectura tecnológica elegida por el proyecto, no por la metodología.
6. Distinción entre instrucciones al agente, ejecución real de validadores y bloqueo efectivo de integración.

**Estas capacidades no son individualmente novedosas.** La novedad que investigamos es el diseño coherente de una metodología centrada en ellas.

## 6. Caso anterior a la formulación pública de GADD

El **11 de junio de 2026** se anunció un encuentro de **Flutter Tucumán** titulado *«Arquitectura Flutter en serio: gobernanza, capas y buenas prácticas»*.

Una publicación de la comunidad documenta la demo: un mismo requerimiento funcional de Pokédex bajo dos gobernanzas distintas, **MVVM** y **Hexagonal**, con consecuencias diferentes para los límites de capas y las responsabilidades.

La evidencia confirma una demostración previa de los **principios prácticos** que estamos formalizando, **no** que la metodología ya se llamara GADD o que todos los controles hubieran sido técnicamente obligatorios en esa fecha.

- [Evento de Meetup](https://www.meetup.com/es-es/flutter-tucuman/events/314892755/)
- [Publicación comunitaria de la demo](https://es.linkedin.com/posts/flutter-tucum%C3%A1n_flutter-fluttertucuman-dart-activity-7471973622002266112-k-aI)
- [Caso de estudio 001](../CASE-STUDY-001-POKEDEX.md)

## 7. Evidencia práctica existente y evaluación continua

GADD **no nace como una idea sin probar**. Sus principios se formalizan a partir de experiencias prácticas previas. Es importante distinguir **lo observado** de **lo que todavía necesitamos medir o verificar**.

### 7.1. Qué evidencias ya tenemos

- **Demostración arquitectónica pública (junio de 2026).** Se utilizó un mismo requerimiento funcional de Pokédex en dos proyectos Flutter con políticas diferentes: MVVM y Hexagonal. Las estructuras observadas respetaron enfoques de implementación distintos. Esto respalda la viabilidad de **gobernanza específica del proyecto sin imponer una arquitectura universal**. Ver el [caso de estudio](../CASE-STUDY-001-POKEDEX.md).
- **Verificación automatizada observada en experiencias reales.** Se han utilizado controles arquitectónicos ejecutables y se han observado comprobaciones que terminan correctamente o fallan al detectar infracciones. Esto respalda que ciertas reglas **pueden verificarse fuera de las declaraciones del agente**. Los artefactos de proyectos de terceros y sus validadores privados **no se distribuyen aquí**.
- **Aprendizajes documentados sobre consistencia.** En la retrospectiva de Pokédex se identificaron divergencias entre la arquitectura efectiva y algunos documentos de planificación, evidenciando por qué GADD incluye jerarquía de políticas y control de coherencia.

### 7.2. Alcance de esas evidencias

La existencia de un validador que falla demuestra un **control ejecutable**; por sí sola **no demuestra que la protección de la rama impida un merge**, ni que todas las decisiones del agente hayan sido autorizadas o que todos los criterios funcionales hayan pasado. La demostración de 2026 tampoco prueba que el nombre GADD ya existiera entonces: **GADD formaliza ahora esos principios y experiencias**.

### 7.3. Qué seguiremos midiendo

La evaluación futura no intenta determinar si los principios alguna vez funcionaron: busca **cuantificar sus beneficios, límites y transferibilidad** en proyectos comparables:

- Contradicciones entre políticas identificadas antes de la implementación.
- Desviaciones del mandato detectadas, escaladas o bloqueadas.
- Porcentaje de cambios con evidencia verificable y decisión registrada.
- Diferencia entre checks ejecutados y checks efectivamente obligatorios para integrar.
- Nuevas regresiones arquitectónicas respecto de un baseline aceptado.
- Tiempo de revisión humana y costo operativo adicional.
- Consistencia al cambiar de modelos, agentes, herramientas y arquitecturas.

Los resultados permitirán mejorar la metodología y evaluar si sus controles aportan suficiente beneficio frente al costo. **La validación adicional amplía el alcance de una experiencia existente; no reemplaza ni niega lo que ya fue observado.**

## 8. Posicionamiento breve

> **SDD estructura la intención. ADD organiza equipos de agentes. ODD ajusta orgánicamente el flujo de trabajo. GADD propone un contrato de gobernanza verificable para delegar y aceptar cambios de software.**

Es una **síntesis comparativa**, no una definición universal ni excluyente. Pueden utilizarse conjuntamente.

## Fuentes primarias consultadas (05-11-2026)

- [Spec Kit](https://github.github.com/spec-kit/) y [Quickstart](https://github.github.com/spec-kit/quickstart.html).
- [ADD](https://getadd.dev/docs/).
- [Gentle AI / ODD](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/usage.md).
- [GADD Core](../CORE.md) y [modelo de evidencia](../CONFORMANCE.md).
