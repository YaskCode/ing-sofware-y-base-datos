# Plataforma Inteligente de Gestión Wellness

Cada equipo desarrolla una plataforma web responsive para gestionar rutinas de un dominio wellness, por ejemplo fitness, yoga, hábitos o mindfulness. La aplicación debe permitir a sus usuarios registrar objetivos, consultar rutinas y sesiones y revisar su evolución mensual. El equipo identifica las operaciones de administración que requiere su dominio y diseña un agente especializado.

La [presentación original](programa-proyecto-isbd.pptx) describe el alcance y los componentes de referencia. Incluye recomendaciones, detección de abandono, predicción de progreso, chat y generación de planes. La demostración de cierre debe identificar qué componentes están implementados, qué resultados se verificaron y qué mejoras quedan en el backlog.

## Desarrollo y evidencias

1. [Requisitos y calidad](../programa/semana1.md). Comparación funcional del estado del arte, planificación, análisis de riesgos, factibilidad, requisitos y diseño preliminar del agente.
2. [Arquitectura](../programa/semana2.md). Microservicios, API gateway, contratos, eventos y diseño AI-first con puntos de integración para MCP.
3. [Persistencia y automatización](../programa/semana3.md). Modelos de datos, Firestore, BigQuery, contenedores y pipeline de CI.
4. [Integración y cierre](../programa/semana4.md). Motor de recomendaciones, agente, dashboard, arquitectura final, despliegue y demo.

Trabajen en el repositorio de equipo asignado en [YaskCode-laboratory](https://github.com/YaskCode-laboratory). Usen issues para acordar el alcance y vinculen el PR de cada entrega con requisitos, pruebas y evidencias. Para la entrega final incluyan el SHA o tag de la versión, instrucciones de reproducción, enlace al despliegue según los permisos del curso y video de demostración. Usen datos sintéticos en las demos y omitan secretos y datos personales de commits, logs y capturas.

## Traspaso a las siguientes asignaturas

| Evidencia de salida de ISBD | Uso en Sistemas Inteligentes | Uso en Computación Acelerada para IA |
|---|---|---|
| Contratos de API, arquitectura y decisiones | Integrar herramientas y orquestar agentes | Seleccionar una carga y conservar un contrato de servicio comparable |
| Esquema, diccionario y datos sintéticos | Preparar conocimiento y casos de evaluación de RAG y agentes | Repetir cargas con entradas y tamaños controlados |
| Versión desplegable, pipeline y pruebas | Evolucionar Wellness con una línea base funcional | Comparar ejecución, optimización y servicio con métricas reproducibles |

Incluyan en el README del equipo un índice de estos artefactos, las decisiones pendientes y el estado de las pruebas.
