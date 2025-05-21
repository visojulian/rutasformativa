# Ruta Formativa: Perfil Junior (Stack: C#, .NET, Angular/React, EF Core, Azure DevOps)

## Objetivo del Perfil

El perfil Junior representa el inicio del camino profesional en desarrollo de software. Su formación está centrada en adquirir bases sólidas de programación, comprender el stack del proyecto, y ejecutar tareas simples con acompañamiento activo. La ruta formativa busca:

*   Asegurar el entendimiento de conceptos fundamentales de programación.
*   Familiarizar a la persona con las herramientas del equipo (control de versiones, testing básico, buenas prácticas).
*   Promover una actitud activa hacia el aprendizaje, la comunicación y el trabajo colaborativo.
*   Sentar las bases para una evolución técnica sostenida hacia roles con mayor autonomía.
*   Aplicación de herramientas IA para potenciar su aprendizaje, sin depender de ellas.

---

## Ejes Técnicos

### Fundamentos de Programación (C#)

*   **Reconocer y aplicar estructuras de control básicas como condicionales, bucles y funciones.**

*   **Entender la diferencia entre tipos de datos primitivos (tipos de valor), objetos (tipos de referencia) y estructuras como listas (`List<T>`) o mapas (`Dictionary<TKey, TValue>`).**
    *   **Artículo:** [Tipos (referencia de C#) (Microsoft Docs)](https://learn.microsoft.com/es-es/dotnet/csharp/language-reference/builtin-types/reference-types), [Tipos de valor (referencia de C#) (Microsoft Docs)](https://learn.microsoft.com/es-es/dotnet/csharp/language-reference/builtin-types/value-types), [List<T> (Microsoft Docs)](https://learn.microsoft.com/es-es/dotnet/api/system.collections.generic.list-1), [Dictionary<TKey,TValue> (Microsoft Docs)](https://learn.microsoft.com/es-es/dotnet/api/system.collections.generic.dictionary-2)

*   **Escribir funciones (métodos) simples que resuelvan problemas concretos, con entrada (parámetros) y salida (valor de retorno) de datos claras.**
    *   **Artículo:** [Métodos (Guía de programación de C#) (Microsoft Docs)](https://learn.microsoft.com/es-es/dotnet/csharp/programming-guide/classes-and-structs/methods)
    *   **Ejercicio:** [Ejercicios de programación en C# (Codewars - filtrar por C# y dificultad 8 kyu)](https://www.codewars.com/kata/search/csharp?q=&r%5B%5D=-8&beta=false)

*   **Leer y comprender código ajeno con estructuras básicas.**
    *   **Ejercicio:** Explorar proyectos open-source sencillos en GitHub (ej. buscar ["C# simple example"](https://github.com/search?q=c%23%20simple%20example&type=repositories)).

*   **Iniciar la incorporación de buenas prácticas de legibilidad y organización del código.**
    *   **Artículo:** [Convenciones de codificación de C# (Microsoft Docs)](https://learn.microsoft.com/es-es/dotnet/csharp/fundamentals/coding-style/coding-conventions), [Clean Code - A Handbook of Agile Software Craftsmanship (Resumen/Principios)](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29) (Inglés)

*   **Comprender los conceptos básicos de programación orientada a objetos: clases, instancias, atributos (propiedades/campos) y métodos; herencia, composición y polimorfismo básico.**
    *   **Artículo:** [Programación orientada a objetos (C#) (Microsoft Docs)](https://learn.microsoft.com/es-es/dotnet/csharp/fundamentals/object-oriented/), [Herencia (C#) (Microsoft Docs)](https://learn.microsoft.com/es-es/dotnet/csharp/fundamentals/object-oriented/inheritance), [Polimorfismo (C#) (Microsoft Docs)](https://learn.microsoft.com/es-es/dotnet/csharp/fundamentals/object-oriented/polymorphism)
    *   **Video:** [Object-Oriented Programming with C# (freeCodeCamp)](https://www.youtube.com/watch?v=cwqCQmDbCac) (Inglés)
    *   **Herramienta IA:** Pedir a GitHub Copilot/ChatGPT: "Explica la herencia en C# con un ejemplo de una clase `Animal` y una clase `Perro`."

---

### Frontend (Angular y/o React)

*   **Construir páginas web utilizando HTML semántico, respetando la estructura del contenido.**

*   **Aplicar estilos con CSS modular (o preprocesadores como SASS/SCSS si se usan), comprendiendo la cascada y la especificidad.**
    *   **Artículo:** [Cascada y herencia (MDN Web Docs)](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance), [Especificidad (MDN Web Docs)](https://developer.mozilla.org/es/docs/Web/CSS/Specificity)
    *   **Video:** [Qué es la ESPECIFICIDAD en CSS y cómo funciona la CASCADA (HolaMundo)](https://www.youtube.com/watch?v=tL62c4Gm0kI)

*   **Usar JavaScript moderno (ES6+) / TypeScript para agregar interactividad básica.**
    *   **Artículo:** [JavaScript (MDN Web Docs)](https://developer.mozilla.org/es/docs/Web/JavaScript), [TypeScript para programadores de JavaScript (TypeScript Docs)](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html) (Inglés, oficial)

*   **Implementar una SPA simple con un framework del stack (Angular o React), comprendiendo el ciclo de vida básico de componentes.**
    *   **Angular:** [Tutorial: Tour de los Héroes (Angular Docs)](https://angular.io/tutorial/tour-of-heroes), [Ciclo de vida de los componentes (Angular Docs)](https://angular.io/guide/lifecycle-hooks)
    *   **React:** [Tutorial: Tic-Tac-Toe (React Docs)](https://react.dev/learn/tutorial-tic-tac-toe), [Component Lifecycle (React Docs)](https://react.dev/learn/lifecycle-of-reactive-effects) (Para Hooks, antes era más explícito con clases)
    *   **Video (Angular):** [Curso Angular (Fernando Herrera)](https://www.youtube.com/watch?v=0sR5a8W2u2k&list=PLCKuOXG0bLG21k9f79cMAwGlxy45i4vt7)
    *   **Video (React):** [React JS - Curso Práctico para Principiantes (Fazt)](https://www.youtube.com/watch?v=6Jfk8ic3KVk)

*   **Crear formularios simples con validaciones básicas en el cliente.**
    *   **Angular:** [Validación de formularios reactivos (Angular Docs)](https://angular.io/guide/form-validation#reactive-form-validation)
    *   **React:** [Forms (React Docs)](https://react.dev/learn/sharing-state-between-components#controlled-and-uncontrolled-components), [React Hook Form (Librería popular)](https://react-hook-form.com/get-started)
    *   **Video (Angular):** [Formularios Reactivos - Angular (Fernando Herrera)](https://www.youtube.com/watch?v=QnF2hraj5jY)
    *   **Video (React):** [React Hook Form Tutorial (Codevolution)](https://www.youtube.com/watch?v=RkXv4XApLNU) (Inglés)

---

### Backend (.NET / ASP.NET Core)

*   **Implementar operaciones CRUD (crear, leer, actualizar, eliminar) utilizando controladores básicos en ASP.NET Core.**
    *   **Artículo:** [Creación de una API web con ASP.NET Core y Visual Studio (Microsoft Docs)](https://learn.microsoft.com/es-es/aspnet/core/tutorials/first-web-api)

*   **Aplicar validaciones de entrada en endpoints del servidor (usando Data Annotations o FluentValidation).**
    *   **Artículo:** [Validación de modelos en ASP.NET Core MVC (Microsoft Docs)](https://learn.microsoft.com/es-es/aspnet/core/mvc/models/validation)

*   **Usar herramientas como Postman o la UI de Swagger para testear endpoints manualmente.**
    *   **Artículo:** [Get started with Postman](https://learning.postman.com/docs/getting-started/overview/), [Tutorial: Introducción a las API web de ASP.NET Core con Swagger (OpenAPI) (Microsoft Docs)](https://learn.microsoft.com/es-es/aspnet/core/tutorials/getting-started-with-swashbuckle)

*   **Comprender la estructura básica de un servidor REST (ASP.NET Core Web API).**
    *   **Artículo:** [¿Qué es una API REST? (Red Hat)](https://www.redhat.com/es/topics/api/what-is-a-rest-api)

*   **Identificar la separación entre lógica de negocio (Services), rutas (Controllers) y acceso a datos (Repositories/DbContext).**
    *   **Artículo:** [Patrón de repositorio en ASP.NET Core (Microsoft Docs - Ejemplo)](https://learn.microsoft.com/es-es/aspnet/core/fundamentals/dependency-injection#service-lifetimes-and-registration-options) (Busca ejemplos de Repository Pattern)

---

### Bases de Datos (SQL Server/Otra BD Relacional con EF Core)

*   **Utilizar SQL para realizar consultas simples sobre bases de datos relacionales.**
    *   **Artículo/Tutorial:** [SQL Tutorial (W3Schools - Inglés)](https://www.w3schools.com/sql/), [SQLBolt - Learn SQL with simple, interactive exercises (Inglés)](https://sqlbolt.com/)

*   **Comprender relaciones 1:N y N:M en modelos de datos.**
    *   **Artículo:** [Relaciones (Entity Framework Core - Microsoft Docs)](https://learn.microsoft.com/es-es/ef/core/modeling/relationships)

*   **Introducir el uso de Entity Framework Core (EF Core) para interactuar con la base de datos desde el código C#.**
    *   **Artículo:** [Información general sobre Entity Framework Core (Microsoft Docs)](https://learn.microsoft.com/es-es/ef/core/)
    *   **Video:** [Getting Started With Entity Framework Core (IAmTimCorey - Inglés)](https://www.youtube.com/watch?v=4sxyDXt1igs)

*   **Crear migraciones iniciales con EF Core para definir la estructura de las tablas.**
    *   **Artículo:** [Información general sobre las migraciones (EF Core - Microsoft Docs)](https://learn.microsoft.com/es-es/ef/core/managing-schemas/migrations/)
    *   **Comandos:** `dotnet ef migrations add NombreDeLaMigracion`, `dotnet ef database update`

---

### Seguridad

*   **Aplicar validaciones básicas del lado del servidor para prevenir entradas inválidas.**

*   **Manejar errores comunes de manera controlada y segura (por ejemplo, errores de autenticación o entradas malformadas) usando middleware de excepciones en ASP.NET Core.**
    *   **Artículo:** [Control de errores en ASP.NET Core (Microsoft Docs)](https://learn.microsoft.com/es-es/aspnet/core/fundamentals/error-handling)

---

### Testing (MSTest, NUnit, xUnit para .NET)

*   **Escribir pruebas unitarias simples para funciones puras (métodos en clases de servicio o lógica de negocio).**
    *   **Artículo:** [Pruebas unitarias de C# en .NET Core con dotnet test y MSTest (Microsoft Docs)](https://learn.microsoft.com/es-es/dotnet/core/testing/unit-testing-with-mstest) (También hay para NUnit y xUnit)

---

### Cloud y DevOps (Azure DevOps)

*   **Entender el concepto de entornos de desarrollo, testing y producción.**
    *   **Artículo:** [Deployment environment (Wikipedia - Inglés)](https://en.wikipedia.org/wiki/Deployment_environment)
    *   **Video:** [Learn How Companies Deploy Code to Production Environment [In 5 Mins!]](https://www.youtube.com/watch?v=J9JbzsufemE)

*   **Observar cómo se dispara un pipeline de CI/CD en Azure DevOps y qué procesos incluye (linting, testeo, build, despliegue).**
    *   **Artículo:** [¿Qué es CI/CD? (Azure DevOps - Microsoft Docs)](https://learn.microsoft.com/es-es/azure/devops/pipelines/get-started/what-is-azure-pipelines), [Conceptos clave para nuevas canalizaciones de Azure (Microsoft Docs)](https://learn.microsoft.com/es-es/azure/devops/pipelines/get-started/key-pipelines-concepts)

---

### Arquitectura y Diseño

*   **Comprender el modelo MVC (para aplicaciones web tradicionales) y su aplicación en ASP.NET Core MVC, o patrones para APIs (como el uso de Controllers y Services).**
    *   **Artículo:** [Información general sobre ASP.NET Core MVC (Microsoft Docs)](https://learn.microsoft.com/es-es/aspnet/core/mvc/overview), [Diseño de API web (Microsoft Docs)](https://learn.microsoft.com/es-es/azure/architecture/best-practices/api-design)

*   **Identificar la separación entre presentación (Frontend: Angular/React), lógica de negocio y acceso a datos.**

*   **Comenzar a usar servicios o helpers (clases de servicio en C#) para extraer lógica repetida.**
    *   **Artículo:** [Don't repeat yourself (Wikipedia - Inglés)](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
    *   **Ejercicio:** Identificar código duplicado y aplicar el principio DRY.

*   **Leer diagramas básicos de arquitectura o flujos de componentes.**
    *   **Artículo:** [UML Basic Component Diagram (Visual Paradigm - Inglés)](https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-component-diagram/), [UML Basic Sequence Diagram (Visual Paradigm - Inglés)](https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-sequence-diagram/)

---

### Control de Versiones (Git con Azure Repos)

*   **Usar comandos básicos de Git: clone, commit, pull, push.**
    *   **Artículo:** [Documentación de Git (Sitio Oficial)](https://git-scm.com/doc), [Tutorial de Git en Azure Repos (Microsoft Docs)](https://learn.microsoft.com/es-es/azure/devops/repos/git/gitquickstart)
    *   **Video:** [Git & GitHub Crash Course For Beginners (Traversy Media - Inglés)](https://www.youtube.com/watch?v=SWYqp7iY_Tc)

*   **Crear ramas nuevas y trabajar sobre ellas.**
    *   **Artículo:** [Ramas de Git (Azure Repos - Microsoft Docs)](https://learn.microsoft.com/es-es/azure/devops/repos/git/git-branching-guidance)
    *   **Video:** [Git Branching and Merging (The Net Ninja - Inglés)](https://www.youtube.com/watch?v=0iuqXh0oojo)

*   **Participar en flujos de trabajo con Pull Requests (PRs) en Azure Repos, entendiendo su objetivo.**
    *   **Artículo:** [Acerca de las solicitudes de incorporación de cambios (Azure Repos - Microsoft Docs)](https://learn.microsoft.com/es-es/azure/devops/repos/git/pull-requests)

*   **Incorporar mensajes de commit descriptivos y coherentes (posiblemente vinculados a Work Items de Azure Boards).**
    *   **Artículo:** [Cómo escribir buenos mensajes de commit (Chris Beams - Inglés)](https://cbea.ms/git-commit/), [Conventional Commits (Sitio Oficial - Inglés)](https://www.conventionalcommits.org/en/v1.0.0/)

---

### Documentación y Comunicación

*   **Escribir comentarios útiles en el código (XML Documentation Comments en C#) para explicar intenciones o decisiones.**
    *   **Artículo:** [Comentarios de documentación XML (Guía de C# - Microsoft Docs)](https://learn.microsoft.com/es-es/dotnet/csharp/language-reference/xmldoc/)
    *   **Ejemplo:** Presiona `///` encima de un método en Visual Studio.

*   **Usar nombres de variables, métodos y clases que expresen su propósito, siguiendo las convenciones de C#.**
    *   **Artículo:** [Directrices de nomenclatura (Framework Design Guidelines - Microsoft Docs)](https://learn.microsoft.com/es-es/dotnet/standard/design-guidelines/naming-guidelines)

*   **Participar en revisiones de código (PRs en Azure Repos) como receptor de feedback.**
    *   **Artículo:** [How to Make Good Code Reviews Better (Gergely Orosz - Inglés)](https://blog.pragmaticengineer.com/good-code-reviews-better-code-reviews/)

*   **Preguntar con claridad ante dudas técnicas (usando los canales del equipo, ej. Teams, Azure Boards Discussions).**
    *   **Artículo:** [How to ask good questions (Stack Overflow - Inglés)](https://stackoverflow.com/help/how-to-ask)

*   **Anotar aprendizajes y procedimientos como parte del onboarding (quizás en la Wiki de Azure DevOps o personal).**
    *   **Herramienta (Azure):** [Creación de una wiki para el proyecto (Azure DevOps - Microsoft Docs)](https://learn.microsoft.com/es-es/azure/devops/project/wiki/wiki-create-repo)

---

### Uso de IA (GitHub Copilot, ChatGPT, Azure OpenAI)

*   **Utilizar herramientas de IA para tareas básicas como generar ejemplos de código C# o TypeScript, explicar código o prototipar soluciones simples.**
    *   **Herramienta:** [GitHub Copilot (Sitio Oficial)](https://github.com/features/copilot), [ChatGPT (OpenAI)](https://chat.openai.com/)
    *   **Ejercicio:** Intenta usar "Explain this code" o "Generate a C# function to..." en GitHub Copilot/Chat.

*   **Validar críticamente los resultados obtenidos y no integrarlos sin revisión y comprensión.**

*   **Aprender a formular buenos prompts para obtener respuestas útiles y específicas para C#/.NET, Angular/React.**

---

**Nota:** Muchos recursos, especialmente los oficiales de Microsoft, tienen versiones en español, pero algunos de los mejores tutoriales de la comunidad o artículos de blog pueden estar en inglés. Aprender a consumir recursos en inglés es una habilidad valiosa en desarrollo. ¡Mucha suerte!