# Ares 🖋️ - El Arquitecto de Estándares para el Desarrollo con IA

**Ares es un meta-prompt de código abierto diseñado para actuar como un "Arquitecto de IA" que colabora contigo para forjar una 'constitución' de desarrollo a medida para tus proyectos. Su objetivo es hacer que el desarrollo asistido por agentes de IA (como los de Cursor.sh) sea seguro, consistente y de la más alta calidad.**

---

## 🤔 ¿Qué Problema Resuelve Ares?

En la era del desarrollo asistido por IA de 2025, los agentes de IA pueden escribir código a una velocidad sin precedentes. Sin embargo, este poder conlleva riesgos:

-   **Inconsistencia:** La IA puede usar diferentes patrones y estilos en cada solicitud.
-   **Deuda Técnica:** El código puede ser funcional pero arquitectónicamente pobre.
-   **Falta de Contexto:** La IA no conoce las reglas, patrones y la lógica de negocio de tu proyecto.

Ares resuelve esto actuando como un **sistema de configuración experto**. Dialoga contigo, analiza tu código y genera un conjunto de **Project Rules** (`.cursor/rules/*.mdc`) que le enseñan a cualquier agente de IA cómo debe comportarse dentro de tu repositorio.

## ✨ Características Principales

-   **Diálogo Colaborativo:** Ares no impone reglas. Te entrevista sobre tu proyecto y tus preferencias para crear una configuración a medida.
-   **Análisis de Código Profundo:** Analiza tu repositorio para detectar automáticamente el stack tecnológico, los patrones de código y las áreas críticas que necesitan ser protegidas por reglas.
-   **Generación de Reglas de Élite:** Crea un conjunto de reglas robustas basadas en las mejores prácticas de la industria, cubriendo:
    -   Arquitectura y Estructura del Proyecto.
    -   Flujos de Trabajo Agénticos (planificación, implementación, testing).
    -   Estándares de Calidad de Código y Convenciones.
    -   Seguridad y Manejo de Secretos.
    -   Testing Automatizado y Notificaciones.
-   **Sistema Auto-Contenido:** El prompt de Ares contiene todo el conocimiento necesario para que cualquier LLM moderno (GPT-4, Claude 3.5, etc.) pueda ejecutarlo sin necesidad de contexto previo sobre el "paradigma de 2025".
-   **Modular y Extensible:** La arquitectura de Ares (un "cerebro" en `ares_meta_prompt.json` y una "biblioteca" en `ares_rules_library.json`) permite una fácil personalización y expansión.

## 🚀 Cómo Usar Ares

Usar Ares es un proceso sencillo en 3 pasos, diseñado para ser ejecutado dentro de un IDE con capacidades de IA como [Cursor.sh](https://cursor.sh/):

### Paso 1: Proporcionar Contexto

1.  **Instala `repomix`:** Si no lo tienes, instala la herramienta para empaquetar tu repositorio.
    ```bash
    npm install -g repomix
    ```
2.  **Genera el fichero de contexto:** En la raíz de tu proyecto, ejecuta:
    ```bash
    repomix > mi_proyecto_contexto.md
    ```
    Esto creará un único fichero de texto con todo el código y la estructura de tu proyecto.

### Paso 2: Iniciar la Conversación con Ares

1.  **Abre tu IDE de IA** (ej. Cursor).
2.  **Copia el contenido** del fichero `ares_meta_prompt.json` de este repositorio.
3.  **Pégalo** en una nueva ventana de chat.
4.  **Adjunta el contexto:** A continuación del prompt, adjunta el contenido completo de `mi_proyecto_contexto.md` que generaste en el paso anterior.
5.  **Envía el mensaje.**

### Paso 3: Dialogar y Generar

1.  **Ares te saludará**, presentará su análisis inicial y te hará el primer bloque de preguntas.
2.  **Responde a sus preguntas** en el chat. Ares continuará el diálogo en fases hasta tener toda la información necesaria.
3.  Una vez finalizado el diálogo, **Ares generará todos los ficheros `.mdc`** para tu proyecto.
4.  **Crea los ficheros** en la carpeta `.cursor/rules/` de tu proyecto y pega el contenido que Ares te ha proporcionado.

¡Listo! Tu agente de IA ahora tiene una "constitución" que seguir, asegurando un desarrollo de alta calidad.

## 🔧 Estructura del Repositorio de Ares

Este repositorio está organizado de forma modular para facilitar su mantenimiento y contribución:

-   **/prompts**: Contiene las diferentes versiones del meta-prompt de Ares.
    -   `ares_v3.2_meta_prompt.json`: El "cerebro" de Ares. Define su personalidad, lógica y flujo de trabajo.
    -   `ares_v3.2_rules_library.json`: La "biblioteca" de Ares. Contiene las plantillas de reglas agnósticas que utiliza.
-   **/docs**: Documentación sobre la filosofía de Ares, guías de contribución y el roadmap del proyecto.
-   `README.md`: Este fichero.

## 🤝 Cómo Contribuir

¡Ares es un proyecto abierto y las contribuciones son bienvenidas! Si tienes ideas para mejorar a Ares, aquí tienes cómo puedes ayudar:

1.  **Abre un Issue:** Si encuentras un bug, tienes una sugerencia para una nueva regla o quieres proponer una mejora en la lógica de Ares, abre un issue detallando tu idea.
2.  **Mejora las Plantillas:** ¿Crees que una plantilla en `ares_rules_library.json` puede ser más robusta o agnóstica? ¡Haz un Pull Request!
3.  **Expande la Lógica:** Si tienes experiencia en "prompt engineering", puedes proponer mejoras a la lógica de diálogo o análisis en `ares_meta_prompt.json`.

Por favor, consulta nuestra `CONTRIBUTING.md` (¡aún por crear!) para más detalles sobre el proceso.

## 🛣️ Roadmap Futuro (Ideas)

-   **Ares v3.3:** Integración más profunda con herramientas MCP, sugiriendo la instalación y configuración de MCPs comunes.
-   **Ares v4.0:** Capacidad de leer un `repomix` y generar un conjunto de reglas iniciales con **cero preguntas**, para luego permitir al usuario refinarlas.
-   **Biblioteca de Reglas por Framework:** Crear bibliotecas de reglas especializadas para frameworks populares (Django, Rails, Laravel, etc.).

## 📜 Licencia

Este proyecto está bajo la Licencia [MIT](LICENSE).
