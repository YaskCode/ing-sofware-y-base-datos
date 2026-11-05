# Laboratorios guiados

Trabaja con datos sintéticos en el repositorio de equipo. Adjunta a cada PR instrucciones de reproducción, versión evaluada y resultados observados. Los ejercicios pueden prepararse localmente. Para actividades en Google Cloud usa el proyecto autorizado por la docente, registra los recursos utilizados y elimínalos al terminar si son exclusivos del laboratorio.

## 1. Trazabilidad y documentación viva

1. Elige el flujo de registro de una sesión Wellness. Identifica actor, precondición, escenario exitoso y un error.
2. Abre un issue con una historia y enlaza un requisito funcional, un escenario de calidad y sus criterios de aceptación. Por ejemplo, con un usuario autenticado y una sesión válida, al guardar la sesión el historial debe mostrarla una sola vez.
3. Modela el flujo con Mermaid y adjunta un diagrama UML de casos de uso. Registra cualquier propuesta de IA que hayas modificado y la razón.
4. Abre un PR con la matriz historia → requisito → criterio → evidencia. Pide a otra persona que intente reproducir el recorrido a partir de la documentación.

**Resultado esperado.** Cada criterio se relaciona con una verificación y el diagrama permite ubicar la ruta de error.

## 2. API contenerizada

1. Define un contrato para `GET /health` y una operación de Wellness. Implementa ambos con FastAPI. Añade una prueba para la respuesta exitosa y otra para una entrada inválida.
2. Crea un Dockerfile cuyo proceso escuche en `0.0.0.0:8080` o en el puerto definido mediante `PORT`. Construye con `docker build -t wellness-api .` y ejecuta con `docker run --rm -p 8080:8080 wellness-api`.
3. Ejecuta `curl -fsS http://localhost:8080/health` y valida la operación contra el contrato. Despliega el contenedor en Cloud Run y repite las pruebas con acceso autorizado.
4. Registra revisión desplegada, contrato, resultados HTTP y un diagrama de la comunicación entre componentes.

**Resultado esperado.** El endpoint de salud devuelve 200 y la operación satisface el contrato en ambos entornos.

## 3. Persistencia, analítica y CI

1. Modela usuarios, rutinas y sesiones con claves, cardinalidades y restricciones. Representa en Firestore los documentos requeridos por una consulta del historial.
2. Crea sesiones sintéticas con identificadores opacos, fecha y duración. Verifica la consulta por usuario y periodo y carga una copia analítica en BigQuery.
3. Agrega por mes y compara los totales con los datos de origen. Para el ejercicio de BigQuery ML, construye un modelo de regresión de duración con variables disponibles antes de la sesión y separa entrenamiento y evaluación por fecha. Compara el error absoluto medio con una predicción constante basada en el conjunto de entrenamiento.
4. Configura GitHub Actions para instalar dependencias y ejecutar pruebas en cada PR. Incluye pruebas de validación de datos y conserva evidencia de una ejecución exitosa.

**Resultado esperado.** Los totales concuerdan, el experimento identifica el conjunto evaluado y el pipeline detecta una validación fallida.

## 4. Evaluación y observabilidad de IA

1. Versiona un conjunto sintético de casos con una solicitud válida, datos incompletos y una solicitud fuera del alcance Wellness. Define el comportamiento esperado de cada caso.
2. Ejecuta el agente o motor de recomendaciones y captura versión del prompt o modelo, resultado y latencia. Incluye una respuesta controlada ante fallo del proveedor.
3. Compara resultados con las expectativas. Clasifica errores y presenta en el dashboard resultados agregados, sin almacenar entradas personales ni credenciales.
4. Demuestra el flujo desde la interfaz y documenta cómo repetirlo con la versión de cierre.

**Resultado esperado.** La evidencia permite reproducir la demo y determinar qué casos cumplen el comportamiento previsto.
