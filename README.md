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

# Guía de Comandos SQL - MySQL

Una guía detallada de los comandos más utilizados en MySQL con explicaciones y ejemplos prácticos.

## Índice
- [CREATE TABLE](#create-table)
- [INSERT](#insert)
- [SELECT](#select)
- [UPDATE](#update)
- [DELETE](#delete)
- [ALTER TABLE](#alter-table)
- [DROP TABLE](#drop-table)

## CREATE TABLE

### Descripción
El comando CREATE TABLE se utiliza para crear una nueva tabla en la base de datos. Define la estructura de la tabla, incluyendo nombres de columnas, tipos de datos y restricciones.

### Sintaxis Básica
```sql
CREATE TABLE nombre_tabla (
    columna1 tipo_dato1 [restricciones],
    columna2 tipo_dato2 [restricciones],
    ...
);
```

### Ejemplo Práctico
```sql
CREATE TABLE empleados (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE,
    salario DECIMAL(10,2),
    fecha_contrato DATE
);
```

### CREATE TABLE IF NOT EXISTS

#### Descripción
Esta variante evita errores si la tabla ya existe. Es útil en scripts que pueden ejecutarse múltiples veces.

#### Sintaxis
```sql
CREATE TABLE IF NOT EXISTS nombre_tabla (
    columna1 tipo_dato1 [restricciones],
    columna2 tipo_dato2 [restricciones],
    ...
);
```

#### Ejemplo
```sql
CREATE TABLE IF NOT EXISTS productos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100) NOT NULL,
    precio DECIMAL(8,2),
    stock INT DEFAULT 0
);
```

## INSERT

### Descripción
El comando INSERT se utiliza para agregar nuevos registros a una tabla.

### INSERT INTO ... VALUES

#### Descripción
Forma básica de insertar un solo registro o múltiples registros.

#### Sintaxis
```sql
INSERT INTO tabla (columna1, columna2, ...)
VALUES (valor1, valor2, ...);
```

#### Ejemplo
```sql
INSERT INTO empleados (nombre, email, salario)
VALUES ('Juan Pérez', 'juan@email.com', 30000.00);
```

### INSERT INTO ... SELECT

#### Descripción
Permite insertar datos desde otra tabla o consulta.

#### Sintaxis
```sql
INSERT INTO tabla1 (columna1, columna2, ...)
SELECT columna1, columna2, ...
FROM tabla2
WHERE condicion;
```

#### Ejemplo
```sql
INSERT INTO empleados_backup (nombre, email, salario)
SELECT nombre, email, salario
FROM empleados
WHERE fecha_contrato < '2023-01-01';
```

## SELECT

### Descripción
El comando SELECT se utiliza para recuperar datos de una o más tablas.

### SELECT Básico

#### Sintaxis
```sql
SELECT columna1, columna2
FROM tabla
WHERE condicion;
```

#### Ejemplo
```sql
SELECT nombre, salario
FROM empleados
WHERE salario > 25000;
```

### SELECT con JOIN

#### Descripción
Permite combinar datos de múltiples tablas.

#### Ejemplo
```sql
SELECT e.nombre, d.nombre_departamento
FROM empleados e
INNER JOIN departamentos d ON e.departamento_id = d.id;
```

## ALTER TABLE

### Descripción
ALTER TABLE se utiliza para modificar la estructura de una tabla existente.

### Agregar Columna

#### Sintaxis
```sql
ALTER TABLE tabla
ADD COLUMN nueva_columna tipo_dato [restricciones];
```

#### Ejemplo
```sql
ALTER TABLE empleados
ADD COLUMN telefono VARCHAR(15);
```

### Modificar Columna

#### Sintaxis
```sql
ALTER TABLE tabla
MODIFY COLUMN columna nuevo_tipo_dato [restricciones];
```

#### Ejemplo
```sql
ALTER TABLE empleados
MODIFY COLUMN telefono VARCHAR(20) NOT NULL;
```

## DROP TABLE

### Descripción
DROP TABLE elimina una tabla y todos sus datos de la base de datos.

### Sintaxis Básica
```sql
DROP TABLE nombre_tabla;
```

### DROP TABLE IF EXISTS

#### Descripción
Elimina la tabla solo si existe, evitando errores.

#### Sintaxis
```sql
DROP TABLE IF EXISTS nombre_tabla;
```

#### Ejemplo
```sql
DROP TABLE IF EXISTS empleados_temp;
```

## UPDATE

### Descripción
UPDATE modifica registros existentes en una tabla.

### Sintaxis
```sql
UPDATE tabla
SET columna1 = valor1, columna2 = valor2
WHERE condicion;
```

### Ejemplo
```sql
UPDATE empleados
SET salario = salario * 1.10
WHERE fecha_contrato < '2023-01-01';
```

## DELETE

### Descripción
DELETE elimina registros de una tabla.

### Sintaxis
```sql
DELETE FROM tabla
WHERE condicion;
```

### Ejemplo
```sql
DELETE FROM empleados
WHERE fecha_contrato < '2020-01-01';
```
