# Almacenamiento de la Información y Bases de Datos

## 1. Evolución del almacenamiento

El almacenamiento de información ha pasado por distintas etapas. En los inicios de la informática, los datos se guardaban de forma manual en archivos físicos. Después se trasladaron a formatos digitales simples mediante ficheros. Con el crecimiento de la complejidad y volumen de información, estos sistemas resultaron insuficientes, lo que impulsó la creación de sistemas más organizados y eficientes: las bases de datos.

Los sistemas de ficheros presentaban limitaciones como:

* Duplicación de datos
* Falta de integridad
* Escasa seguridad
* Dificultad para acceder y modificar información
* Mala gestión de múltiples usuarios simultáneos

Estas dificultades hicieron necesaria una evolución hacia sistemas que permitieran centralizar, organizar y proteger la información de forma eficiente, dando lugar al concepto de base de datos. A partir de ahí, se desarrollaron herramientas para gestionarlas: los Sistemas Gestores de Bases de Datos (SGBD).

---

## 2. Ficheros

Un **fichero** es una colección de datos relacionados que sirve para almacenar información en memoria secundaria.

### Estructura de un fichero

* **Registro**: conjunto de datos relacionados (fila)
* **Campo**: unidad mínima de información (columna)

### Tipos de ficheros

* **Permanentes**: mantienen datos estables

  * *Maestros*: datos actuales
  * *Constantes*: datos fijos
  * *Históricos*: datos antiguos
* **Temporales**: apoyo en procesos

  * *Intermedios*, *maniobras*, *resultados*

### Soportes de almacenamiento

* **Acceso secuencial** (cintas magnéticas)
* **Acceso directo** (discos duros)

### Métodos de acceso

* **Secuencial**: lectura ordenada
* **Directo**: acceso por posición
* **Indexado**: uso de índices
* **Hash**: posición calculada

---

## 3. Bases de Datos

Una **base de datos (BD)** es un conjunto organizado de información relacionada, almacenada de forma estructurada y con acceso eficiente.

### Elementos

* **Entidades**: objetos de los que se almacena información
* **Atributos**: características de las entidades
* **Registros**: instancias completas de entidades
* **Metadatos**: datos sobre los datos

### Ventajas

* Acceso simultáneo
* Reducción de redundancia
* Seguridad y control
* Recuperación ante fallos
* Independencia de datos

---

## 4. Modelos de Bases de Datos

Diferentes formas de organizar la información:

| Modelo              | Descripción                    |
| ------------------- | ------------------------------ |
| Jerárquico          | Estructura árbol, padre-hijo   |
| En red              | Relación compleja entre nodos  |
| Relacional          | Tablas y relaciones            |
| Orientado a Objetos | Basado en clases y herencia    |
| Otros               | Objeto-relacional, NoSQL, etc. |

### Modelo Relacional (más usado)

* Basado en tablas (**relaciones**) formadas por **tuplas** (filas) y **atributos** (columnas)
* Usa **claves primarias** e **índices**
* Lenguaje estándar: **SQL**

---

## 5. Tipos de Bases de Datos

* **Según contenido**: documentales, estadísticas, referenciales
* **Según acceso**: monousuario o multiusuario
* **Según arquitectura**:

  * *Centralizadas*: un solo equipo
  * *Distribuidas*: varias ubicaciones conectadas

---

## 6. SGBD (Sistemas Gestores de Bases de Datos)

Software encargado de crear, gestionar y controlar bases de datos.

### Lenguajes

* **DDL**: definición de datos
* **DML**: manipulación (consultas, inserciones)
* **DCL**: control (permisos)

### Arquitectura ANSI/SPARC

* **Nivel físico**: almacenamiento
* **Nivel lógico**: estructura general
* **Nivel externo**: vistas para usuarios

---

## 7. Tipos de SGBD

### Comerciales

Oracle, SQL Server, DB2, Sybase

### Libres

MySQL, PostgreSQL, SQLite, Firebird, Apache Derby

---

## 8. Bases de Datos Distribuidas

Base de datos distribuida entre varios servidores conectados en red. Puede usar **fragmentación**:

* **Horizontal** (filas)
* **Vertical** (columnas)
* **Mixta**
