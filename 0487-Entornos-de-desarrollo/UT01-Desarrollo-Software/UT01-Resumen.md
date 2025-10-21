# Entornos de Desarrollo - Tema 1: Desarrollo de Software

## 1. Software y tipos de software

El **software** es el conjunto de programas y datos que permiten que el hardware funcione y ejecute tareas. Se clasifica en tres tipos principales:

* **Software de sistema:** Permite el funcionamiento del hardware y gestiona los recursos del ordenador. Ejemplo: sistemas operativos (Windows, Linux, macOS).
* **Software de programación:** Herramientas que facilitan el desarrollo de software, como editores de código, compiladores, intérpretes e IDEs (por ejemplo, Eclipse o Visual Studio Code).
* **Software de aplicación:** Programas diseñados para realizar tareas concretas. Ejemplo: procesadores de texto, hojas de cálculo, navegadores, videojuegos.

Un **programa** es un conjunto de instrucciones escritas en un lenguaje de programación que indican a la máquina qué operaciones realizar sobre los datos.

---

## 2. Relación hardware-software

El **hardware** son los componentes físicos del ordenador. El **software** es la parte lógica que se ejecuta sobre ellos. Ambos están estrechamente relacionados:

* **Desde el punto de vista del sistema operativo:** actúa como intermediario entre hardware y aplicaciones, gestionando recursos como CPU, memoria o dispositivos de entrada/salida.
* **Desde el punto de vista de las aplicaciones:** los programas están escritos en lenguajes comprensibles para humanos, pero deben traducirse a código binario (0 y 1) para que el hardware los entienda. Esto se realiza mediante compiladores o intérpretes.

---

## 3. Fases del desarrollo del software

El **desarrollo de software** comprende todas las etapas desde la idea hasta la entrega y mantenimiento del producto final. Las principales fases son:

1. **Análisis:** Se definen los requisitos del sistema (funcionales y no funcionales). Es la fase más importante, ya que un mal análisis afecta a todo el proyecto.
2. **Diseño:** Se estructura el sistema, dividiendo en partes, definiendo bases de datos, algoritmos, herramientas y tecnologías.
3. **Codificación:** Los programadores implementan el código fuente siguiendo el diseño. Debe ser modular, legible, eficiente y portable.
4. **Compilación:** Traducción del código fuente a lenguaje máquina. Puede hacerse mediante compilación (traduce todo de una vez) o interpretación (línea a línea).
5. **Pruebas:** Se verifican los módulos (pruebas unitarias) y el sistema completo (pruebas de integración) para asegurar su correcto funcionamiento.
6. **Explotación:** Instalación, configuración y uso de la aplicación por parte del cliente. Incluye pruebas finales (Beta Test).
7. **Mantenimiento:** Actualización y mejora del software. Puede ser:

   * *Correctivo:* para corregir errores.
   * *Evolutivo:* para añadir nuevas funcionalidades.
   * *Adaptativo:* para ajustarse a nuevos entornos o hardware.
   * *Perfectivo:* para optimizar el rendimiento o la usabilidad.
8. **Documentación:** Debe realizarse durante todo el proceso. Incluye:

   * *Guías técnicas* (para desarrolladores),
   * *Guías de instalación* (para técnicos),
   * *Guías de uso* (para usuarios).

---

## 4. Ciclos de vida del software

El **ciclo de vida del software** describe cómo evoluciona un producto desde su creación hasta su retirada. Existen varios modelos:

### Modelo en cascada

* Etapas secuenciales sin posibilidad de volver atrás.
* Útil para proyectos pequeños con requisitos bien definidos.
* No permite cambios durante el desarrollo.

### Modelo en cascada con realimentación

* Igual que el anterior, pero permite volver a fases previas para corregir errores.
* Muy usado cuando los requisitos son claros pero puede haber ajustes menores.

### Modelos evolutivos

* Se adaptan a proyectos cambiantes y flexibles.

**a) Modelo iterativo-incremental:**

* Cada versión mejora la anterior.
* Se lanzan incrementos parciales del producto hasta lograr la versión final.

**b) Modelo en espiral:**

* Combina el enfoque iterativo con la gestión de riesgos.
* Cada ciclo incluye análisis, diseño, codificación, pruebas y evaluación del cliente.

### Modelos ágiles

* Se centran en la satisfacción del cliente y la flexibilidad ante cambios.
* Desarrollos incrementales y colaborativos con comunicación continua.
* Ejemplo: **Scrum**.

