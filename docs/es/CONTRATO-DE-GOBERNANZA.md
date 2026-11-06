# Contrato de gobernanza GADD — modelo de referencia v0.1

**Estado:** Propuesta metodológica, no certificación.  
**Objetivo:** expresar controles verificables para el desarrollo con agentes de IA, independientemente del modelo, IDE, framework o arquitectura elegidos.

La [especificación central de GADD](../CORE.md) define los requisitos mínimos. Este documento explica cómo materializarlos en cada proyecto.

## Cuatro responsabilidades diferentes

| Dimensión | Pregunta | Evidencia esperada |
|---|---|---|
| **Autoridad** | ¿Quién aprueba objetivos, diseños, excepciones y aceptación? | Responsable y decisiones registradas |
| **Gobernanza** | ¿Qué políticas son obligatorias y cuál prevalece si hay contradicción? | Políticas versionadas y jerarquía de precedencia |
| **Ejecución** | ¿Qué puede modificar un agente o desarrollador y cuándo debe detenerse? | Mandato, alcance, límites y reglas de parada |
| **Verificación y aceptación** | ¿Qué controles se ejecutaron y qué permite integrar el cambio? | Resultados comprobables, revisión y gates de integración |

Una respuesta del agente que diga «pasaron las pruebas» **no equivale a evidencia independiente**. Un job verde que no sea obligatorio **no garantiza el bloqueo del merge**.

## Contrato mínimo por cambio

Cada equipo puede implementar estos datos con Markdown, YAML, tickets, un motor de workflow u otras herramientas. GADD no impone nombres de archivos.

- Identificador de cambio, objetivo y criterios de aceptación.
- Rol humano responsable, nivel de riesgo y alcance autorizado.
- Versión de las políticas arquitectónicas y de verificación aplicables.
- Mandato al agente: operaciones permitidas, restricciones y puntos de parada.
- Aprobaciones requeridas y su evidencia.
- Comandos de validación, resultados reales y revisión.
- Condiciones obligatorias de integración y excepciones autorizadas.
- Referencias a baselines cuando exista una política de deuda técnica.

## Jerarquía de políticas

Cada proyecto debe definir su propia precedencia. Un posible orden ilustrativo es: restricciones legales y organizacionales no dispensables; contrato arquitectónico canónico del repositorio; decisiones de diseño específicas aprobadas; instrucciones de roles y agentes; ejemplos y recomendaciones no aprobadas.

**Si un plan generado contradice la arquitectura autorizada, debe detenerse la fase afectada hasta resolverlo.** El agente no tiene autoridad para elegir silenciosamente el documento que más le conviene.

La metodología no exige que todos los proyectos utilicen Clean Architecture, MVVM o Hexagonal. Exige respetar las decisiones *propias de cada proyecto*.

## Ciclo de vida de referencia

```text
INTENCIÓN Y CRITERIOS DE ACEPTACIÓN
                ↓
POLÍTICAS DEL PROYECTO Y MANDATO
                ↓
PLAN / DISEÑO Y APROBACIÓN CUANDO CORRESPONDA
                ↓
IMPLEMENTACIÓN EN ALCANCE AUTORIZADO
                ↓
VALIDACIÓN INDEPENDIENTE
                ↓
REVISIÓN / DEUDA TÉCNICA / EXCEPCIONES
                ↓
CONTROLES DE INTEGRACIÓN
                ↓
ACEPTACIÓN RESPONSABLE
```

Cada control debe expresar condición, autoridad, evidencia y acción ante fallas.

## Los tres niveles de evidencia

| Nivel | Qué demuestra | Qué no demuestra |
|---|---|---|
| **Documentado (Documented)** | La política existe y está versionada | Que el agente la respetó |
| **Observado (Observed)** | Existe evidencia verificable de su ejecución | Que no pueda omitirse en otra ocasión |
| **Exigible (Enforced)** | Un mecanismo independiente impide avanzar si falla la condición obligatoria | Que se detecten todos los defectos posibles |

Para que un validador sea **bloqueante**, las infracciones obligatorias deben producir un estado fallido: código de salida no cero, job fallido o mecanismo equivalente. La comparación con baselines puede ser informativa sin que eso la convierta en una falla de diseño; debe declararse con precisión.

Ejecutar un workflow sobre PR no significa automáticamente que el repositorio impida fusionar cambios con checks fallidos. Hay que verificar protección de ramas, nombres de checks, excepciones y permisos.

## Arquitectura, pruebas y límites de detección

Las fitness functions detectan únicamente las restricciones que implementan; pueden existir falsos positivos y negativos. Las pruebas del validador deben cubrir sus fallas y límites.

Una métrica creciente no siempre equivale a una regresión. Las políticas de deuda deberían ser proporcionales al módulo, umbrales, baseline aprobado y riesgos del cambio.

## Mismo requisito funcional, distinto diseño

Una Pokédex puede cumplir los mismos criterios funcionales en MVVM y en Hexagonal, aunque sus dependencias internas sean distintas. Es la gobernanza del proyecto —no una preferencia del agente— la que decide la implementación. Ver el [caso de estudio de la Pokédex](../CASE-STUDY-001-POKEDEX.md).

## Antes de aceptar un cambio

Debe ser posible comprobar que el objetivo fue autorizado, que no había políticas contradictorias sin resolver, que los controles exigidos corrieron sobre la revisión correcta, que los fallos se corrigieron o justificaron y que las decisiones humanas realmente se registraron.

GADD complementa SDD, TDD, DDD, CI, revisión de código y fitness functions. No reclama la invención de esas prácticas: propone un contrato común para enlazarlas y evaluar su cumplimiento.
