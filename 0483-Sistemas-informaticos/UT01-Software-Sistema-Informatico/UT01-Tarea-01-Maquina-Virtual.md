# Resumen: Software de un Sistema Informático

Este documento resume los conceptos fundamentales del capítulo **Software de un Sistema Informático**, explicando los elementos de un sistema, los tipos de software, la gestión del sistema operativo y la virtualización. Está pensado como material de referencia para FP DAW.

---

## 1. Qué es un Sistema Informático

Un **sistema informático** es un conjunto de elementos que permiten el tratamiento automatizado de la información: almacenamiento, procesamiento y presentación de datos.

### Componentes principales

* **Hardware**: elementos físicos del sistema (CPU, memoria, disco, periféricos...).
* **Software**: elementos lógicos —los programas y datos que hacen funcionar el hardware—.
* **Usuario**: elemento humano que crea, usa y mantiene el sistema.

### Tipos de software

* **Software de sistema**: controla y coordina el hardware (ej. sistemas operativos, controladores, utilidades básicas).
* **Software de aplicación**: permite realizar tareas concretas (procesadores de texto, navegadores, etc.).

---

## 2. Instalación de Software

### Etapas del proceso de instalación

1. **Comprobación de requisitos**

   * Cada aplicación tiene unos **requisitos mínimos** (hardware, sistema operativo, versión).
   * También existen **requisitos recomendados** para un funcionamiento óptimo.

2. **Ejecución del instalador**

   * **Instalación básica**: automática, pensada para usuarios principiantes.
   * **Instalación personalizada**: permite seleccionar componentes o rutas de instalación.

3. **Configuración**

   * Ajuste de parámetros visuales, directorios por defecto o idioma.

---

## 3. Tipos de Aplicaciones

### 3.1 Aplicaciones de propósito general

Programas de uso común por la mayoría de usuarios:

* **Procesadores de texto** (Word, Writer)
* **Hojas de cálculo** (Excel, Calc)
* **Presentaciones** (PowerPoint, Impress)
* **Correo y mensajería**, **navegadores**, **antivirus**, **compresores**

### 3.2 Aplicaciones de propósito específico

Programas diseñados para tareas concretas:

* **Contabilidad, facturación, gestión empresarial (ERP)**
* **Diseño gráfico y multimedia (Photoshop, Gimp)**
* **Entornos de desarrollo (Visual Studio, Eclipse)**
* **Aplicaciones científicas o técnicas**

---

## 4. Licencias de Software

El software está protegido por derechos de autor. Las licencias determinan qué puede hacer el usuario con el programa.

### 4.1 Software propietario

El usuario **no puede modificar ni redistribuir** el código.

* **CLUF** (Contrato de Licencia de Usuario Final)
* **OEM**: software preinstalado, vinculado a un equipo concreto.
* **Licencia por volumen**: uso corporativo.
* **Freeware**: gratuito pero no modificable.
* **Shareware**: versión de prueba con limitaciones.

### 4.2 Software libre (Licencia GNU GPL)

Otorga **cuatro libertades básicas**:

1. Usar el programa para cualquier propósito.
2. Estudiar su funcionamiento y modificarlo (requiere acceso al código fuente).
3. Distribuir copias.
4. Mejorar el programa y compartir las mejoras.

El software libre no siempre es gratuito, pero siempre es **abierto y colaborativo**. Ejemplo: Linux.

### 4.3 Copyright vs Copyleft

* **Copyright (©)**: restringe el uso y copia.
* **Copyleft (ↄ)**: permite copiar, modificar y redistribuir siempre que se mantenga la misma licencia libre.

---

## 5. Sistemas Operativos

### Definición

El **sistema operativo (SO)** es el software base que gestiona los recursos del hardware y sirve de interfaz entre usuario y máquina.

### Objetivos principales

* Abstraer la complejidad del hardware.
* Optimizar el uso de recursos.
* Permitir la ejecución de programas.
* Gestionar archivos, errores y comunicaciones.

### El Kernel o Núcleo

Es la parte central del sistema operativo. Se encarga de:

* **Gestión de procesos** (programas en ejecución)
* **Gestión de memoria**
* **Gestión de archivos**
* **Gestión de entrada/salida**

### Tipos de Sistemas Operativos

* **Por estructura:** Monolíticos, Jerárquicos, por Capas, Microkernel, Máquina virtual, Cliente-servidor.
* **Por número de usuarios:** Monousuario / Multiusuario.
* **Por número de tareas:** Monotarea / Multitarea.
* **Por procesadores:** Monoprocesador / Multiprocesador.
* **Por red:** En red / Distribuidos.

