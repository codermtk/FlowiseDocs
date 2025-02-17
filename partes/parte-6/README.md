# Parte 6: Agentes Avanzados

En esta sexta parte del curso, exploraremos herramientas avanzadas, utilities y frameworks autónomos que nos permiten crear agentes más sofisticados en Flowise.

## Contenidos

* [Utilities](./#utilities)
* [AutoGPT](./#autogpt)
* [BabyAGI](./#babyagi)
* [Herramientas en Profundidad](./#herramientas-en-profundidad)

## Utilities

Los Utility nodes son herramientas de desarrollo que nos ayudan a implementar funcionalidades personalizadas en nuestros flujos.

### Custom JS Function

* Permite escribir código JavaScript personalizado
* Útil para transformaciones de datos

### Set/Get Variable

* Almacena y recupera variables en el flujo

### If Else

* Implementa lógica condicional
* Permite bifurcaciones en el flujo

### Sticky Note

* Añade notas y documentación
* Mejora la legibilidad del flujo

## AutoGPT

AutoGPT es un agente autónomo que utiliza un proceso de pensamiento en cadena para completar tareas por sí mismo (tiene la capacidad de usar herramientas). Es como tener un asistente que:

* Piensa paso a paso sobre cómo resolver un problema
* Decide qué acciones tomar
* Ejecuta las acciones necesarias
* Evalúa los resultados
* Ajusta su estrategia según sea necesario

## BabyAGI

BabyAGI es un agente autónomo (sin nodo de herramientas) que:

* Crea tareas automáticamente
* Reprioriza la lista de tareas
* Se enfoca en alcanzar un objetivo específico

## Herramientas en Profundidad

### Herramientas de Búsqueda

* **BraveSearch API**: Búsqueda web usando Brave
* **Exa Search**: Motor de búsqueda especializado
* **Google Custom Search**: Búsqueda personalizada de Google
* **SearchApi**: API de búsqueda general
* **SearXNG**: Meta motor de búsqueda
* **Serp API**: Resultados de motores de búsqueda
* **Serper**: Alternativa a Google Search

### Herramientas de Procesamiento

* **Calculator**: Realiza cálculos matemáticos
* **Python Interpreter**: Ejecuta código Python
* **Chain Tool**: Utiliza chains como herramientas
* **Chatflow Tool**: Integra otros chatflows

### Herramientas de Datos

* **Read File**: Lee archivos del sistema
* **Write File**: Escribe archivos en el sistema
* **Request Get**: Realiza peticiones HTTP GET
* **Request Post**: Realiza peticiones HTTP POST

### Herramientas Especializadas

* **Custom Tool**: Crea herramientas personalizadas
* **OpenAPI Toolkit**: Integra APIs externas
* **Web Browser**: Navega y extrae información web
* **Retriever Tool**: Recupera información de fuentes

## Links Relevantes

### Utilities

* [Custom JS Function](../../integraciones/langchain/utilities/custom-js-function.md)
* [Variables](../../integraciones/langchain/utilities/variables.md)
* [If Else](../../integraciones/langchain/utilities/if-else.md)
* [Sticky Notes](../../integraciones/langchain/utilities/sticky-note.md)

### Frameworks Autónomos

* [AutoGPT](../../documentacion-oficial/integraciones/langchain/agents/autogpt.md)
* [BabyAGI](../../documentacion-oficial/integraciones/langchain/agents/babyagi.md)

### Herramientas

* [Tools](../../documentacion-oficial/integraciones/langchain/tools/)
* [BraveSearch](../../integraciones/langchain/tools/brave-search.md)
* [Calculator](../../documentacion-oficial/integraciones/langchain/tools/calculator.md)
* [Chain Tool](../../documentacion-oficial/integraciones/langchain/tools/chain-tool.md)
* [Custom Tool](../../documentacion-oficial/integraciones/langchain/tools/custom-tool.md)
* [Python Tool](../../integraciones/langchain/tools/python.md)
* [Request Tool](../../integraciones/langchain/tools/request.md)
* [Web Browser](../../documentacion-oficial/integraciones/langchain/tools/web-browser.md)
