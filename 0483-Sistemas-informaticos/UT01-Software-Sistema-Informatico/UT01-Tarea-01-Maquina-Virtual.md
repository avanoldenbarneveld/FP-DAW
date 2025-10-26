# Guía práctica de referencia – Sistemas Informáticos (Windows, Linux y VirtualBox)

Este documento recoge de forma resumida y clara los pasos y conceptos realizados durante la práctica completa relacionada con gestión de procesos, memoria y virtualización. Su objetivo es servir como guía de referencia para futuras tareas o configuraciones similares.

---

## ✅ Actividad 1 – Tipos de software y licencias

Se identifican diferentes programas clasificándolos según:

* **Tipo de licencia**: software libre o propietario.
* **Propósito**: general (uso común) o específico (diseñado para tareas concretas).
* **Descripción**: breve explicación del uso de cada programa.

Esta actividad ayuda a diferenciar distintos tipos de software y comprender cuándo es mejor usar alternativas libres.

---

## ✅ Actividad 2 – Gestión de procesos

### 🔹 En Windows (Administrador de tareas)

Se aprende a gestionar procesos desde el Administrador de tareas:

* Mostrar columnas avanzadas como **PID** y **Línea de comandos**.
* Cambiar la **prioridad de un proceso** desde la pestaña *Detalles*.
* **Finalizar procesos** cuando una aplicación no responde.

Esto permite entender cómo el sistema operativo asigna recursos a los procesos.

### 🔹 En Linux (`ps -efl`)

Se utiliza el comando `ps -efl` para:

* Ver **todos los procesos activos** con información detallada.
* Entender campos como UID, PID, PPID, NI y CMD.
* Identificar **jerarquía de procesos** desde un proceso hijo hasta el proceso inicial del sistema.

Este ejercicio sirve para interpretar cómo Linux organiza y controla los procesos.

---

## ✅ Actividad 3 – Gestión de la memoria

### 🔹 En Windows

Desde la pestaña **Rendimiento** del Administrador de tareas:

* Se consulta **cuánta memoria RAM hay instalada** y **cuánta se está usando**.
* Se accede al **Monitor de recursos** para ver detalles de uso de CPU, memoria, disco y red.
* Se estudia la **memoria virtual** utilizada por Windows mediante el archivo `pagefile.sys`.

> La memoria virtual amplía la RAM usando espacio del disco duro para evitar errores cuando la memoria física se llena.

### 🔹 En Linux (`free`)

Se utiliza el comando `free` para ver:

* Memoria RAM total, usada y libre.
* Memoria **swap** disponible.
* Comparación entre RAM y swap según buenas prácticas del sistema.

Esto refuerza la gestión de memoria en sistemas operativos.

---

## ✅ Actividad 4 – Instalación de Windows 10 en VirtualBox

Se trabaja paso a paso en la instalación de una máquina virtual:

### ⚙️ Creación de máquina virtual

* Se asigna un nombre obligatorio según el estándar de la actividad.
* Se configura tipo y versión del sistema operativo.

### 💾 Configuración de hardware virtual

* Se define tamaño de **RAM y procesador**.
* Se crea un **disco duro virtual** dinámico.

### 💿 Instalación del sistema operativo

* Se utiliza una imagen ISO de Windows 10.
* Se realiza instalación manual y configuración básica del sistema.

### ⭐ Guest Additions

* Se instalan los **complementos del invitado** para mejorar integración: pantalla completa, ratón fluido, copiar/pegar entre equipos.

### 🔗 Carpeta compartida

* Se configura una carpeta compartida entre máquina anfitrión y la virtual para intercambiar archivos.

### 🌐 Instalación de software

* Se instalan aplicaciones dentro de la máquina virtual.
* Se aprende a ver **software instalado** y **hardware del sistema**.
* Se practica la **desinstalación** de software.

---

## ✅ Actividad 5 – Mantenimiento en VirtualBox

### 📦 Archivo .vdi

* Se localiza el archivo del disco duro virtual (.vdi).
* Se explica que es posible hacer copia manual del .vdi como respaldo.

### 🧬 Clonar una máquina virtual

* Se crea una **copia completa de la máquina** en VirtualBox para usar como reserva.

### 🕒 Instantáneas (Snapshots)

* Se crea una instantánea para **guardar el estado actual** de la máquina.
* Sirve para restaurar el sistema fácilmente si ocurre algún error en el futuro.

---

## ✅ Conclusión

Este documento resume cómo gestionar procesos, memoria y cómo instalar y mantener máquinas virtuales. Las herramientas utilizadas fueron:

* Administrador de tareas (Windows)
* Monitor de recursos (Windows)
* Comandos `ps` y `free` (Linux)
* Oracle VirtualBox

Todo este proceso mejora la comprensión práctica del funcionamiento del sistema operativo y la administración de recursos.

---

> 📚 **Consejo final:** guarda esta guía porque te servirá en futuras prácticas de administración de sistemas y virtualización. También es buen contenido para tu portfolio técnico o documentación en GitHub.
