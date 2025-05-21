## Cómo Usar esta Guía Mejorada (Para el Junior)

Esta ruta está diseñada para ser tu mapa. No te sientas presionado a aprender todo de golpe.
1.  **Prioriza:** Habla con tu mentor/líder para entender qué áreas son más críticas para tus primeras tareas.
2.  **Aprende Haciendo:** La teoría es importante, pero la práctica es clave. Intenta aplicar cada concepto.
3.  **Pregunta:** ¡No te quedes con dudas! Preguntar es una señal de compromiso.
4.  **Colabora:** Comparte tus aprendizajes y pide feedback.
5.  **Pequeños Pasos:** Concéntrate en un tema a la vez. La suma de pequeños logros te llevará lejos.

---

## Ejes Técnicos (Mejoras y Adiciones)

### Fundamentos de Programación (C#)

*   **Entender la diferencia entre tipos de datos primitivos (tipos de valor), objetos (tipos de referencia) y estructuras como listas (`List<T>`) o mapas (`Dictionary<TKey, TValue>`).**
    *   **Nuevo Material (Explicación conceptual):**
        *   **Tipos de Valor (Value Types):** Piensa en ellos como tener tu propia copia de un juguete. Si le das tu copia a un amigo y él la rompe, tu juguete original sigue intacto. Ej: `int`, `bool`, `struct`.
        *   **Tipos de Referencia (Reference Types):** Piensa en ellos como tener una dirección a donde está guardado un juguete compartido. Si le das esa dirección a un amigo y él va y rompe el juguete, el juguete está roto para ambos. Ej: `string`, `class`, `List<T>`.
    *   **Ejemplo de Código (C#):**
        ```csharp
        // Tipos de Valor
        int a = 10;
        int b = a; // b es una COPIA de a
        b = 20;
        Console.WriteLine($"a: {a}, b: {b}"); // Output: a: 10, b: 20

        // Tipos de Referencia
        List<string> listA = new List<string> { "apple" };
        List<string> listB = listA; // listB apunta a la MISMA lista que listA
        listB.Add("banana");
        Console.WriteLine($"listA count: {listA.Count}, listB count: {listB.Count}"); // Output: listA count: 2, listB count: 2
        Console.WriteLine(string.Join(", ", listA)); // Output: apple, banana
        ```
    *   **Desafío Personal:** Crea una `struct` simple (ej. `Point` con X e Y) y una `class` simple (ej. `User` con Nombre y Edad). Experimenta asignándolas a nuevas variables y modificando sus propiedades para observar la diferencia entre copia de valor y copia de referencia.

*   **Comprender los conceptos básicos de programación orientada a objetos: clases, instancias, atributos (propiedades/campos) y métodos; herencia, composición y polimorfismo básico.**
    *   **Nuevo Material (Artículo):** [SOLID Principles Explained in C# (Code Maze)](https://code-maze.com/solid-principles-csharp/) (Inglés, para cuando se sientan más cómodos, pero es bueno tenerlo en el radar).
    *   **Ejemplo de Código (C# - Composición vs Herencia):**
        ```csharp
        // Herencia: Un Perro ES UN Animal
        public abstract class Animal {
            public string Nombre { get; set; }
            public abstract void HacerSonido(); // Polimorfismo
        }

        public class Perro : Animal {
            public override void HacerSonido() => Console.WriteLine("Guau!");
            public void TraerPelota() => Console.WriteLine("Perro trayendo la pelota.");
        }

        // Composición: Un Coche TIENE UN Motor
        public class Motor {
            public void Arrancar() => Console.WriteLine("Motor arrancado.");
        }

        public class Coche {
            private Motor _motor; // Coche TIENE UN Motor
            public Coche() {
                _motor = new Motor(); // Crea su propia instancia de Motor
            }
            public void EncenderCoche() {
                _motor.Arrancar();
                Console.WriteLine("Coche encendido.");
            }
        }
        ```
    *   **Desafío Personal:** Diseña un pequeño sistema de clases para una biblioteca. Piensa en `Libro`, `Autor`, `Usuario`. ¿Qué propiedades y métodos tendrían? ¿Dónde usarías herencia (ej. `MaterialBibliografico` como clase base para `Libro` y `Revista`)? ¿Dónde usarías composición (ej. un `Libro` tiene una lista de `Autores`)?

---

### Frontend (Angular y/o React)

*   **Aplicar estilos con CSS modular (o preprocesadores como SASS/SCSS si se usan), comprendiendo la cascada y la especificidad.**
    *   **Nuevo Material (Juego Interactivo):** [CSS Diner (Juego para aprender selectores CSS)](https://flukeout.github.io/) (Inglés, muy divertido y práctico).
    *   **Nuevo Material (Artículo SASS/SCSS):** [Sass Basics (Sitio Oficial)](https://sass-lang.com/guide) (Inglés).
    *   **Desafío Personal:** Intenta replicar el estilo de un componente simple de una web que te guste (ej. un botón, una tarjeta de producto) usando solo HTML y CSS. Luego, intenta organizarlo usando BEM (Block, Element, Modifier) o la estructura de módulos CSS si tu framework lo facilita.

*   **Implementar una SPA simple con un framework del stack (Angular o React), comprendiendo el ciclo de vida básico de componentes.**
    *   **Ejemplo de Código (Conceptual React con Hooks):**
        ```javascript
        import React, { useState, useEffect } from 'react';

        function MiComponente({ mensajeInicial }) {
          const [mensaje, setMensaje] = useState(mensajeInicial);
          const [contador, setContador] = useState(0);

          // Similar a componentDidMount y componentDidUpdate
          useEffect(() => {
            console.log('El componente se montó o actualizó. Mensaje:', mensaje);
            document.title = `Contador: ${contador}`;

            // Similar a componentWillUnmount
            return () => {
              console.log('El componente se va a desmontar.');
            };
          }, [mensaje, contador]); // Se ejecuta si mensaje o contador cambian

          return (
            <div>
              <p>{mensaje}</p>
              <button onClick={() => setMensaje('Nuevo mensaje desde el botón!')}>
                Cambiar Mensaje
              </button>
              <p>Contador: {contador}</p>
              <button onClick={() => setContador(c => c + 1)}>
                Incrementar
              </button>
            </div>
          );
        }
        export default MiComponente;
        ```
    *   **Ejemplo de Código (Conceptual Angular):**
        ```typescript
        import { Component, OnInit, OnDestroy, Input, OnChanges, SimpleChanges } from '@angular/core'; // Agregado OnChanges, SimpleChanges

        @Component({
          selector: 'app-mi-componente',
          template: `
            <div>
              <p>{{ mensaje }}</p>
              <button (click)="cambiarMensaje()">Cambiar Mensaje</button>
              <p>Contador: {{ contador }}</p>
              <button (click)="incrementar()">Incrementar</button>
            </div>
          `
        })
        export class MiComponenteComponent implements OnInit, OnDestroy, OnChanges { // Agregado OnChanges
          @Input() mensajeInicial: string = "Hola Angular!";
          mensaje: string = "";
          contador: number = 0;

          constructor() {
            // El constructor se llama ANTES de que los inputs estén disponibles.
            console.log('Constructor: mensajeInicial aquí es:', this.mensajeInicial, '(puede ser el valor por defecto si el padre no lo pasa aún)');
          }

          ngOnChanges(changes: SimpleChanges): void {
            // Se llama ANTES de ngOnInit y cada vez que un @Input cambia.
            console.log('ngOnChanges:', changes);
            if (changes['mensajeInicial'] && changes['mensajeInicial'].currentValue) {
                // Si mensajeInicial es un input y ha cambiado, podríamos querer actualizar 'mensaje' aquí
                // o en ngOnInit si solo es para inicialización.
                this.mensaje = changes['mensajeInicial'].currentValue;
                console.log('ngOnChanges: mensajeInicial cambió a:', this.mensaje);
            }
          }
          
          ngOnInit(): void {
            // ngOnInit se llama DESPUÉS de la primera ejecución de ngOnChanges.
            // Es un buen lugar para la lógica de inicialización que depende de los inputs.
            if (!this.mensaje) { // Si ngOnChanges no lo estableció (ej. no hubo input de padre)
                this.mensaje = this.mensajeInicial;
            }
            console.log('OnInit: Componente inicializado. Mensaje:', this.mensaje);
            this.actualizarTituloDocumento();
          }

          cambiarMensaje(): void {
            this.mensaje = 'Nuevo mensaje desde el botón Angular!';
            console.log('Mensaje cambiado a:', this.mensaje);
          }

          incrementar(): void {
            this.contador++;
            this.actualizarTituloDocumento();
            console.log('Contador incrementado a:', this.contador);
          }

          actualizarTituloDocumento(): void {
            document.title = `Contador: ${this.contador}`;
          }

          ngOnDestroy(): void {
            console.log('OnDestroy: Componente a punto de ser destruido.');
            // Buen lugar para limpiar suscripciones, timers, etc.
          }
        }
        ```
    *   **Desafío Personal:** Crea un componente "Contador" simple que tenga un botón para incrementar y otro para decrementar un número que se muestra en pantalla. Agrega `console.log` en los diferentes métodos del ciclo de vida (`constructor`, `ngOnChanges`, `ngOnInit`, `ngOnDestroy` para Angular; `constructor` (si es clase), `render`, `componentDidMount`, `componentDidUpdate`, `componentWillUnmount` para React Clases, o el cuerpo de la función y `useEffect` para React Hooks) para ver cuándo se ejecutan. Pasa una propiedad inicial al contador y observa cómo `ngOnChanges` (Angular) o `useEffect` con dependencias (React) reaccionan.

---

### Backend (.NET / ASP.NET Core)

*   **Implementar operaciones CRUD (crear, leer, actualizar, eliminar) utilizando controladores básicos en ASP.NET Core.**
    *   **Ejemplo de Código (ASP.NET Core - Controlador Básico):**
        ```csharp
        using Microsoft.AspNetCore.Mvc;
        using System.Collections.Generic;
        using System.Linq;

        // Modelo simple
        public class Producto {
            public int Id { get; set; }
            public string? Nombre { get; set; } // Permitir nulos o usar DataAnnotations para requerir
            public decimal Precio { get; set; }
        }

        [ApiController]
        [Route("api/[controller]")] // Ruta base: /api/productos
        public class ProductosController : ControllerBase
        {
            // Simulación de una base de datos en memoria.
            // En una aplicación real, esto vendría de un servicio/repositorio conectado a una DB.
            private static List<Producto> _productos = new List<Producto>
            {
                new Producto { Id = 1, Nombre = "Laptop Pro", Precio = 1200.00m },
                new Producto { Id = 2, Nombre = "Mouse Gamer", Precio = 25.00m },
                new Producto { Id = 3, Nombre = "Teclado Mecánico", Precio = 75.50m }
            };
            private static int _nextId = _productos.Count > 0 ? _productos.Max(p => p.Id) + 1 : 1;

            // GET: api/productos
            [HttpGet]
            public ActionResult<IEnumerable<Producto>> GetProductos()
            {
                if (!_productos.Any())
                {
                    return NoContent(); // 204 No Content si la lista está vacía
                }
                return Ok(_productos);
            }

            // GET: api/productos/5
            [HttpGet("{id}")]
            public ActionResult<Producto> GetProducto(int id)
            {
                var producto = _productos.FirstOrDefault(p => p.Id == id);
                if (producto == null)
                {
                    return NotFound(new { Message = $"Producto con ID {id} no encontrado." }); // 404 Not Found
                }
                return Ok(producto);
            }

            // POST: api/productos
            // El cuerpo de la solicitud debe contener un JSON con Nombre y Precio
            [HttpPost]
            public ActionResult<Producto> CreateProducto([FromBody] Producto nuevoProducto) // [FromBody] es implícito para tipos complejos
            {
                if (nuevoProducto == null)
                {
                    return BadRequest("El producto no puede ser nulo.");
                }
                // Aquí irían validaciones más robustas (ej. DataAnnotations en el modelo Producto)
                if (string.IsNullOrWhiteSpace(nuevoProducto.Nombre))
                {
                    ModelState.AddModelError("Nombre", "El nombre del producto es requerido.");
                }
                if (nuevoProducto.Precio <= 0)
                {
                     ModelState.AddModelError("Precio", "El precio debe ser mayor a cero.");
                }

                if (!ModelState.IsValid)
                {
                    return BadRequest(ModelState); // 400 Bad Request con detalles de validación
                }

                nuevoProducto.Id = _nextId++;
                _productos.Add(nuevoProducto);

                // Retorna 201 Created, con la URL para obtener el nuevo recurso y el recurso mismo.
                return CreatedAtAction(nameof(GetProducto), new { id = nuevoProducto.Id }, nuevoProducto);
            }

            // PUT: api/productos/5
            // El cuerpo de la solicitud debe contener un JSON con los campos a actualizar.
            [HttpPut("{id}")]
            public IActionResult UpdateProducto(int id, [FromBody] Producto productoActualizado)
            {
                if (productoActualizado == null || id != productoActualizado.Id)
                {
                    return BadRequest("Datos del producto inválidos o ID no coincide.");
                }

                var productoExistente = _productos.FirstOrDefault(p => p.Id == id);
                if (productoExistente == null)
                {
                    return NotFound(new { Message = $"Producto con ID {id} no encontrado para actualizar." });
                }

                // Validaciones para productoActualizado (similares al POST)
                if (string.IsNullOrWhiteSpace(productoActualizado.Nombre)) ModelState.AddModelError("Nombre", "El nombre del producto es requerido.");
                if (productoActualizado.Precio <= 0) ModelState.AddModelError("Precio", "El precio debe ser mayor a cero.");
                if (!ModelState.IsValid) return BadRequest(ModelState);


                productoExistente.Nombre = productoActualizado.Nombre;
                productoExistente.Precio = productoActualizado.Precio;
                // En un escenario real, aquí llamarías a _context.SaveChanges() si usas EF Core.

                return NoContent(); // 204 No Content indica éxito sin devolver cuerpo.
                                    // Alternativamente, podrías devolver Ok(productoExistente).
            }

            // DELETE: api/productos/5
            [HttpDelete("{id}")]
            public IActionResult DeleteProducto(int id)
            {
                var productoExistente = _productos.FirstOrDefault(p => p.Id == id);
                if (productoExistente == null)
                {
                    return NotFound(new { Message = $"Producto con ID {id} no encontrado para eliminar." });
                }

                _productos.Remove(productoExistente);
                // En un escenario real, aquí llamarías a _context.SaveChanges() si usas EF Core.

                return NoContent(); // 204 No Content
            }
        }
        ```
    *   **Desafío Personal:** Implementa el controlador anterior. Asegúrate de entender los códigos de estado HTTP que se devuelven (`Ok`, `NotFound`, `Created`, `BadRequest`, `NoContent`). Usa Postman o la UI de Swagger para probar cada uno de los endpoints (GET todos, GET por ID, POST, PUT, DELETE). Intenta enviar datos incorrectos al POST o PUT para ver cómo responden las validaciones.

---

### Bases de Datos (SQL Server/Otra BD Relacional con EF Core)

*   **Introducir el uso de Entity Framework Core (EF Core) para interactuar con la base de datos desde el código C#.**
    *   **Ejemplo de Código (EF Core - Consulta Simple LINQ):**
        ```csharp
        // --- Modelo Producto (Producto.cs) ---
        public class Producto
        {
            public int Id { get; set; }
            public string Nombre { get; set; } = string.Empty;
            public decimal Precio { get; set; }
            public int CategoriaId { get; set; } // Foreign Key
            public Categoria? Categoria { get; set; } // Navigation property
        }

        // --- Modelo Categoria (Categoria.cs) ---
        public class Categoria
        {
            public int Id { get; set; }
            public string Nombre { get; set; } = string.Empty;
            public ICollection<Producto> Productos { get; set; } = new List<Producto>(); // Navigation property
        }
        
        // --- DbContext (AppDbContext.cs) ---
        // using Microsoft.EntityFrameworkCore;
        public class AppDbContext : DbContext
        {
            public DbSet<Producto> Productos { get; set; }
            public DbSet<Categoria> Categorias { get; set; }

            public AppDbContext(DbContextOptions<AppDbContext> options) : base(options) { }

            protected override void OnModelCreating(ModelBuilder modelBuilder)
            {
                base.OnModelCreating(modelBuilder);
                // Configuración de relaciones (Fluent API) si es necesario,
                // aunque EF Core puede inferir muchas relaciones por convención.
                modelBuilder.Entity<Producto>()
                    .HasOne(p => p.Categoria)
                    .WithMany(c => c.Productos)
                    .HasForeignKey(p => p.CategoriaId);
                
                // Seed data (opcional)
                modelBuilder.Entity<Categoria>().HasData(
                    new Categoria { Id = 1, Nombre = "Electrónica" },
                    new Categoria { Id = 2, Nombre = "Libros" }
                );
                modelBuilder.Entity<Producto>().HasData(
                    new Producto { Id = 1, Nombre = "Laptop Gamer", Precio = 1500.99m, CategoriaId = 1 },
                    new Producto { Id = 2, Nombre = "Clean Code", Precio = 35.50m, CategoriaId = 2 }
                );
            }
        }

        // --- Servicio (ProductoService.cs) ---
        // using Microsoft.EntityFrameworkCore;
        // using System.Collections.Generic;
        // using System.Linq;
        // using System.Threading.Tasks;
        public class ProductoService
        {
            private readonly AppDbContext _context;

            public ProductoService(AppDbContext context)
            {
                _context = context;
            }

            public async Task<List<Producto>> GetProductosCarosAsync(decimal precioMinimo)
            {
                // LINQ to Entities: Esto se traducirá a una consulta SQL
                return await _context.Productos
                                     .Include(p => p.Categoria) // Cargar datos relacionados (Eager Loading)
                                     .Where(p => p.Precio > precioMinimo)
                                     .OrderBy(p => p.Nombre)
                                     .ToListAsync();
            }

            public async Task<Producto?> GetProductoPorIdAsync(int id)
            {
                return await _context.Productos
                                     .Include(p => p.Categoria)
                                     .FirstOrDefaultAsync(p => p.Id == id);
            }
        }
        ```
    *   **Desafío Personal:** Siguiendo un tutorial de EF Core (como el de Microsoft Docs o el video de Tim Corey), crea una pequeña aplicación de consola o una API mínima con ASP.NET Core.
        1.  Define dos modelos con una relación uno-a-muchos (ej. `Autor` y `Libro`).
        2.  Configura tu `DbContext`.
        3.  Usa los comandos `dotnet ef migrations add NombreMigracion` y `dotnet ef database update` para crear la base de datos (SQLite es una buena opción para empezar por su simplicidad, no requiere servidor).
        4.  Implementa métodos en un servicio para:
            *   Agregar un nuevo autor.
            *   Agregar un libro a un autor existente.
            *   Obtener todos los libros de un autor específico (usando `Include` para cargar el autor).
            *   Obtener todos los libros que contengan una palabra clave en su título.

---

### Testing (MSTest, NUnit, xUnit para .NET)

*   **Escribir pruebas unitarias simples para funciones puras (métodos en clases de servicio o lógica de negocio).**
    *   **Nuevo Material (Artículo):** [The Arrange, Act, Assert (AAA) Pattern (Documentación de xUnit, aplicable a otros)](https://xunit.net/docs/getting-started/test-organization) (Inglés).
    *   **Ejemplo de Código (MSTest):**
        ```csharp
        // --- Clase a Probar (ej. en un proyecto de Lógica de Negocio) ---
        public class CalculadoraSimple
        {
            public int Sumar(int a, int b) => a + b;
            public int Restar(int a, int b) => a - b;
            public double Dividir(double dividendo, double divisor)
            {
                if (divisor == 0)
                {
                    throw new ArgumentException("No se puede dividir por cero.", nameof(divisor));
                }
                return dividendo / divisor;
            }
        }

        // --- Proyecto de Pruebas Unitarias (MSTest) ---
        // Asegúrate de tener una referencia al proyecto que contiene CalculadoraSimple
        // y el paquete NuGet Microsoft.VisualStudio.TestTools.UnitTesting
        // using Microsoft.VisualStudio.TestTools.UnitTesting;
        // using MiProyectoDeLogica; // Namespace de CalculadoraSimple

        [TestClass]
        public class CalculadoraSimpleTests
        {
            private CalculadoraSimple _calculadora = null!; // Inicializado en TestInitialize

            [TestInitialize]
            public void Setup()
            {
                // Este método se ejecuta ANTES de CADA prueba en esta clase.
                // Útil para crear instancias comunes.
                _calculadora = new CalculadoraSimple();
            }

            [TestMethod]
            public void Sumar_DosNumerosPositivos_RetornaSumaCorrecta()
            {
                // Arrange (Organizar)
                int num1 = 5;
                int num2 = 10;
                int esperado = 15;

                // Act (Actuar)
                int resultado = _calculadora.Sumar(num1, num2);

                // Assert (Afirmar)
                Assert.AreEqual(esperado, resultado, "La suma de dos números positivos no fue la esperada.");
            }

            [TestMethod]
            public void Restar_NumeroMayorDeMenor_RetornaNegativoCorrecto()
            {
                // Arrange
                int num1 = 3;
                int num2 = 8;
                int esperado = -5;

                // Act
                int resultado = _calculadora.Restar(num1, num2);

                // Assert
                Assert.AreEqual(esperado, resultado, "La resta no produjo el negativo esperado.");
            }

            [TestMethod]
            public void Dividir_PorNumeroValido_RetornaCocienteCorrecto()
            {
                // Arrange
                double dividendo = 10;
                double divisor = 2;
                double esperado = 5;

                // Act
                double resultado = _calculadora.Dividir(dividendo, divisor);

                // Assert
                Assert.AreEqual(esperado, resultado, 0.001, "La división no fue la esperada."); // Delta para doubles
            }

            [TestMethod]
            [ExpectedException(typeof(ArgumentException))] // Para MSTest v1 y v2
            public void Dividir_PorCero_LanzaArgumentException()
            {
                // Arrange
                double dividendo = 10;
                double divisor = 0;

                // Act
                _calculadora.Dividir(dividendo, divisor); // Esta línea debe lanzar la excepción

                // Assert (No es necesario si se usa ExpectedException)
                // Si no se usa ExpectedException, se puede usar Assert.ThrowsException<ArgumentException>(() => _calculadora.Dividir(dividendo, divisor));
            }

            // Alternativa para probar excepciones (más moderna y recomendada para MSTest v2+ y otros frameworks)
            [TestMethod]
            public void Dividir_PorCero_LanzaArgumentException_Alternativa()
            {
                // Arrange
                double dividendo = 10;
                double divisor = 0;

                // Act & Assert
                var exception = Assert.ThrowsException<ArgumentException>(() => _calculadora.Dividir(dividendo, divisor));
                Assert.AreEqual("No se puede dividir por cero. (Parameter 'divisor')", exception.Message);
            }
        }
        ```
    *   **Desafío Personal:** Toma una función o método simple que hayas escrito (o uno de los ejemplos de C# anteriores, como el `ProductoService` si ya trabajaste con EF Core). Escribe al menos 3-5 pruebas unitarias para él usando el patrón AAA:
        1.  Un caso "feliz" (entrada y salida esperada).
        2.  Un caso con valores límite (ej. cero, números negativos, strings vacíos/nulos si aplica).
        3.  Si el método puede lanzar excepciones, una prueba que verifique que la excepción correcta se lanza bajo las condiciones adecuadas.
        4.  Si el método tiene diferentes caminos lógicos (condicionales), intenta cubrir cada camino con una prueba.

---

### Cloud y DevOps (Azure DevOps)

*   **Observar cómo se dispara un pipeline de CI/CD en Azure DevOps y qué procesos incluye (linting, testeo, build, despliegue).**
    *   **Desafío Personal (Observacional/Guiado):** Pide a un miembro del equipo (mentor, líder técnico, o un compañero con más experiencia) que te guíe a través de un pipeline de CI/CD en Azure DevOps:
        1.  **Disparador:** ¿Qué evento inicia el pipeline (un commit a una rama específica, una creación de PR, un schedule)?
        2.  **Agente:** ¿Dónde se ejecuta el pipeline (Microsoft-hosted vs. self-hosted)?
        3.  **Etapas (Stages):** Identifica las principales etapas (ej., `Build`, `Test`, `DeployToDev`, `DeployToStaging`).
        4.  **Trabajos (Jobs):** Dentro de cada etapa, ¿qué trabajos se ejecutan? ¿Se ejecutan en paralelo?
        5.  **Tareas (Tasks):** Para un trabajo específico (ej. el de Build de .NET), observa las tareas: restaurar dependencias (`dotnet restore`), construir el proyecto (`dotnet build`), ejecutar tests (`dotnet test`), publicar artefactos.
        6.  **Artefactos:** ¿Qué archivos se generan como salida del pipeline de build y cómo se usan en el pipeline de release (despliegue)?
        7.  **Logs:** Aprende a navegar por los logs de una ejecución del pipeline. Intenta encontrar dónde se muestran los resultados de los tests.
        8.  **Variables:** Pregunta sobre el uso de variables en el pipeline (ej. para connection strings, claves de API). ¿Cómo se manejan los secretos?
        Si es posible, haz un cambio pequeño en una rama de desarrollo que dispare el pipeline y sigue su ejecución. No necesitas configurarlo tú mismo aún, pero entender el flujo, los componentes y cómo diagnosticar fallos básicos es crucial.

---

### Arquitectura y Diseño

*   **Comenzar a usar servicios o helpers (clases de servicio en C#) para extraer lógica repetida.**
    *   **Ejemplo de Código (C# - Principio DRY con un Servicio):**
        ```csharp
        // --- PROBLEMA: Lógica de cálculo de descuento repetida ---
        // En un controlador de Pedidos
        public class PedidosController : ControllerBase 
        {
            public IActionResult ProcesarPedido(PedidoDto pedido) 
            {
                decimal subtotal = pedido.Items.Sum(i => i.Precio * i.Cantidad);
                decimal descuento = 0;
                if (pedido.EsClienteVIP && subtotal > 100) 
                {
                    descuento = subtotal * 0.10m; // 10% descuento VIP para compras > 100
                } 
                else if (subtotal > 200) 
                {
                    descuento = subtotal * 0.05m; // 5% descuento para compras > 200
                }
                decimal total = subtotal - descuento;
                // ... guardar pedido con total y descuento ...
                return Ok(new { Subtotal = subtotal, Descuento = descuento, Total = total });
            }
        }

        // En un servicio de Carrito de Compras (quizás para mostrar el precio final antes de pedir)
        public class CarritoService 
        {
            public CarritoResumenDto CalcularResumen(CarritoDto carrito)
            {
                decimal subtotal = carrito.Items.Sum(i => i.Precio * i.Cantidad);
                decimal descuento = 0;
                 if (carrito.EsClienteVIP && subtotal > 100) 
                {
                    descuento = subtotal * 0.10m; // LÓGICA REPETIDA
                } 
                else if (subtotal > 200) 
                {
                    descuento = subtotal * 0.05m; // LÓGICA REPETIDA
                }
                decimal total = subtotal - descuento;
                return new CarritoResumenDto { Subtotal = subtotal, DescuentoAplicado = descuento, TotalEstimado = total };
            }
        }
        // (Suponiendo que PedidoDto y CarritoDto tienen propiedades similares como Items, EsClienteVIP)

        // --- SOLUCIÓN: Extraer lógica a un Servicio de Descuentos ---
        public interface ICalculadoraDescuentoService 
        {
            decimal CalcularDescuento(decimal subtotal, bool esClienteVIP);
        }

        public class CalculadoraDescuentoService : ICalculadoraDescuentoService 
        {
            private const decimal DESCUENTO_VIP = 0.10m;
            private const decimal UMBRAL_VIP = 100m;
            private const decimal DESCUENTO_GENERAL = 0.05m;
            private const decimal UMBRAL_GENERAL = 200m;

            public decimal CalcularDescuento(decimal subtotal, bool esClienteVIP) 
            {
                if (esClienteVIP && subtotal > UMBRAL_VIP) 
                {
                    return subtotal * DESCUENTO_VIP;
                }
                if (subtotal > UMBRAL_GENERAL) 
                {
                    return subtotal * DESCUENTO_GENERAL;
                }
                return 0m;
            }
        }

        // --- USO DEL SERVICIO (requiere Inyección de Dependencias) ---
        // En PedidosController (Constructor Injection)
        public class PedidosControllerRefactorizado : ControllerBase 
        {
            private readonly ICalculadoraDescuentoService _calculadoraDescuento;
            public PedidosControllerRefactorizado(ICalculadoraDescuentoService calculadoraDescuento) 
            {
                _calculadoraDescuento = calculadoraDescuento;
            }

            public IActionResult ProcesarPedido(PedidoDto pedido) 
            {
                decimal subtotal = pedido.Items.Sum(i => i.Precio * i.Cantidad);
                decimal descuento = _calculadoraDescuento.CalcularDescuento(subtotal, pedido.EsClienteVIP);
                decimal total = subtotal - descuento;
                // ... guardar pedido ...
                return Ok(new { Subtotal = subtotal, Descuento = descuento, Total = total });
            }
        }
        // Similarmente para CarritoService...
        ```
    *   **Desafío Personal:** Revisa alguno de tus proyectos de ejercicio o código que hayas escrito recientemente.
        1.  Identifica al menos una pieza de lógica de negocio (no solo una línea, sino un cálculo o una serie de condiciones) que se repita en dos o más lugares, o que sientas que "ensucia" un controlador o una clase principal.
        2.  Crea una nueva clase de servicio (e interfaz si te sientes cómodo) para encapsular esa lógica.
        3.  Refactoriza el código original para que utilice tu nuevo servicio. Si estás en un proyecto ASP.NET Core, investiga cómo registrar e inyectar tu servicio usando la Inyección de Dependencias incorporada.

---

### Control de Versiones (Git con Azure Repos)

*   **Participar en flujos de trabajo con Pull Requests (PRs) en Azure Repos, entendiendo su objetivo.**
    *   **Nuevo Material (Tutorial Interactivo Git):** [Learn Git Branching](https://learngitbranching.js.org/) (Inglés, excelente para visualizar y practicar comandos).
    *   **Desafío Personal:**
        1.  **Clona un repositorio:** Si tienes un proyecto de prueba, úsalo. Si no, crea uno nuevo en Azure Repos (o GitHub/GitLab).
        2.  **Crea y cambia a una nueva rama:** `git checkout -b feature/mi-nueva-funcionalidad`
        3.  **Realiza algunos cambios:** Añade un nuevo archivo, modifica uno existente. Haz al menos dos commits separados en tu rama:
            *   `git add .`
            *   `git commit -m "feat: Implementa la parte A de la funcionalidad X"`
            *   (Haz más cambios)
            *   `git add .`
            *   `git commit -m "fix: Corrige error en la parte A al manejar caso Y"`
        4.  **Sube tu rama al remoto:** `git push -u origin feature/mi-nueva-funcionalidad` (la primera vez `-u` establece el tracking).
        5.  **Crea un Pull Request (PR) / Merge Request (MR):** Ve a la interfaz web de Azure Repos (o tu proveedor Git). Crea un PR desde tu rama `feature/mi-nueva-funcionalidad` hacia la rama principal (`main` o `develop`).
            *   Escribe un título descriptivo para el PR.
            *   En la descripción, explica brevemente qué hace tu cambio y por qué. Si está relacionado con un Work Item de Azure Boards, vincúlalo.
        6.  **Revisión (Auto-revisión o pedir a un compañero):** Revisa los cambios en la pestaña "Files changed" del PR. Añade comentarios si ves algo que mejorarías.
        7.  **(Opcional - Simular conflicto):** Si trabajas con un compañero, pídele que haga un cambio en el mismo archivo y línea en la rama `main`/`develop` y lo suba *antes* de que fusiones tu PR. Cuando intentes fusionar (o después de un `git pull` en `main` y luego `git merge feature/mi-nueva-funcionalidad` localmente), tendrás un conflicto. Intenta resolverlo localmente:
            *   `git checkout main` (o `develop`)
            *   `git pull`
            *   `git checkout feature/mi-nueva-funcionalidad`
            *   `git rebase main` (o `git merge main`)
            *   Abre los archivos con conflictos, edítalos para resolverlos, luego `git add <archivo-resuelto>` y `git rebase --continue` o `git commit` (si fue merge).
            *   `git push --force-with-lease` (si hiciste rebase y ya habías pusheado la rama) o `git push` (si fue merge o primer push tras rebase).
        8.  **Completa el PR:** Una vez revisado y sin conflictos (o resueltos), completa/fusiona el PR. Elige si quieres borrar la rama `feature` después de la fusión.

---

### Documentación y Comunicación

*   **Anotar aprendizajes y procedimientos como parte del onboarding (quizás en la Wiki de Azure DevOps o personal).**
    *   **Desafío Personal:** Durante tu próxima semana, identifica **tres** cosas que aprendas que crees que hubieran sido útiles saber antes o que podrían ayudar a otro nuevo miembro del equipo.
        1.  **Concepto técnico:** Algo que te costó entender al principio (ej. "cómo funciona el binding en Angular", "cuándo usar `async/await` en C#").
        2.  **Proceso del equipo:** Un paso específico en el flujo de trabajo (ej. "cómo pedir acceso a la base de datos de QA", "dónde encontrar los mockups de diseño").
        3.  **Solución a un problema común:** Un error que encontraste y cómo lo solucionaste (ej. "error X al correr `npm install`, solucionado borrando `node_modules` y `package-lock.json` y reintentando").
        Escribe una breve nota (2-3 párrafos máximo por ítem) para cada uno. Si tu equipo tiene una Wiki en Azure DevOps, pregunta si puedes añadir tus notas allí. Si no, guárdalas en un documento personal. El acto de escribirlo para enseñar a otro refuerza tu propio aprendizaje.

---

### Uso de IA (GitHub Copilot, ChatGPT, Azure OpenAI)

*   **Aprender a formular buenos prompts para obtener respuestas útiles y específicas para C#/.NET, Angular/React.**
    *   **Nuevo Material (Artículo/Guía):** [Prompt Engineering Guide (Sitio web con muchos ejemplos y técnicas)](https://www.promptingguide.ai/) (Inglés, muy completo).
    *   **Adición al objetivo:** "Entender las implicancias de la propiedad intelectual y la privacidad al usar IA con código propietario. Siempre priorizar las políticas de la empresa."
    *   **Ejemplo de Prompt (Malo vs. Bueno):**
        *   **Malo:** "c# list sort"
        *   **Intermedio:** "Cómo ordenar una lista de objetos Usuario en C# por edad"
        *   **Bueno:** "Estoy usando C# con .NET 7. Tengo una clase `Usuario` con propiedades `public string Nombre { get; set; }` y `public int Edad { get; set; }`. Necesito ordenar una `List<Usuario>` por la propiedad `Edad` de forma descendente. Muéstrame el código usando LINQ y explica brevemente qué hace el método `OrderByDescending` y cómo se usa una expresión lambda aquí. Adicionalmente, ¿qué consideraciones de rendimiento debería tener si la lista es muy grande (más de 1 millón de usuarios)?"
    *   **Desafío Personal:** Elige una tarea de programación pequeña que tengas que hacer o que te interese.
        1.  **Intento 1 (Prompt Genérico):** Formula un prompt muy básico a tu herramienta de IA (Copilot Chat, ChatGPT, etc.). Evalúa la respuesta. ¿Es útil? ¿Es completa? ¿Es correcta?
        2.  **Intento 2 (Prompt Específico con Contexto):** Refina tu prompt. Añade:
            *   **Rol:** "Actúa como un desarrollador senior de C#..."
            *   **Contexto:** "...estoy trabajando en una API de ASP.NET Core, usando EF Core para el acceso a datos..."
            *   **Tarea específica:** "...necesito escribir un método de servicio que..."
            *   **Restricciones/Requisitos:** "...debe manejar X caso, debe retornar Y formato, no debe usar Z librería externa..."
            *   **Formato de salida deseado:** "Dame el código completo del método, incluyendo using necesarios. Explica las partes clave."
        3.  Compara la respuesta del Intento 2 con la del Intento 1.
        4.  **Validación:** Implementa el código sugerido por la IA (si es relevante). Pruébalo. ¿Funciona como esperas? ¿Hay errores sutiles? ¿Entiendes completamente lo que hace cada línea? **No copies y pegues ciegamente.**
        5.  **Iteración:** Si la respuesta no es perfecta, intenta un tercer prompt pidiendo correcciones o aclaraciones sobre la respuesta anterior.

---

**Nota Final:**

Esta ruta es una guía robusta. El aprendizaje más efectivo vendrá de la **práctica deliberada**, el **trabajo en tareas reales** (incluso pequeñas al principio) y la **mentoría activa** por parte de los miembros más senior del equipo. Animo a los juniors a ser curiosos, a no tener miedo de "romper cosas" (en entornos seguros de desarrollo, ¡claro!) y a celebrar cada pequeño avance.

¡Mucho éxito en este camino de aprendizaje!