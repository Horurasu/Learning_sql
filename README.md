# Aprendiendo SQL

SQL, o Lenguaje de Consulta Estructurado (Structured Query Language), es un lenguaje de programación usado para comunicarse con bases de datos y gestionarlas. SQL es el lenguaje estándar para manipular datos en sistemas de gestión de bases de datos relacionales (RDBMS) o para el procesamiento de flujos en un sistema de gestión de flujo de datos relacional (RDSMS). Fue desarrollado por IBM en los años 70.

## Componentes de SQL

SQL está compuesto por varios elementos, cada uno con un propósito específico en la comunicación con bases de datos:

- **Consultas (Queries):** Permiten recuperar datos de una base de datos. El comando `SELECT` es el más usado para esta tarea.
- **Lenguaje de Definición de Datos (DDL):** Permite crear, modificar o eliminar bases de datos y objetos como tablas y vistas. Comandos principales: `CREATE`, `ALTER`, `DROP`, `TRUNCATE`.
- **Lenguaje de Manipulación de Datos (DML):** Permite gestionar datos dentro de los objetos de la base de datos. Incluye los comandos `SELECT`, `INSERT`, `UPDATE`, `DELETE`.
- **Lenguaje de Control de Datos (DCL):** Incluye comandos como `GRANT` y `REVOKE`, que gestionan permisos y control de acceso en la base de datos.

## ¿Qué son las Bases de Datos Relacionales?

Las bases de datos relacionales almacenan y proporcionan acceso a puntos de datos relacionados entre sí. Basadas en el modelo relacional de E.F. Codd (1970), estas bases organizan la información en tablas con filas y columnas. Características clave:

- Uso de SQL para consultar y gestionar datos.
- Soporte para transacciones ACID (Atomicidad, Consistencia, Aislamiento, Durabilidad).
- Mantenimiento de la integridad de datos mediante restricciones (por ejemplo, claves primarias y foráneas).
- Capacidad para establecer relaciones entre tablas, permitiendo consultas complejas.
- Escalabilidad y soporte para entornos multiusuario.

Ejemplos de sistemas de bases de datos relacionales: MySQL, PostgreSQL, Oracle, y Microsoft SQL Server.

## Ventajas y Limitaciones de RDBMS

### Ventajas

- **Datos Estructurados:** Permite almacenar datos en una estructura organizada de filas y columnas.
- **Propiedades ACID**:
  - **A**tomacidad (Atomicity): Una transacción es indivisible; ocurre completa o no ocurre.
  - **C**onsistencia (Consistency): La base de datos siempre pasa de un estado válido a otro.
  - **I**solamiento (Isolation): Las transacciones no interfieren entre sí.
  - **D**urabilidad (Durability): Los cambios se guardan permanentemente.
- **Normalización:** Reduce la redundancia de datos y mejora su integridad.
- **Escalabilidad:** Permite agregar recursos conforme crece la carga de trabajo.
- **Integridad de Datos:** Uso de restricciones para garantizar la precisión y confiabilidad.
- **Seguridad:** Autenticación, control de acceso y cifrado de datos.

### Limitaciones

- **Complejidad:** Configuración y gestión complejas, especialmente para aplicaciones grandes.
- **Costo:** Puede ser caro en términos de licencias y recursos necesarios.
- **Esquema Fijo:** Requiere una estructura rígida de datos, difícil de cambiar.
- **Datos no Estructurados:** No es adecuado para datos no estructurados (como archivos multimedia).
- **Escalabilidad Horizontal:** No tan fácil de escalar horizontalmente como las bases de datos NoSQL.

## SQL vs NoSQL

Las bases de datos SQL y NoSQL representan dos enfoques distintos. Las bases de datos SQL tienen esquemas estructurados y usan tablas, enfatizando la integridad de datos y consultas complejas. Por otro lado, las bases de datos NoSQL ofrecen mayor flexibilidad en estructuras de datos, a menudo sacrificando algo de consistencia para mejorar escalabilidad y rendimiento. La elección depende de factores como la estructura de datos, necesidades de escalabilidad y requerimientos de consistencia.

## Sintaxis Básica de SQL

La sintaxis básica de SQL incluye comandos esenciales para interactuar con bases de datos relacionales. Entre los comandos fundamentales:

- **SELECT**: Recupera datos de la base de datos.
- **INSERT INTO**: Añade nuevos registros.
- **UPDATE**: Modifica datos existentes.
- **DELETE**: Elimina registros.

Los comandos `WHERE` (filtrar), `ORDER BY` (ordenar) y `JOIN` (combinar datos de múltiples tablas) permiten manipular y consultar datos de forma eficiente.

## Palabras Clave en SQL

Las palabras clave en SQL son términos reservados con significados especiales dentro de las consultas. Incluyen:

- **Comandos:** `SELECT`, `INSERT`, `UPDATE`
- **Cláusulas:** `WHERE`, `GROUP BY`, `HAVING`
  
Escribir las palabras clave en mayúsculas mejora la legibilidad y es una convención común en SQL.

## Tipos de Datos en SQL

Los tipos de datos en SQL definen el tipo de valores que pueden almacenarse en una columna y determinan cómo se almacenan, procesan y recuperan. Tipos comunes incluyen:

- **Numéricos:** `INTEGER`, `DECIMAL`
- **Caracteres:** `CHAR`, `VARCHAR`
- **Fecha y Hora:** `DATE`, `TIMESTAMP`
- **Binarios:** `BLOB`
- **Booleanos**

## Operadores en SQL

Los operadores en SQL permiten realizar operaciones en los datos de una base de datos. Tipos comunes:

- **Aritméticos:** `+`, `-`, `*`, `/`
- **De Comparación:** `=`, `!=`, `<`, `>`
- **Lógicos:** `AND`, `OR`, `NOT`
- **De Conjunto:** `UNION`, `INTERSECT`, `EXCEPT`

Estos operadores facilitan el control preciso sobre la recuperación y modificación de datos.

## Comandos Básicos en MySQL

### Iniciar MySQL

Para iniciar el servidor MySQL en un sistema compatible, se suele ejecutar el siguiente comando en la terminal (CMD, BASH, POWERSHELL, SHELL, etc):

```bash
 mysql -u root -p
```

