# Aprendizajes clave de la Tarea SI03 (Sistemas Informáticos)

Este documento resume **los conceptos, procedimientos y aprendizajes académicos** adquiridos al realizar la Tarea SI03. No recoge las capturas ni el desarrollo concreto, sino **lo que debo saber para un examen**.

---

## 1. Instalación de un segundo sistema operativo y gestión del arranque

**Competencias adquiridas:**

* Comprender la estructura de particiones necesarias para Windows (partición activa, de sistema y de arranque).
* Saber diferenciar:

  * **Partición activa:** la que indica al firmware dónde está el cargador.
  * **Partición de sistema:** contiene Bootmgr y BCD.
  * **Partición de arranque:** donde está instalado el Windows que estoy ejecutando.
* Instalar un segundo Windows en una partición nueva.
* Modificar descripciones del gestor de arranque usando **bcdedit**.
* Validar que el gestor muestra correctamente varias instalaciones de Windows.

**Conceptos importantes para examen:**

* El cargador de arranque (Boot Manager) vive en la partición de sistema.
* bcdedit permite listar, modificar, renombrar y administrar las entradas del BCD.

---

## 2. Uso avanzado del símbolo del sistema (cmd)

Este ejercicio refuerza dominio real de **ruta absoluta, relativa, filtros, redirección y manipulación del sistema de archivos**.

### 2.1 Configuración básica del sistema

**Lo aprendido:**

* Cambiar fecha del sistema con `date`.
* Cambiar la etiqueta de un volumen con `label`.

### 2.2 Búsqueda de archivos

**Conceptos clave:**

* Uso de `dir` con comodines y búsqueda recursiva (`/s`).
* `dir C:\w* /s /b` muestra coincidencias exactas, formato básico `/b` para procesar mejor salidas.
* Uso del patrón `??s*` para filtrar por posición concreta del carácter.

### 2.3 Creación de estructuras de directorios

**Aprendizajes:**

* Crear carpetas con `mkdir`.
* Crear archivos usando redirección (`echo texto > archivo.txt`).
* Comprender diferencias entre ruta absoluta y relativa.
* Visualizar estructura con `tree /f`.

### 2.4 Listado con rutas absolutas y relativas

**Claves:**

* Desde un directorio, navegar correctamente y listar contenido de otros usando rutas relativas (`..\Windows\System32`).
* Filtrar por extensión: `*.exe`.

### 2.5 Copias, renombrados y cambios de extensión

**Operaciones reforzadas:**

* Copiar múltiples archivos con un solo comando (`copy`, `xcopy`).
* Crear directorios y copiar ejecutables renombrándolos.
* Modificar extensión usando un bucle `for`: `*.txt` → `.sol`.
* Renombrar con `ren`.

### 2.6 Copias completas de directorios

**Aprendizajes:**

* `xcopy /E /I /Y` para copiar estructura completa.
* Borrar carpetas recursivamente (`rmdir /S /Q`).
* Copiar solo archivos sin subdirectorios.

### 2.7 Atributos y redirección avanzada

**Claves de examen:**

* Atributos en Windows: **S (sistema), H (oculto), R (solo lectura)**.
* Cambiar atributos: `attrib +s +h archivo`.
* Redirección:

  * `>` crea/reescribe.
  * `>>` añade contenido.
* Concatenar archivos y ver su contenido (`type`).

### 2.8 Listado de ejecutables (extensiones .exe y .com)

**Aprendizaje:**

* Cómo generar listados filtrados de programas ejecutables.
* Recorrer Windows y System32 de forma selectiva.

### 2.9 Uso de filtros (pipes) y utilidades del sistema

**Conceptos importantes:**

* Redirección de salida: `>`.
* Ordenar resultados con `sort`.
* Filtrar cadenas con `find`.
* Generar listados de directorios completos con `tree` o `dir /s`.

### 2.10 Procesamiento de listados

**Habilidades adquiridas:**

* Crear un archivo con todo el árbol de directorios.
* Ordenarlo alfabéticamente.
* Filtrar archivos modificados hoy.

