# 🧠 Unidad 2 – Creación de mi primer programa

## 1. Introducción

* Un programa es un conjunto de instrucciones que resuelve un problema mediante el uso de datos almacenados en memoria.
* El lenguaje elegido es **Java**, por ser **multiplataforma, robusto y orientado a objetos (POO)**.
* Los programas trabajan con **datos**, que se almacenan, procesan y transforman usando **operadores e instrucciones**.
* Aprenderás:

  * Tipos de datos primitivos.
  * Variables y constantes.
  * Operadores y expresiones.
  * Conversiones de tipo.
  * Comentarios y buenas prácticas.

---

## 2. Variables e Identificadores

### Conceptos clave

* **Variable**: zona de memoria con un nombre y un tipo, que almacena un valor modificable.

  ```java
  int edad;
  ```
* **Identificador**: nombre de la variable; debe ser válido y descriptivo.
* **Declaración**: `tipo nombre;`
* **Ejemplo**: `int aux;` → entero de 4 bytes con identificador `aux`.

### Reglas de identificadores

* Comienzan con letra, `_` o `$`.
* Sin espacios ni símbolos especiales.
* Java distingue **mayúsculas/minúsculas**.
* No se pueden usar palabras reservadas ni literales (`true`, `false`, `null`).
* Buenas prácticas: usar nombres descriptivos → `numAlumnos`, `PI`, `MiClase`.

### Tipos de variables

| Tipo                 | Características              |
| -------------------- | ---------------------------- |
| Variables            | Valor modificable            |
| Constantes (`final`) | Valor inmutable              |
| Miembro              | Dentro de una clase          |
| Local                | Dentro de un método o bloque |

---

## 3. Tipos de Datos

### Categorías principales

1. **Primitivos**: valores simples predefinidos (números, caracteres, booleanos).
2. **Referenciados**: almacenan direcciones de memoria (objetos, arrays, `String`).

### Tipos primitivos

| Tipo      | Bits | Rango aproximado               | Ejemplo                  |
| --------- | ---- | ------------------------------ | ------------------------ |
| `byte`    | 8    | −128 a 127                     | `byte b = 1;`            |
| `short`   | 16   | −32,768 a 32,767               | `short s = 2;`           |
| `int`     | 32   | −2,147,483,648 a 2,147,483,647 | `int n = 3;`             |
| `long`    | 64   | ±9×10¹⁸                        | `long l = 1000L;`        |
| `float`   | 32   | 1.4×10⁻⁴⁵ a 3.4×10³⁸           | `float f = 1.2f;`        |
| `double`  | 64   | 4.9×10⁻³²⁴ a 1.8×10³⁰⁸         | `double d = 3.14;`       |
| `char`    | 16   | Unicode 0–65,535               | `char c = 'ñ';`          |
| `boolean` | 1    | `true` / `false`               | `boolean activo = true;` |

> 🔎 Java usa el **estándar IEEE-754** para coma flotante (float y double) y garantiza el mismo tamaño en todas las plataformas.

### Tipos referenciados

* **`String`**: secuencia de caracteres (objeto, pero se usa como tipo básico).

  ```java
  String mensaje = "Hola mundo";
  ```
* **Arrays**: estructuras indexadas de elementos del mismo tipo.

  ```java
  int[] numeros;
  ```
* **Enumerados (`enum`)**: conjunto de valores constantes.

  ```java
  enum Dias {LUNES, MARTES, MIERCOLES}
  ```

---

## 4. Literales

Valores fijos que se asignan directamente:

* **Enteros:** `10`, `024` (octal), `0xA` (hexadecimal)
* **Reales:** `3.14`, `6.02e23`, `2.0f`
* **Carácter:** `'A'`, `'\u0041'`
* **Booleanos:** `true`, `false`
* **Cadenas:** `"texto"`, `"Juan dijo: \"Hola\""`

---

## 5. Operadores y Expresiones

### Tipos de operadores

| Tipo                     | Ejemplos             | Descripción                 |                   |    |                                |
| ------------------------ | -------------------- | --------------------------- | ----------------- | -- | ------------------------------ |
| **Aritméticos**          | `+ - * / % ++ --`    | Operaciones matemáticas     |                   |    |                                |
| **Asignación**           | `= += -= *= /= %=`   | Asignan o modifican valores |                   |    |                                |
| **Relacionales**         | `== != > < >= <=`    | Comparan valores            |                   |    |                                |
| **Lógicos**              | `&&                  |                             | ! &               | ^` | Combinan condiciones booleanas |
| **Bit a bit**            | `~ &                 | ^ << >> >>>`                | Operan sobre bits |    |                                |
| **Condicional ternario** | `cond ? val1 : val2` | Evalúa según una condición  |                   |    |                                |

### Precedencia de operadores

1. Postfijos `++ --`
2. Prefijos `+ - ! ~`
3. `* / %`
4. `+ -`
5. Desplazamiento `<< >> >>>`
6. Relacionales `< <= > >=`
7. Igualdad `== !=`
8. Bit a bit `& ^ |`
9. Lógicos `&& ||`
10. Condicional `?:`
11. Asignación `= += -= …`

> 💡 Usa paréntesis para clarificar la evaluación de expresiones complejas.

---

## 6. Conversión de Tipos

### Automática (promoción)

Cuando el tipo destino tiene **más capacidad**:

```java
int x = 5;
double y = x; // conversión automática int → double
```

### Explícita (casting)

Cuando puede haber pérdida de datos:

```java
int x = 130;
byte y = (byte) x; // casting explícito
```

### Reglas de promoción

1. Si hay `double`, el resto se convierte a `double`.
2. Si no, y hay `float`, el resto a `float`.
3. Si no, y hay `long`, el resto a `long`.
4. Si no, todo se convierte a `int`.

---

## 7. Comentarios en Java

| Tipo          | Sintaxis        | Uso                           |
| ------------- | --------------- | ----------------------------- |
| Una línea     | `// comentario` | Breve explicación             |
| Varias líneas | `/* texto */`   | Bloques de código             |
| Javadoc       | `/** texto */`  | Documentación HTML automática |

> 🧩 Buena práctica: comenta el propósito del código, no lo obvio.

---

## 8. Buenas prácticas y consejos

* Usa nombres descriptivos y consistentes.
* Consulta siempre la documentación oficial de **Oracle Java SE**.
* Prueba los ejemplos y analiza los errores del compilador.
* Usa comentarios Javadoc para generar documentación.
* Entiende la **precedencia de operadores** antes de escribir expresiones complejas.
* Declara variables solo cuando sean necesarias y con el tipo más apropiado.

---

## 📚 Recursos recomendados

* **Documentación oficial Java SE:** [https://docs.oracle.com/javase/](https://docs.oracle.com/javase/)
* **The Java Language Specification**
* **Thinking in Java – Bruce Eckel (gratuito)**
* **IEEE 754 estándar** para coma flotante
* **Manual "Aprenda informática como si estuviera en primero" – UPNA**