---

## 5. Herramientas CASE

Las **herramientas CASE (Computer-Aided Software Engineering)** automatizan tareas del desarrollo para aumentar la productividad y la calidad.

Ventajas:

* Mejor planificación y control del proyecto.
* Reutilización de código.
* Facilita el mantenimiento y la estandarización.

Tipos:

* **U-CASE:** planificación y análisis.
* **M-CASE:** diseño.
* **L-CASE:** codificación, pruebas y documentación.

Ejemplos: ArgoUML, Use Case Maker, ObjectBuilder.

---

## 6. Frameworks

Un **framework** es una estructura o entorno que facilita el desarrollo de aplicaciones sin empezar desde cero. Incluye bibliotecas, herramientas y un conjunto de reglas.

**Ventajas:**

* Desarrollo rápido.
* Reutilización y estandarización del código.
* Portabilidad.

**Desventajas:**

* Dependencia del framework.
* Puede requerir muchos recursos del sistema.

**Ejemplos:**

* .NET (Windows), Spring (Java), Qt (C++), Angular (JavaScript).

---

## 7. Lenguajes de programación

Un **lenguaje de programación** es un conjunto de símbolos, reglas (sintaxis) y significados (semántica) que permiten escribir programas que la máquina pueda ejecutar.

### Evolución

1. **Lenguaje máquina:** Binario (0 y 1), dependiente del hardware.
2. **Lenguaje ensamblador:** Usa mnemónicos, requiere traductor.
3. **Lenguaje de alto nivel:** Más cercano al lenguaje humano (C, Java, Python...).
4. **Lenguaje visual:** Basado en interfaces gráficas.

### Clasificación

**Según el nivel de abstracción:**

* *Bajo nivel:* cercano al hardware (ensamblador).
* *Alto nivel:* cercano al lenguaje humano (Python, Java).

**Según la ejecución:**

* *Compilados:* traducidos completamente antes de ejecutar (C, Pascal).
* *Interpretados:* traducidos en tiempo real (Python, JavaScript).
* *Intermedios:* usan bytecode (Java con su JVM).

**Según la técnica de programación:**

* *Estructurados:* flujo secuencial y controlado (C, Pascal).
* *Orientados a objetos:* basados en clases, objetos, métodos y herencia (Java, C++, C#).
* *Visuales:* permiten programar mediante interfaces gráficas (Visual Basic .NET).

### Código fuente, objeto y ejecutable

* **Código fuente:** escrito por el programador en lenguaje de alto nivel.
* **Código objeto:** traducción intermedia, no ejecutable directamente.
* **Código ejecutable:** resultado final que entiende el ordenador.

### Licencias

* **Código abierto:** editable y reutilizable libremente (open source).
* **Código cerrado:** propiedad privada, sin acceso al código fuente.

---

## 8. Máquinas virtuales y entornos de ejecución

Una **máquina virtual (VM)** es un software que simula un entorno hardware para ejecutar aplicaciones independientemente del equipo físico.

**Funciones:**

* Garantiza portabilidad y seguridad.
* Gestiona la memoria.
* Aísla la aplicación del hardware real.

**Ejemplo:** La **JVM (Java Virtual Machine)** ejecuta el bytecode generado por programas Java.

### Entornos de ejecución (Runtime Environment)

* Son servicios que permiten ejecutar programas sobre una máquina virtual.
* Incluyen bibliotecas estándar (APIs) y la máquina virtual.
* En Java, se denomina **JRE (Java Runtime Environment)** y combina JVM + API Java.

---

## 9. Sentencias de control básicas (Anexo)

**1. Secuenciales:** se ejecutan en orden.

```c
int a = 5;
int b = 10;
int suma = a + b;
```

**2. Selectivas:** ejecutan un bloque según una condición.

```c
if (a > b) {
  printf("A es mayor");
} else {
  printf("B es mayor");
}
```

**3. Repetitivas:** repiten acciones mientras se cumpla una condición.

```c
int i = 0;
while (i < 10) {
  printf("Iteración %d\n", i);
  i++;
}
```

---

## 10. Conclusión

El desarrollo de software es un proceso estructurado que abarca desde el análisis inicial hasta el mantenimiento del producto. Conocer las fases, los modelos de ciclo de vida, las herramientas de apoyo, los frameworks, los lenguajes de programación y los entornos de ejecución es esencial para crear software de calidad, sostenible y adaptable a los cambios tecnológicos.