---

## 6. Gestión de Procesos

Un **proceso** es un programa en ejecución. Puede tener **subprocesos** (hilos).

### Estados de un proceso

* **Ejecución** → activo en CPU.
* **Preparado** → listo pero esperando turno.
* **Bloqueado** → espera de un recurso.
* **Muerto** → ha terminado o fallado.

### Planificador de procesos

Decide qué proceso usa el procesador en cada momento mediante **algoritmos de planificación**:

* **FIFO (First In, First Out)** → primero en llegar, primero en ejecutarse.
* **SJF (Shortest Job First)** → el trabajo más corto primero.
* **SRT (Shortest Remaining Time)** → prioridad al proceso con menos tiempo restante.
* **Round Robin (RR)** → turnos de ejecución fijos.
* **Prioridades** → procesos con prioridad alta se ejecutan antes.

---

## 7. Gestión de Memoria

La **memoria principal (RAM)** almacena los procesos activos. El **gestor de memoria** asigna y libera espacio según los métodos:

### 7.1 Tipos de gestión

* **Particiones fijas**: división en bloques de tamaño constante (ineficiente por fragmentación interna).
* **Particiones variables**: se asigna solo lo necesario (puede causar fragmentación externa).
* **Paginación**: divide la memoria en páginas de igual tamaño. Alta eficiencia, baja fragmentación.

### 7.2 Memoria virtual / Swap

* **Windows: Memoria virtual (pagefile.sys)** → usa disco duro como extensión de RAM.
* **Linux: Memoria swap** → partición del disco dedicada al intercambio.
* Ambas permiten ejecutar más procesos de los que caben en RAM.

---

## 8. Gestión de Entrada/Salida (E/S)

Permite la comunicación entre el sistema y los periféricos.

### Controladores (Drivers)

Software que traduce instrucciones del sistema operativo para el dispositivo físico.

### Estructuras de datos

* **Spool**: cola de impresión o espera (ej. impresoras).
* **Buffer**: almacenamiento temporal para sincronizar velocidades entre dispositivos.

### Modos de transferencia

1. **E/S programada** → la CPU realiza todo el proceso.
2. **E/S por interrupciones** → el periférico avisa cuando está listo.
3. **DMA (Acceso Directo a Memoria)** → el controlador gestiona la transferencia sin usar la CPU.

---

## 9. Gestión de Archivos

Los archivos se organizan en **directorios** o **carpetas**. El **sistema de archivos** gestiona cómo se almacenan y recuperan los datos.

### Objetivos del sistema de archivos

* Acceso rápido y eficiente.
* Fiabilidad y seguridad.
* Facilidad de mantenimiento.
* Control de permisos (lectura, escritura, ejecución).
* Control de concurrencia (acceso simultáneo de varios usuarios).

### Atributos comunes de los archivos

* Nombre, extensión, tamaño, propietario, permisos, fechas de creación/modificación.

Los sistemas de archivos se estructuran jerárquicamente en forma de **árbol de directorios**.

---

## 10. Virtualización y Máquinas Virtuales

La **virtualización** permite ejecutar varios sistemas operativos en un mismo equipo físico mediante software especializado.

### Conceptos clave

* **Máquina anfitrión (host)**: el equipo físico.
* **Máquina invitada (guest)**: el sistema operativo virtual.

### Ventajas

* Ahorro de recursos y costes.
* Entornos de prueba seguros.
* Ejecución de sistemas antiguos o distintos en un mismo equipo.

### Software de virtualización

* **VirtualBox (Oracle)** → libre y gratuito.
* **VMware** → propietario.
* **Hyper-V (Microsoft)** → integrado en Windows.
* **Parallels** → para macOS.

### Configuración básica de una máquina virtual

1. Crear una nueva VM con nombre, SO, RAM y disco.
2. Asignar tipo de disco (tamaño dinámico o fijo).
3. Montar una ISO de instalación (ej. Windows 10).
4. Instalar las **Guest Additions** para optimizar gráficos, ratón y carpetas compartidas.

### Modos de red en VirtualBox

* **NAT**: conexión a Internet a través del host.
* **Puente (Bridged)**: la VM actúa como un equipo más en la red.
* **Red interna**: comunicación entre máquinas virtuales.
* **Host-only**: solo conexión entre host e invitado.

---

## 11. Conclusión

El software constituye el componente lógico esencial de los sistemas informáticos. Comprender sus tipos, licencias y gestión a través de los sistemas operativos es fundamental para el desarrollo de aplicaciones y la administración técnica. La virtualización amplía estas posibilidades, permitiendo experimentar y trabajar en entornos seguros y controlados.
