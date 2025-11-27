# 📘 Aprendizajes clave – BDDA02 · Tarea 3

Referencia rápida para revisar antes del examen.

---

## 🔹 Modelo relacional y conceptos básicos

* Relación = tabla; tuplas = filas; dominio = tipo de dato permitido.
* Grado = número de columnas de una tabla.
* Cardinalidad = cantidad de filas.
* Tipos de claves:

  * **Clave primaria (PK)** → identifica un registro.
  * **Claves candidatas** → posibles PK.
  * **Clave alternativa** → clave candidata no elegida como PK.
  * **Clave externa (FK)** → referencia a otra tabla , mantiene integridad.
* Valor **NULL** = ausencia de dato; cuidado con operaciones y restricciones.

---

## 🔹 DDL (Data Definition Language) que debo controlar

* `CREATE DATABASE / TABLE` → creación inicial.
* `ALTER TABLE` → fundamental para modificaciones.

  * `ADD COLUMN` → añadir atributos.
  * `DROP COLUMN` → eliminar atributos.
  * `RENAME` → renombrar tablas o columnas.
  * `ADD CONSTRAINT` / `DROP CONSTRAINT` → manejo de reglas.
  * `MODIFY` → cambiar estructura o tipos.
* `DROP TABLE` → elimina por completo una tabla.

📌 Ejemplos de la tarea — muy probables en examen:

* Eliminar columna: `ALTER TABLE mascotas DROP COLUMN edad;` fileciteturn0file2
* Renombrar tabla: `ALTER TABLE duenios RENAME TO cuidadores;` fileciteturn0file2
* Añadir columna: `ALTER TABLE cuidadores ADD tarjeta_credito VARCHAR2(30);` fileciteturn0file2
* Añadir restricción CHECK (límite calorías): `CHECK (calorias <= 1000);` fileciteturn0file2
* Eliminar constraint con `DROP CONSTRAINT`.

---

## 🔹 Tipos de restricciones esenciales

| Restricción                | Función clave                    |
| -------------------------- | -------------------------------- |
| `NOT NULL`                 | evita valores vacíos             |
| `UNIQUE`                   | no permite duplicados            |
| `PRIMARY KEY`              | UNIQUE + NOT NULL                |
| `FOREIGN KEY / REFERENCES` | mantiene integridad entre tablas |
| `CHECK`                    | valida valores con condiciones   |
| `DEFAULT`                  | valor por defecto                |

💡 Tener MUY claro cómo se viola cada una:

* PK duplicada (ORA-00001) fileciteturn0file1
* CHECK incorrecto (ORA-02290) fileciteturn0file1
* NOT NULL con NULL → ORA-01400 fileciteturn0file1
* FK sin referencia válida → ORA-02291 fileciteturn0file1

---

## 🔹 DCL (Data Control Language)

Crear usuarios + asignar permisos según rol:

```sql
CREATE USER nombre IDENTIFIED BY contraseña;
GRANT SELECT, INSERT, UPDATE, DELETE ON tabla TO usuario;
```

Roles de la tarea (importante para preguntas teóricas):

* **Gerente** → CRUD en MASCOTAS, CUIDADORES, RESERVAS, PEDIDOS.
* **Camarero** → CRUD solo en RESERVAS y PEDIDOS.
* **Responsable_eventos** → CRUD en EVENTOS + UPDATE en PLATOS.
* **Cocinero** → CRUD total en PLATOS.

---

## 🔹 Exportación de la base de datos

* Se genera un `.sql` con estructura completa del esquema.
* Verificar que contiene restricciones, FK, PK, nombres actualizados.
* Comprobar que refleja cambios finales.

---

## 🔹 Normalización y diseño

* Si aparece un nuevo requisito → revisar si el modelo lo cubre.
* Ejemplo del caso: relación **muchos a muchos** Camareros ↔ Mascotas
  → tabla intermedia `asignaciones()`.

> Punto clave para examen: **saber proponer/rediseñar tablas según nuevas necesidades.**

---

## 🎯 Qué repasar sí o sí antes del examen

* Sintaxis ALTER + creación y eliminación de restricciones.
* Tipos de claves y restricciones con ejemplos.
* Violación de integridad referencial (FK) y PRIMARY KEY.
* CHECK y NOT NULL (cómo fallan, cómo se aplican).
* Comandos GRANT / creación de usuarios.
* Tablas para relaciones muchos a muchos.
