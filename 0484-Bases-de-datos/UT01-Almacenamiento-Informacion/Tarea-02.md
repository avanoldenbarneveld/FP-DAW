# Instalación y configuración de Oracle Database 21c XE – Guía de referencia

Este documento resume claramente los pasos que hemos seguido para realizar la **Tarea 2: Instalación y configuración de Oracle** del módulo **Bases de Datos (BDDA)** en **FP DAW/DAM**. Además, sirve como referencia rápida para recordar el proceso en el futuro.

---

## Objetivo de la tarea

La tarea consiste en instalar el sistema gestor de bases de datos **Oracle Database 21c Express Edition (XE)**, acceder al sistema mediante **SQLPLUS** y crear un nuevo usuario. El trabajo se divide en tres apartados obligatorios:

1. Instalación de Oracle Database 21c XE
2. Acceso al usuario administrador desde SQLPLUS
3. Creación de un usuario común en Oracle

Cada paso debe incluir capturas de pantalla y una breve explicación para demostrar que se comprendió el proceso.

---

## Apartado 1: Instalación de Oracle Database 21c XE

### ¿Qué hemos hecho?

1. Entramos en la web oficial de Oracle y descargamos la versión **Oracle Database 21c Express Edition para Windows x64**.
2. Ejecutamos el instalador `OracleXE213_Win64.exe`.
3. Durante la instalación, seleccionamos carpeta por defecto y establecimos la contraseña para el usuario administrador `SYS`.
4. Terminamos la instalación correctamente.

### ¿Para qué sirve?

Este paso instala el sistema de base de datos Oracle en el ordenador. A partir de aquí, podemos crear usuarios, bases de datos y trabajar con SQL.

---

## Apartado 2: Acceso al usuario administrador desde SQLPLUS

### ¿Qué hemos hecho?

1. Abrimos **Símbolo del sistema (CMD)** como administrador.
2. Nos conectamos a Oracle con el usuario administrador usando:

   ```
   sqlplus / as sysdba
   ```
3. Comprobamos qué usuario está conectado y en qué contenedor estamos trabajando usando:

   ```
   show user;
   show con_name;
   ```

### ¿Qué comprobamos aquí?

Vimos que:

* El usuario activo era `SYS` (administrador de Oracle).
* El contenedor activo era `CDB$ROOT` (contenedor raíz de la base de datos).

---

## Apartado 3: Creación de un usuario desde SQLPLUS

### ¿Qué hemos hecho?

1. Creamos un nuevo usuario común en Oracle con nuestro nombre (obligatorio en la tarea):

   ```
   create user c##alberto identified by alberto;
   ```
2. Le dimos permisos básicos para poder conectarse y trabajar:

   ```
   grant connect, resource to c##alberto;
   ```
3. Cerramos la sesión del administrador y probamos acceder con el nuevo usuario:

   ```
   exit;
   sqlplus c##alberto/alberto
   ```
4. Confirmamos que la conexión funcionaba correctamente usando otra vez `show user` y `show con_name`.

### ¿Qué aprendimos aquí?

* Oracle XE requiere que los **usuarios comunes** empiecen por **`c##`**.
* El usuario `SYS` es el administrador y es el único que puede crear otros usuarios.
* Para trabajar en Oracle debemos conceder permisos explícitamente a cada usuario.

---

## Archivos y comandos importantes

### Comandos de SQLPLUS utilizados

```
sqlplus / as sysdba
show user;
show con_name;
create user c##alberto identified by alberto;
grant connect, resource to c##alberto;
exit;
sqlplus c##alberto/alberto
```

### Estructura obligatoria de capturas de la tarea

1. Descarga de Oracle 21c XE
2. Instalación completada
3. Conexión como administrador SYS
4. Mostrar usuario y contenedor activo
5. Creación del usuario nuevo
6. Conexión con el usuario creado

---

## Notas para futuras tareas

* El usuario `SYS` solo debe usarse para administración, nunca para trabajar con bases de datos.
* Cada usuario nuevo necesita permisos para poder crear tablas y conectarse.
* Oracle XE trabaja con contenedores (`CDB$ROOT`, `PDB$SEED`, etc.).
* SQLPLUS es la herramienta básica de línea de comandos para trabajar con Oracle.

---

## Próximos pasos

Después de esta tarea, en siguientes prácticas comenzaremos a:

* Crear tablas y estructuras de base de datos
* Insertar y consultar datos con SQL
* Trabajar con restricciones (PRIMARY KEY, FOREIGN KEY, etc.)
* Gestionar privilegios y roles

---

Este documento sirve como referencia rápida para repasar todo el proceso cuando sea necesario. Se recomienda guardarlo y revisarlo antes de futuros ejercicios o exámenes relacionados con Oracle.
