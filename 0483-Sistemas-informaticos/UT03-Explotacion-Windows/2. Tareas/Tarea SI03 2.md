# Resumen de Aprendizajes – Sistemas Informáticos (SI03)

Este documento recoge, en formato claro y revisable, todo lo que aprendí realizando la **Tarea 01 de la asignatura Sistemas Informáticos** del Grado Superior en Desarrollo de Aplicaciones Web.

---

## 1. Gestor de arranque y BCDEDIT

* Aprendí a usar **bcdedit** para modificar entradas del cargador de arranque de Windows.
* Logré renombrar correctamente cada instalación como *Windows 10 A* y *Windows 10 B*.
* Verifiqué que los cambios se reflejaban en el **gestor de arranque**, distinguiendo ambos sistemas.

**Idea clave:** bcdedit permite personalizar, crear y gestionar entradas del bootloader.

---

## 2. Tipos de particiones en Windows

Identifiqué en el Administrador de discos estas particiones y entendí su función:

### ● Partición activa

* Es la partición que usa el firmware para encontrar el cargador de arranque.
* En mi caso: *Reservado para el sistema (500 MB)*.

### ● Partición de sistema

* Contiene los archivos de arranque (bootmgr y BCD).
* Coincide con la partición activa en esta instalación.

### ● Partición de arranque

* Es donde está instalado el SO en ejecución.
* En mi caso: *C: (29,30 GB)* al arrancar Windows 10 B.

**Idea clave:** activa = arranque del firmware; sistema = archivos de boot; arranque = SO en uso.

---

## 3. Ejercicio 2 – Comandos básicos del sistema

### 2.1 Cambiar fecha y etiqueta del disco

* Cambié la fecha con: `date 01/11/2025`
* Modifiqué la etiqueta de C: con: `label C: win_vanoldebarneveld`

Aprendizaje: **el símbolo del sistema permite cambiar parámetros del sistema y unidades sin interfaz gráfica**.

---

### 2.2 Buscar archivos por nombre

Comando usado:

```
dir C:\w* /s /b
```

Aprendí a:

* Buscar recursivamente (`/s`).
* Mostrar solo rutas completas (`/b`).
* Filtrar por patrón de inicio del nombre.

---

### 2.3 Crear estructuras de directorios y archivos

Aprendí a usar rutas absolutas y relativas para:

* Crear carpetas (`mkdir`).
* Crear archivos con redirección (`echo > archivo`).
* Moverme con `cd`.
* Ver el árbol completo con `tree /f`.

**Idea clave:** dominar rutas absolutas y relativas es indispensable para administrar sistemas.

---

## 4. Búsquedas avanzadas con comodines

Ejecuté:

```
dir C:??s* /s /b
```

Aprendí que:

* `?` sustituye a un único carácter.
* Es posible filtrar por la **posición exacta** de un carácter.
* `/s` explora todo el disco.

---

## 5. Uso de rutas relativas hacia directorios del sistema

Comando aprendido:

```
dir ..\Windows\System32\*.exe
```

* Practiqué navegar rutas relativas a partir de mi ubicación actual.
* Obtuve listados de .exe de SYSTEM32.

---

## 6. Copias, renombrados y automatización

### Acciones realizadas

* Copiar archivos (`copy`).
* Crear carpetas como *PRACTICA2*.
* Copiar ejecutables y renombrarlos.
* Usar un bucle `for` para convertir extensiones `.txt` → `.sol`.
* Renombrar archivos (`ren`).

**Idea clave:** combinar comandos permite automatizar tareas repetitivas.

---

## 7. Copias avanzadas con XCOPY y uso de rutas relativas

Aprendí a:

* Hacer copias recursivas sin confirmación:

  ```
  xcopy C:\SISTEMAS C:\CopiaSistemas /E /I /Y
  ```
* Copiar archivos entre carpetas distintas usando rutas relativas.
* Eliminar un directorio completo con:

  ```
  rmdir /S /Q CopiaSistemas
  ```

---

## 8. Atributos, redirecciones y listado del sistema

Aprendí a manipular atributos con:

```
attrib +s +h archivo
attrib -s -h archivo
```

También:

* Crear contenido en archivos con `>`.
* Añadir contenido sin borrar lo anterior con `>>`.
* Generar listados completos del sistema (`dir /s`).
* Ordenar resultados con `sort`.
* Filtrar por fecha o patrones usando `find`.

**Idea clave:** los operadores `>`, `>>`, `|`, y los atributos permiten un flujo de trabajo muy potente.

---

## 9. Identificación de archivos por atributos (S, H, R)

Aprendí a generar un listado completo de la unidad y filtrarlo para encontrar archivos con atributos específicos:

```
dir C: /s /a > atributosC.txt
find "SHR" atributosC.txt > shr.txt
```

---

## 10. Creación de archivos por lotes (BAT)

Desarrollé mi primer archivo por lotes (`diaHoy.bat`) usando redirección.
Incluía:

* Un comando que buscaba archivos modificados hoy.
* Un apagado programado del sistema:

```
shutdown /s /t 15
```

**Idea clave:** los archivos BAT permiten automatizar tareas del sistema usando comandos encadenados.

---

# Conclusiones generales

* Aprendí a manejar **herramientas clave de administración de Windows**.
* Mejoré el uso de **CMD**, rutas, comodines, pipes y redirección.
* Trabajé comandos fundamentales de administración: `dir`, `copy`, `xcopy`, `attrib`, `shutdown`, `for`, `rmdir`, `tree`, `label`, `date`.
* Practiqué conceptos esenciales: particiones, bootloader, rutas, atributos, automatización.

Este resumen me servirá para revisar antes de exámenes y para afianzar comandos esenciales como desarrollador y administrador de sistemas.

---

**Fin del documento.**
