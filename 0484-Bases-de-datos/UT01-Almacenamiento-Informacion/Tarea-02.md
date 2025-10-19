# UT1 BD01 - Preguntas y Respuestas

## Contexto del caso práctico

Un colegio necesita gestionar información relacionada con **libros de gratuidad, servicio de comedor y autobús escolar**. Actualmente realizan todos los trámites manualmente mediante fichas en papel, lo que provoca desorden, duplicidad de datos y dificultad para acceder a la información. Quieren informatizar el sistema creando una **base de datos** que permita almacenar:

* Datos del alumnado y sus familias.
* Uso del servicio de autobús (incluyendo parada).
* Uso del comedor (fiambrera o menú).
* Estado y seguimiento de libros (histórico de alumnos por libro y posibles desperfectos).
* Gestión de tasas económicas asociadas.

El tutor añadirá información al inicio de curso y actualizará el estado de los libros al final. Secretaría gestionará datos bancarios y modificaciones de comedor o transporte. Otra persona desarrollará una **web sencilla** conectada a esta base de datos para facilitar la gestión.

## 1. ¿Qué modelo de base de datos utilizarías para desarrollarla?

El modelo más adecuado es el **modelo relacional**. Permite organizar la información en tablas relacionadas y garantiza coherencia, integridad y facilidad en las consultas mediante SQL. Es el estándar más utilizado en sistemas de gestión con datos estructurados como alumnos, familias, servicios de comedor y transporte.

## 2. ¿Cómo clasificarías esta base de datos según los tipos vistos en teoría?

Siguiendo las clasificaciones estudiadas:

* **Según su variabilidad:** Base de datos dinámica (se actualiza durante el curso).
* **Según su contenido:** Base de datos operacional o transaccional.
* **Según su ubicación:** Centralizada (se usa en un único centro escolar).
* **Según acceso de usuarios:** Multiusuario (secretaría, tutor, administración).
* **Según el tiempo:** Actual con histórico (histórico de libros asociados a alumnos).
* **Según su gestión:** Informatizada (gestionada mediante un SGBD).

## 3. Elige un Sistema Gestor de Bases de Datos y explica el motivo. ¿Qué extensiones se usan para importar/exportar?

Se elegiría **MySQL** por ser gratuito, fácil de instalar, multiplataforma y con amplia documentación y soporte. Además, utiliza SQL y es ideal para proyectos educativos o pequeños sistemas de gestión.

Extensiones habituales para importar/exportar:

* `.sql` → estructura y datos completos.
* `.csv` → datos tabulares para hojas de cálculo.
* `.xml` → intercambio estructurado de datos.
* `.json` → intercambio de datos en aplicaciones web.

## 4. ¿Base de datos centralizada o distribuida? Explica tu decisión.

Se utilizaría una **base de datos centralizada** ya que toda la información pertenece a un solo centro educativo. Facilita la administración y reduce costes técnicos. No existe necesidad de replicación ni distribución en varias ubicaciones.

## 5. ¿Cuáles serían los posibles datos constantes en la BD de la escuela?

Los datos constantes, que no cambian con frecuencia, serían:

* Tarifas del comedor.
* Tarifas del transporte escolar.
* Tasas por desperfecto de libros.
* Lista de paradas de autobús.
* Cursos escolares (1º, 2º, 3º...).
* Tipos de servicio de comedor (menú, fiambrera).
* Estados de los libros (nuevo, usado, deteriorado).

## 6. Legislación de protección de datos

**a. ¿Qué ley protege los datos que recogemos?**
El tratamiento de datos está protegido por el **RGPD (Reglamento General de Protección de Datos - UE 2016/679)** y la **LOPDGDD (Ley Orgánica 3/2018 de Protección de Datos Personales y Garantía de los Derechos Digitales)** en España.

**b. ¿Los datos personales tienen algún derecho? ¿Cuáles son?**
Sí, están protegidos por los derechos **ARCO-POL**:

* Acceso
* Rectificación
* Supresión (antes Cancelación)
* Oposición
* Portabilidad
* Olvido
* Limitación del tratamiento

**c. Niveles de seguridad de los datos**
Existen tres niveles de seguridad:

* **Nivel básico:** datos identificativos (nombre, dirección).
* **Nivel medio:** datos académicos o bancarios.
* **Nivel alto:** salud, ideología, religión.

En este caso:

* Datos de alumnos/familias → nivel básico.
* Datos bancarios → nivel medio.
* Notas académicas → nivel medio.
* Datos médicos (alergias) → nivel alto.

## 7. Big Data

El **Big Data** permite gestionar grandes volúmenes de datos provenientes de múltiples fuentes y que cambian con rapidez.

Se define por las **5V**:

* **Volumen** → gran cantidad de datos.
* **Velocidad** → datos generados constantemente.
* **Variedad** → diferentes formatos (texto, audio, vídeo...).
* **Veracidad** → fiabilidad de los datos.
* **Valor** → utilidad que se obtiene tras analizarlos.

**¿Tiene sentido Big Data en este caso?**
No. La cantidad de datos del colegio es pequeña y no requiere herramientas de Big Data. Es suficiente con una base de datos relacional tradicional.