### 2.11 Trabajo con atributos del sistema

**Claves:**

* Obtener atributos de todo un disco.
* Localizar elementos con atributos combinados.

### 2.12 Archivos por lotes (batch)

**Aprendizajes críticos:**

* Crear scripts .bat.
* Uso de variables de entorno (`%date%`).
* Append constante a un archivo de registro.
* Programar un apagado del sistema (`shutdown /s /t 15`).

**Resultado final del batch:**

* Genera cada día una lista de archivos modificados.
* Lo añade al mismo archivo acumulativo.
* Apaga el equipo tras la ejecución.

---

## 3. Competencias globales obtenidas

* Dominio de **cmd** más allá de lo básico.
* Comprensión clara de **estructura de particiones en Windows**.
* Capacidad de **instalar y gestionar múltiples SO**.
* Manejo sólido de **redirecciones, filtros, pipes, atributos y scripts por lotes**.
* Habilidad para automatizar tareas con batch.
* Entendimiento práctico de **sistema de ficheros de Windows**.

---

## 4. Comandos utilizados y explicación

### Comandos de sistema

* **date 01/11/2025** — cambia la fecha del sistema.
* **label C: win_apellido** — cambia la etiqueta del volumen.

### Listados y filtros

* **dir C:/w* /s /b** — busca nombres que empiezan por "w" en todo C.
* **dir C:/??s* /s /b** — tercer carácter = "s".
* **dir ../Windows/System32/*.exe** — lista ejecutables con ruta relativa.

### Creación de carpetas y archivos

* **mkdir C:/SISTEMAS** — crea carpetas.
* **mkdir DOS / LIBRO / TAREAS** — creación por ruta relativa.
* **echo texto > archivo.txt** — crea o sobrescribe archivo.
* **echo texto >> archivo.txt** — añade contenido.
* **type archivo.txt** — muestra contenido.

### Navegación

* **cd C:/SISTEMAS** — cambio de directorio.
* **cd ..** — subir un nivel.

### Copias y renombrado

* **copy origen destino** — copia un archivo.
* **copy C:/SISTEMAS/TAREAS/*.txt C:/** — copia múltiples archivos.
* **xcopy C:/SISTEMAS C:/CopiaSistemas /E /I /Y** — copia carpetas completas.
* **ren hoja1.sol hoja.dat** — renombra.

### Cambiar extensiones

* **for %i in (*.txt) do copy %i ../DOS/%~ni.sol** — genera nuevas extensiones.

### Borrado

* **rmdir CopiaSistemas /S /Q** — borra carpeta completa.

### Atributos

* **attrib +s +h archivo** — añade atributos.
* **attrib -s -h archivo** — los quita.

### Listados avanzados

* **tree C:/SISTEMAS /f** — estructura completa.
* **dir /s > listadoC.txt** — árbol completo.
* **sort listadoC.txt > ordenadoC.txt** — orden alfabético.
* **find "cadena" archivo** — filtrar textos.

### Fecha

* **dir C:/ /s | find "%date%" > diaHoy.txt** — archivos modificados hoy.

### Lotes

* **echo comandos > diaHoy.bat** — crear script.
* **shutdown /s /t 15** — apagado programado.

## 5. Qué debo recordar explícitamente para un examen

1. Diferencias entre partición activa, de sistema y de arranque.
2. Cómo renombrar entradas del BCD con `bcdedit`.
3. Crear y manipular archivos y directorios usando rutas absolutas y relativas.
4. Uso correcto de `dir` con comodines, filtros y modificadores.
5. Interpretar y modificar atributos: `attrib`.
6. Redirección y pipes (`>`, `>>`, `|`).
7. Uso de `xcopy`, `copy`, `ren`, `rmdir`, `tree`, `sort`, `find`.
8. Generar scripts .bat y usar variables de entorno.
9. Buscar archivos por fecha de modificación.
10. Diferencia entre extensiones .exe y .com y dónde se almacenan en Windows.

---
