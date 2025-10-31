**Resumen de la Lección 2: Bases de Datos Relacionales**

---

### 1. Modelo de datos

* **Definición**: Representación formal del mundo real que describe los elementos y sus relaciones.
* **Lenguajes**:

  * **DDL (Data Definition Language)**: define estructuras y restricciones.
  * **DML (Data Manipulation Language)**: manipula los datos (insertar, borrar, modificar).
* **Fases del modelado**:

  * **Conceptual**: representación gráfica del problema (modelo entidad-relación).
  * **Lógico**: describe cómo almacenar y operar con los datos (modelo relacional).
  * **Físico**: implementación real en un SGBD (Oracle, MySQL...).

---

### 2. Modelo relacional

* **Creador**: Edgar F. Codd (IBM).
* **Estructura**: basada en teoría de conjuntos. Los datos se almacenan en **tablas (relaciones)**.
* **Conceptos principales**:

  * **Atributo**: columna de la tabla.
  * **Tupla**: fila o registro.
  * **Dominio**: conjunto de valores válidos y atómicos para un atributo.
  * **Grado**: número de columnas.
  * **Cardinalidad**: número de filas.
* **Sinónimos**: Relación=Tabla=Fichero | Tupla=Fila=Registro | Atributo=Columna=Campo.

---

### 3. Características de las relaciones (tablas)

* Cada tabla tiene **nombre único**.
* Cada **atributo tiene nombre distinto** dentro de una tabla.
* **No puede haber filas duplicadas.**
* El **orden de filas y columnas no importa.**
* Todos los valores de una columna deben pertenecer al mismo **dominio**.

---

### 4. Tipos de tablas

* **Base**: contienen los datos reales.
* **Vista**: tabla virtual derivada de otras.
* **Instantánea**: vista que almacena los datos de forma temporal.
* **Temporal**: eliminada automáticamente.

---

### 5. Tipos de datos

* **Texto**: cadenas de caracteres.
* **Numérico**: enteros o decimales.
* **Fecha/Hora**: fechas o tiempos.
* **Booleano (Sí/No)**.
* **Autonumérico**: incremento automático.
* **Memo**: texto largo.
* **Moneda**: valores monetarios.
* **Objeto OLE**: imágenes, gráficos, etc.

> Elegir correctamente el tipo y tamaño es crucial para evitar errores o pérdidas de información.

---

### 6. Claves

* **Superclave**: conjunto de atributos que identifica únicamente una tupla.
* **Clave candidata**: superclave mínima (no redundante).
* **Clave primaria (PK)**: clave candidata elegida para identificar registros.
* **Claves alternativas**: candidatas no elegidas como primaria.
* **Clave ajena (FK)**: atributo cuyos valores coinciden con la PK de otra tabla (relaciona tablas).

> **Integridad referencial**: una FK debe referenciar valores existentes en la tabla primaria o ser NULL.

---

### 7. Índices

* **Definición**: estructuras que aceleran las búsquedas.
* **Ventajas**: mejoran el rendimiento en consultas frecuentes.
* **Desventajas**: ralentizan inserciones y actualizaciones.
* Se crean automáticamente con **PK, FK y UNIQUE.**

---

### 8. Valor NULL

* Representa **ausencia de dato**.
* Diferente de espacio en blanco o cero.
* Se comporta de forma especial en operaciones lógicas:

  * `TRUE AND NULL → NULL`
  * `FALSE AND NULL → FALSE`
  * `TRUE OR NULL → TRUE`
  * `FALSE OR NULL → NULL`
  * `NOT NULL → NULL`
* Se evalúa con el operador **IS NULL**.

---

### 9. Vistas

* **Tabla virtual** derivada de consultas sobre una o varias tablas.
* Motivos para crearlas:

  * **Seguridad**: limitar acceso a ciertos datos.
  * **Comodidad**: simplificar consultas complejas.
* Los cambios en las tablas base se reflejan automáticamente en las vistas.
* No todos los SGBD permiten modificar vistas (Oracle no, SQL Server sí).

---

### 10. Usuarios, roles y privilegios

* **Usuario**: entidad que accede a la base de datos con ciertos permisos.
* **Privilegio**: permiso para ejecutar operaciones.

  * De sistema (crear usuarios, tablas...)
  * Sobre objeto (INSERT, UPDATE, DELETE...)
* **Rol**: agrupación de privilegios que facilita la gestión.

Comandos:

* `CREATE USER`: crea usuario.
* `GRANT`: concede privilegios.
* `REVOKE`: retira privilegios.
* `DROP USER`: elimina usuario.

---

### 11. Lenguaje SQL

* **SQL (Structured Query Language)**: lenguaje estándar para gestionar bases de datos relacionales.
* Es **declarativo**: describe qué se quiere hacer, no cómo hacerlo.
* **Partes**:

  * **DDL**: definir estructuras (`CREATE`, `DROP`, `ALTER`).
  * **DML**: manipular datos (`SELECT`, `INSERT`, `UPDATE`, `DELETE`).
  * **DCL**: controlar accesos (`GRANT`, `REVOKE`).

**Elementos SQL:**

* **Comandos**: instrucciones.
* **Cláusulas**: modifican comandos (`WHERE`, `ORDER BY`).
* **Operadores**: aritméticos y lógicos.
* **Funciones**: realizan cálculos (`AVG`, `SUM`, `MAX`...).
* **Literales**: valores fijos.

**Normas**:

* Terminan con `;`
* No distingue mayúsculas/minúsculas.
* Comentarios: `/* ... */`.

---

### 12. DDL (Data Definition Language)

Permite **crear, modificar o eliminar** objetos de la base de datos.

#### Creación de tablas

```sql
CREATE TABLE NombreTabla (
  Columna1 TipoDato [restricciones],
  Columna2 TipoDato [restricciones]
);
```

Reglas:

* Nombres únicos por esquema.
* Hasta 30 caracteres, sin palabras reservadas.
* No distingue mayúsculas/minúsculas.

#### Restricciones comunes

* **NOT NULL**: valor obligatorio.
* **UNIQUE**: no admite valores repetidos.
* **PRIMARY KEY**: identifica únicamente las filas.
* **FOREIGN KEY**: relaciona con otra tabla.
* **DEFAULT**: valor por defecto.
* **CHECK**: valida condiciones.

#### Eliminación

```sql
DROP TABLE NombreTabla [CASCADE CONSTRAINTS];
```

Borra tabla y sus datos.

#### Modificación

```sql
ALTER TABLE NombreTabla ADD Columna TipoDato;
ALTER TABLE NombreTabla DROP COLUMN Columna;
ALTER TABLE NombreTabla MODIFY Columna TipoDato;
ALTER TABLE NombreTabla RENAME COLUMN Antiguo TO Nuevo;
```

#### Índices

```sql
CREATE INDEX NombreIndice ON NombreTabla (Columna);
DROP INDEX NombreIndice;
```

---

### 13. DCL (Data Control Language)

* **CREATE USER / DROP USER**: gestiona usuarios.
* **GRANT / REVOKE**: concede o retira permisos.
* **WITH ADMIN OPTION**: permite que el usuario conceda privilegios a otros.
* **PUBLIC**: privilegio válido para todos los usuarios.

---

### En resumen

El modelo relacional organiza los datos en tablas relacionadas mediante claves, gestionadas por un SGBD y manipuladas a través del lenguaje SQL, que combina definición (DDL), manipulación (DML) y control (DCL) de datos, garantizando integridad, eficiencia y seguridad.
