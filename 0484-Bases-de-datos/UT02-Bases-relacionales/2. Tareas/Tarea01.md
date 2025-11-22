## BDDA02 – Tarea 1: Instalación y conexión SQL Developer

### Contexto

Esta tarea corresponde a la Unidad 2 del módulo de Bases de Datos del ciclo DAW. Se pedía instalar Oracle SQL Developer (versión 23.1.1) y conectar con el usuario personal creado en la UT1, evidenciando el proceso mediante capturas.

---

### Pasos realizados

#### 1. Instalación de Oracle SQL Developer

* Se descargó el paquete oficial desde [oracle.com/database/sqldeveloper](https://www.oracle.com/database/sqldeveloper/technologies/download/), eligiendo la versión para **Windows con JDK incluido**.
* Se descomprimió el archivo `.zip` y se ejecutó `sqldeveloper.exe` con permisos de administrador.
* La aplicación se inició correctamente, detectando el entorno **Oracle Database XE 21c** previamente instalado.
* Se realizó la captura inicial con el entorno abierto y el nombre del alumno visible mediante **Lightshot**.

#### 2. Creación del usuario personal en Oracle XE

* Desde `SQLPlus` (modo administrador):

  ```sql
  sqlplus / as sysdba
  ALTER SESSION SET CONTAINER = XEPDB1;
  CREATE USER alberto IDENTIFIED BY 1234;
  GRANT CONNECT, RESOURCE TO alberto;
  ALTER USER alberto QUOTA UNLIMITED ON USERS;
  ```
* El cambio al contenedor **XEPDB1** fue necesario debido a la arquitectura multitenant de Oracle 21c (el error ORA-65096 lo confirmó).
  Esta adaptación está plenamente alineada con la práctica, ya que mantiene el objetivo de usar un usuario propio dentro del entorno XE.

#### 3. Conexión desde SQL Developer

Configuración utilizada:

```
Usuario: alberto
Contraseña: 1234
Host: localhost
Puerto: 1521
Service Name: XEPDB1
```

* Se seleccionó la opción **Usar Service Name** (en lugar de SID) para evitar el error ORA-12505.
* La prueba de conexión resultó **Correcta**.

#### 4. Verificación mediante consulta SQL

En la hoja de trabajo de SQL Developer se ejecutó:

```sql
SELECT 'Conectado correctamente a Oracle' AS MENSAJE FROM dual;
```

El resultado confirmó el funcionamiento correcto del entorno.

---

### Capturas entregadas

1. **Screenshot_1:** SQL Developer instalado y abierto (verificación de entorno Oracle XE).
2. **Screenshot_2:** Conexión correcta del usuario y ejecución de la consulta de prueba.

---

### Conclusión

La instalación y configuración se completaron correctamente. SQL Developer se conectó con éxito al entorno Oracle XE mediante el contenedor `XEPDB1`. Las dos capturas aportadas demuestran el cumplimiento total de los requisitos establecidos en la tarea BDDA02.
