# Conceptos clave y aprendizajes técnicos – BDDA02: Restaurante de Mascotas

### 📘 Modelo relacional

* El modelo relacional organiza los datos en **tablas (entidades)** y define **relaciones** entre ellas mediante claves primarias y foráneas.
* Cada tabla representa una entidad o relación del dominio del problema; los campos se eligen según las características relevantes de cada entidad.
* Las **claves primarias (PK)** garantizan la unicidad de cada fila. Las **claves foráneas (FK)** enlazan registros de distintas tablas, asegurando **integridad referencial**.
* El diseño relacional busca minimizar redundancias y cumplir las formas normales básicas (1FN–3FN) para evitar inconsistencias.

### 🧩 Lenguaje DDL (Data Definition Language)

* `CREATE TABLE` define la estructura de las tablas y las restricciones asociadas.
* `DROP TABLE ... CASCADE CONSTRAINTS` elimina tablas junto con sus dependencias.
* `ALTER TABLE` se usa para modificar estructuras existentes o añadir restricciones.
* Restricciones más comunes:

  * `NOT NULL`: impide valores vacíos.
  * `PRIMARY KEY`: identifica unívocamente cada registro.
  * `FOREIGN KEY`: establece relaciones entre tablas.
  * `CHECK`: valida condiciones lógicas sobre los valores.
  * `DEFAULT`: asigna valores automáticos por omisión.

### ⚙️ Diseño de la base de datos del proyecto

* Entidades principales: **duenios**, **mascotas**, **platos**, **reservas**, **pedidos**, **eventos**.
* Relaciones:

  * Un dueño tiene muchas mascotas.
  * Una mascota puede realizar varias reservas.
  * Una reserva puede incluir múltiples pedidos.
  * Un pedido pertenece a un plato concreto.
* Los eventos se gestionan como entidad independiente, asociada a especies protagonistas.
* Los tipos de datos se eligieron en función de la naturaleza del atributo: `NUMBER` para identificadores y cantidades, `VARCHAR2` para texto, `DATE` para fechas.

### 🧠 Uso de Oracle SQL Developer y Data Modeler

* **SQL Developer** permite ejecutar scripts, validar resultados y visualizar la estructura del esquema.
* **Data Modeler** genera automáticamente el diagrama entidad–relación a partir de las tablas existentes.
* Las relaciones y dependencias se representan visualmente, lo que ayuda a validar la integridad del diseño.

### 🧾 Buenas prácticas en el modelado y documentación

* Utilizar una nomenclatura coherente (minúsculas, `snake_case`, sin tildes ni espacios) mejora la legibilidad y la compatibilidad con SQL.
* Incluir comentarios explicativos en los scripts facilita su comprensión y mantenimiento.
* Verificar cada tabla individualmente (`SELECT * FROM tabla;`) confirma que las estructuras están creadas correctamente antes de continuar con otras dependientes.
* Documentar el proceso mediante un PDF o README consolidado ayuda a revisar decisiones de diseño en el futuro.

### 🔍 Puntos clave para revisión futura

* Reforzar la comprensión del proceso de normalización y su impacto en la integridad de los datos.
* Profundizar en el uso de `ALTER TABLE` para modificaciones estructurales posteriores.
* Experimentar con índices y vistas (`CREATE INDEX`, `CREATE VIEW`) para optimizar consultas.
* Usar Data Modeler o Draw.io para validar gráficamente relaciones complejas.
* Mantener una estrategia de pruebas incremental: crear, verificar, relacionar y documentar cada paso.
