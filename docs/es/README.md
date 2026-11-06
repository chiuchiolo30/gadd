# GADD — Desarrollo Dirigido por Agentes bajo Gobernanza

**Versión:** v0.1.0 · Borrador público  
**Creado por:** Sergio Edgardo Chiuchiolo  
**Iniciativa independiente:** Chiuchiolo Labs

**Chiuchiolo Labs** es la identidad utilizada por el autor para sus proyectos independientes; esta mención no implica una sociedad ni una marca registradas.

GADD (Governed Agent-Driven Development) es una propuesta metodológica **orientada al riesgo y centrada en la gobernanza** para integrar agentes de inteligencia artificial en el desarrollo de software sin perder responsabilidad humana, control de arquitectura, trazabilidad ni verificación independiente.

Su principal ámbito de aplicación son **productos sensibles, críticos para el negocio o de alto impacto**, en los que un cambio incorrecto puede afectar datos personales, operaciones esenciales o procesos sujetos a controles exigentes. La rigurosidad debe depender de las consecuencias de fallar, no del tamaño de la empresa. Los proyectos de bajo riesgo pueden utilizar controles proporcionales; GADD **no garantiza por sí sola seguridad, ausencia de defectos ni cumplimiento regulatorio**.

**Idea central:** los agentes pueden dirigir la ejecución; la gobernanza determina la autoridad; la evidencia demuestra la preparación; las personas conservan la responsabilidad.

## Documentación

- [Manifiesto en español](MANIFIESTO.md)
- [Contrato de gobernanza — modelo de referencia](CONTRATO-DE-GOBERNANZA.md)
- [Especificación central (inglés)](../CORE.md)
- [Ciclo de vida (inglés)](../LIFECYCLE.md)
- [Adopción y evidencia (inglés)](../ADOPTION.md)
- [Dos arquitecturas, una metodología (inglés)](../../examples/ONE-METHOD-TWO-ARCHITECTURES.md)
- [Comparación formal: GADD, ADD, SDD y ODD](COMPARACION-ADD-SDD-ODD.md)
- [Demostración Pokédex en Flutter Tucumán (junio 2026, inglés)](../CASE-STUDY-001-POKEDEX.md)

GADD no obliga a utilizar una arquitectura, proveedor de IA o herramienta concretos. Complementa, en lugar de sustituir, prácticas como SDD, TDD y DDD.

Para seleccionar el rigor de los controles, consultá la [guía de adopción por riesgo](../ADOPTION.md) (inglés).

## Cómo comenzar

Leé el [Manifiesto](MANIFIESTO.md), la [especificación central](../CORE.md) y el [Contrato de gobernanza](CONTRATO-DE-GOBERNANZA.md). Luego revisá el [ciclo de vida](../LIFECYCLE.md) y el [modelo de conformidad](../CONFORMANCE.md) para adaptar los controles a tu propio proyecto.

GADD es una **propuesta metodológica en evolución**. Publicar sus principios no implica que todos los controles funcionen automáticamente ni constituye una certificación de cumplimiento.

## Autoría y licencia

**Autor: Sergio Edgardo Chiuchiolo.** GADD se presenta como una iniciativa independiente bajo la identidad **Chiuchiolo Labs**, sin afirmar que sea una sociedad o una marca registrada.

Los documentos originales y ejemplos Markdown propios están disponibles bajo **[Creative Commons Atribución 4.0 Internacional (CC BY 4.0)](../../LICENSE.md)**. Podés compartirlos y adaptarlos, incluso para fines comerciales, respetando la atribución y señalando los cambios. La licencia no concede derechos marcarios ni protege de manera exclusiva las ideas de la metodología. Consultá también el archivo [CITATION.cff](../../CITATION.cff).
