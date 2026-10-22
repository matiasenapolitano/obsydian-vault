## LLM (Large Language Model)
Es un modelo de lenguaje de gran tamaño. Básicamente es un sistema de IA entrenado a gran escala (aunque puede responder de forma incorrecta o alucinar). Es el motor que utilizan los chatbots como Gemini o ChatGPT.
* Escribir y corregir textos.
* Traducir.
* Resumir documentos muy extensos.
* Programar y depurar código.
* Responder consultas muy complejas.

### TOKENS
Pueden representar una palabra, parte de una palabra, signos de puntuación o fragmentos de números.
* **Ejemplo:** `[super][mercado][-][$][1][,][250][.][00]`
* Cada LLM tiene una capacidad determinada de tokens.
* Se cobra según los tokens entrantes (input) y salientes (output).
* A mayor cantidad de tokens, aumenta la latencia de respuesta.

### VENTANA DE CONTEXTO
Es la cantidad máxima de tokens que un LLM puede considerar en cada solicitud. Incluye prompts, contenido del usuario, historial y demás datos. 

> 💡 **Nota clave:** Es importante diferenciar entre **contexto** (información disponible en el momento) y **conocimiento aprendido** (patrones incorporados durante el entrenamiento). Un prompt puede entrar dentro del límite de texto, pero aun así saturar la ventana, degradation la atención y hacer equivocar al LLM.

---

## COMANDOS Y CONFIGURACIÓN (CLI / AGENT ENVIRONMENT)
* `/connect`: Asigna proveedores/suscripciones contratadas para tenerlas disponibles como modelos.
* `/models`: Selecciona el LLM a utilizar y su variante (según el nivel de razonamiento o esfuerzo requerido).
* `/sessions`: Selecciona la sesión de trabajo tras reabrir el programa (cada apertura inicia una nueva sesión por defecto).
* `/undo`: Deshace el último mensaje y los cambios aplicados en el código.
* `/diff`: Muestra las diferencias de código generadas en la última ejecución.
* `/init`: Crea automáticamente el archivo `AGENTS.md`.
* `@`: Referencia ficheros del proyecto (ejemplo: `@app.js`).
* `!`: Executa comandos directamente en la terminal (modo shell).

---

## PROMPT ENGINEERING
Estructura para guiar al modelo:
1. **Rol (¿Quién soy?):** Define el nivel de experiencia y la especialidad que asume la IA.
2. **Contexto (¿Dónde estamos?):** Explica el proyecto, las tecnologías y el problema general.
3. **Tarea exacta (¿Qué necesitas?):** Instrucción concreta y específica.
4. **Restricciones o Reglas (¿Qué límites hay?):** Convenciones, prohibiciones y estándares.
5. **Formato de salida (¿Cómo lo quieres?):** Estructura del resultado (JSON, Markdown, código puro, etc.).

---

## CONTEXT ENGINEERING
Es la disciplina de decidir qué información debe estar en el contexto del modelo, cuándo y cómo debe estructurarse para producir el mejor resultado.

### AGENTS.MD
Archivo en formato Markdown con instrucciones preestablecidas que se inyectan automáticamente en el contexto. Puede existir a nivel Global, de Repositorio, de Proyecto o de Subcarpeta (creable con `/init`).
* Stack tecnológico.
* Convenciones de código.
* Patrones arquitectónicos.
* Prohibiciones.
* Estructuras del proyecto.
* Flujo de trabajo y TESTING.
* Estilo de commits.

### FICHERO DE MEMORIA
Archivo dinámico que guarda el estado del proyecto: cambios recientes, decisiones tomadas e historial relevante.
* No es una convención obligatoria; se recomienda para proyectos medianos o grandes.

| AGENTS.MD | ARCHIVO DE MEMORIA |
| :--- | :--- |
| **Cómo debe comportarse** | **Qué pasó / Qué sabemos** |

---

## HARNESS
Es el sistema que rodea al modelo y le permite operar. El modelo es el **cerebro**, pero el Harness es el **cuerpo, las manos y el entorno de trabajo**.

**Responsabilidades del Harness:**
1. **Ensamblado del contexto:** Filtra instrucciones del sistema, lee archivos, conserva historial y gestiona el consumo de tokens.
2. **Herramientas disponibles:** Lectura/edición de archivos, ejecución de comandos, búsquedas web, etc.
3. **Gestión de permisos:** Define qué acciones requiere aprobación humana y cuáles se ejecutan automáticamente.
4. **Gestión de memoria:** Resume o recorta la conversación cuando la ventana de contexto se llena.
5. **Manejo de errores:** Reintentos, truncado de salidas y gestión de fallos.
6. **Interfaz de usuario:** Captura la entrada y muestra las respuestas.

---

## FLUJO DE TRABAJO DE UN AGENTE (ReAct Loop)
1. La persona envía el prompt.
2. El **Harness** arma el contexto (prompt, herramientas, permisos, historial, resultados, ubicaciones).
3. El **Modelo** razona, planifica y decide.
4. El **Harness** ejecuta las acciones solicitadas por el modelo.
5. El **Harness** agrega el resultado de la acción al contexto.
6. Se repite el bucle hasta completar la tarea.

