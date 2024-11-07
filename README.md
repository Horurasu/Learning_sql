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
---
---
---
# Guía SQL Básica

## SQL Statements (Declaraciones SQL)

**¿Qué son los Statements?**
Los statements son comandos que indican a la base de datos qué acción realizar. Son las instrucciones básicas que usamos para interactuar con la base de datos, ya sea para consultar, insertar, modificar o eliminar datos.

### Tipos principales de Statements:

#### 1. SELECT Statement
**¿Qué es?** 
Es el comando para recuperar datos de una o más tablas.

**¿Para qué se usa?**
- Consultar información específica
- Filtrar registros según condiciones
- Ordenar resultados
- Agrupar datos

**Sintaxis básica:**
```sql
SELECT columnas FROM tabla WHERE condicion;
```

**Ejemplos explicados:**
```sql
-- Obtener todos los usuarios
SELECT * FROM usuarios;

-- Obtener nombres y emails específicos
SELECT nombre, email 
FROM usuarios 
WHERE edad > 18;

-- Ordenar resultados
SELECT nombre, edad 
FROM usuarios 
ORDER BY edad DESC;
```

#### 2. INSERT Statement
**¿Qué es?**
Comando para agregar nuevos registros a una tabla.

**¿Para qué se usa?**
- Añadir un nuevo registro
- Añadir múltiples registros
- Copiar datos de otra tabla

**Sintaxis básica:**
```sql
INSERT INTO tabla (columnas) VALUES (valores);
```

**Ejemplos explicados:**
```sql
-- Insertar un usuario nuevo
INSERT INTO usuarios (nombre, email) 
VALUES ('Juan', 'juan@email.com');

-- Insertar varios usuarios a la vez
INSERT INTO usuarios (nombre, email) VALUES 
    ('Ana', 'ana@email.com'),
    ('Pedro', 'pedro@email.com');
```

#### 3. UPDATE Statement
**¿Qué es?**
Comando para modificar registros existentes en una tabla.

**¿Para qué se usa?**
- Actualizar datos existentes
- Modificar múltiples registros
- Corregir información

**Sintaxis básica:**
```sql
UPDATE tabla SET columna = valor WHERE condicion;
```

**Ejemplos explicados:**
```sql
-- Actualizar la edad de un usuario
UPDATE usuarios 
SET edad = 25 
WHERE nombre = 'Juan';

-- Actualizar múltiples campos
UPDATE usuarios 
SET 
    edad = 25,
    ciudad = 'Madrid' 
WHERE nombre = 'Juan';
```

#### 4. DELETE Statement
**¿Qué es?**
Comando para eliminar registros de una tabla.

**¿Para qué se usa?**
- Eliminar registros específicos
- Limpiar datos obsoletos
- Mantener la base de datos actualizada

**Sintaxis básica:**
```sql
DELETE FROM tabla WHERE condicion;
```

**Ejemplos explicados:**
```sql
-- Eliminar un usuario específico
DELETE FROM usuarios 
WHERE nombre = 'Juan';

-- Eliminar usuarios por condición
DELETE FROM usuarios 
WHERE edad < 18;
```

## Operadores en SQL

**¿Qué son los operadores?**
Son símbolos o palabras que permiten realizar comparaciones y operaciones lógicas en las consultas SQL.

### 1. Operadores de Comparación
**¿Para qué sirven?**
Comparan valores y devuelven verdadero o falso.

```sql
-- Igual a (=)
SELECT * FROM usuarios WHERE edad = 25;
-- Busca usuarios que tengan exactamente 25 años

-- Mayor que (>)
SELECT * FROM productos WHERE precio > 100;
-- Busca productos que cuesten más de 100

-- Menor que (<)
SELECT * FROM inventario WHERE stock < 10;
-- Busca productos con menos de 10 unidades
```

### 2. Operadores Lógicos
**¿Para qué sirven?**
Combinan múltiples condiciones en una consulta.

```sql
-- AND: Ambas condiciones deben ser verdaderas
SELECT * FROM usuarios 
WHERE edad > 18 AND ciudad = 'Madrid';
-- Busca usuarios mayores de 18 años que vivan en Madrid

-- OR: Al menos una condición debe ser verdadera
SELECT * FROM productos 
WHERE categoria = 'Electrónica' OR categoria = 'Computación';
-- Busca productos de electrónica o computación
```

## Palabras Clave (Keywords)

**¿Qué son las Keywords?**
Son palabras reservadas que tienen un significado especial en SQL y no pueden usarse como nombres de tablas o columnas.

### Keywords Principales:
```sql
SELECT    -- Para seleccionar datos
FROM      -- Para especificar la tabla fuente
WHERE     -- Para filtrar registros
ORDER BY  -- Para ordenar resultados
GROUP BY  -- Para agrupar registros
HAVING    -- Para filtrar grupos
```

## Tipos de Datos

**¿Qué son los tipos de datos?**
Definen qué tipo de información puede almacenar cada columna en una tabla.

### 1. Tipos Numéricos
```sql
INT           -- Para números enteros
DECIMAL(10,2) -- Para números con decimales
FLOAT         -- Para números decimales aproximados
```

### 2. Tipos de Texto
```sql
CHAR(10)      -- Texto de longitud fija
VARCHAR(100)  -- Texto de longitud variable
TEXT          -- Texto largo
```

### 3. Tipos de Fecha/Hora
```sql
DATE          -- Solo fecha
TIME          -- Solo hora
DATETIME      -- Fecha y hora
```

# Data Definition Language (DDL)

## ¿Qué es DDL?
DDL son los comandos SQL utilizados para crear, modificar y eliminar estructuras de base de datos (como tablas, índices, etc.). Es el "lenguaje" que usamos para definir cómo se almacenarán los datos.

## Comandos Principales DDL

### 1. CREATE
**¿Qué es?** 
Comando para crear nuevos objetos en la base de datos.

#### CREATE DATABASE
**¿Para qué sirve?**
Crear una nueva base de datos.

```sql
-- Crear base de datos simple
CREATE DATABASE tienda;

-- Crear base de datos si no existe
CREATE DATABASE IF NOT EXISTS tienda;

-- Crear base de datos especificando charset
CREATE DATABASE tienda
CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;
```

#### CREATE TABLE
**¿Para qué sirve?**
Crear una nueva tabla con sus columnas y restricciones.

```sql
-- Tabla básica
CREATE TABLE usuarios (
    id INT,
    nombre VARCHAR(50)
);

-- Tabla con restricciones
CREATE TABLE productos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100) NOT NULL,
    precio DECIMAL(10,2) NOT NULL,
    descripcion TEXT,
    fecha_creacion DATETIME DEFAULT CURRENT_TIMESTAMP
);

-- Tabla con claves foráneas
CREATE TABLE pedidos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    usuario_id INT,
    fecha DATE,
    total DECIMAL(10,2),
    FOREIGN KEY (usuario_id) REFERENCES usuarios(id)
);
```

#### CREATE INDEX
**¿Para qué sirve?**
Crear índices para optimizar búsquedas.

```sql
-- Índice simple
CREATE INDEX idx_nombre 
ON usuarios(nombre);

-- Índice único
CREATE UNIQUE INDEX idx_email 
ON usuarios(email);

-- Índice compuesto
CREATE INDEX idx_nombre_email 
ON usuarios(nombre, email);
```

### 2. ALTER
**¿Qué es?**
Comando para modificar la estructura de objetos existentes.

#### ALTER TABLE
**¿Para qué sirve?**
Modificar la estructura de una tabla existente.

```sql
-- Agregar columna
ALTER TABLE usuarios
ADD COLUMN telefono VARCHAR(15);

-- Agregar columna con restricciones
ALTER TABLE usuarios
ADD COLUMN edad INT CHECK (edad >= 18);

-- Modificar columna
ALTER TABLE usuarios
MODIFY COLUMN nombre VARCHAR(100) NOT NULL;

-- Eliminar columna
ALTER TABLE usuarios
DROP COLUMN telefono;

-- Agregar clave foránea
ALTER TABLE pedidos
ADD FOREIGN KEY (usuario_id) 
REFERENCES usuarios(id);

-- Renombrar tabla
ALTER TABLE usuarios
RENAME TO clientes;
```

### 3. DROP
**¿Qué es?**
Comando para eliminar objetos de la base de datos.

**¿Para qué sirve?**
Eliminar tablas, bases de datos, índices u otros objetos.

```sql
-- Eliminar base de datos
DROP DATABASE tienda;

-- Eliminar base de datos si existe
DROP DATABASE IF EXISTS tienda;

-- Eliminar tabla
DROP TABLE usuarios;

-- Eliminar tabla si existe
DROP TABLE IF EXISTS usuarios;

-- Eliminar índice
DROP INDEX idx_nombre ON usuarios;
```

### 4. TRUNCATE
**¿Qué es?**
Comando para eliminar todos los registros de una tabla.

**¿Para qué sirve?**
Vaciar una tabla de manera más eficiente que DELETE.

```sql
-- Vaciar tabla
TRUNCATE TABLE usuarios;

-- Vaciar tabla si existe
TRUNCATE TABLE IF EXISTS usuarios;
```

## Ejemplos Prácticos Combinados

### Crear una Base de Datos Completa
```sql
-- Crear base de datos
CREATE DATABASE IF NOT EXISTS tienda_online;

-- Usar la base de datos
USE tienda_online;

-- Crear tabla de categorías
CREATE TABLE categorias (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(50) NOT NULL,
    descripcion TEXT,
    activo BOOLEAN DEFAULT true
);

-- Crear tabla de productos
CREATE TABLE productos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100) NOT NULL,
    precio DECIMAL(10,2) NOT NULL,
    categoria_id INT,
    stock INT DEFAULT 0,
    fecha_creacion DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (categoria_id) REFERENCES categorias(id)
);

-- Agregar índices
CREATE INDEX idx_producto_nombre ON productos(nombre);
CREATE INDEX idx_producto_categoria ON productos(categoria_id);
```

### Modificar Estructura Existente
```sql
-- Agregar nuevas columnas a productos
ALTER TABLE productos
ADD COLUMN marca VARCHAR(50),
ADD COLUMN peso DECIMAL(5,2);

-- Modificar columna existente
ALTER TABLE productos
MODIFY COLUMN nombre VARCHAR(150) NOT NULL;

-- Agregar restricción
ALTER TABLE productos
ADD CONSTRAINT chk_precio 
CHECK (precio > 0);
```

## Buenas Prácticas DDL

1. **Nombres de Objetos**
   - Usar nombres descriptivos
   - Evitar palabras reservadas
   - Usar minúsculas y guiones bajos
   - Ser consistente en la nomenclatura

2. **Restricciones**
   - Nombrar las restricciones explícitamente
   - Usar tipos de datos apropiados
   - Definir claves primarias siempre
   - Usar FOREIGN KEY para mantener integridad

3. **Índices**
   - Crear índices para campos de búsqueda frecuente
   - No excederse en la cantidad de índices
   - Nombrar índices de manera descriptiva

4. **Modificaciones**
   - Hacer backup antes de modificaciones importantes
   - Usar IF EXISTS para evitar errores
   - Probar en ambiente de desarrollo primero

# Data Manipulation Language (DML)

## ¿Qué es DML?
Son los comandos SQL utilizados para manipular los datos dentro de las tablas. Permiten consultar, insertar, modificar y eliminar registros.

## Comandos Principales DML

### 1. SELECT
**¿Qué es?**
Comando para consultar y recuperar datos de una o más tablas.

#### SELECT Básico
```sql
-- Seleccionar todas las columnas
SELECT * FROM usuarios;

-- Seleccionar columnas específicas
SELECT nombre, email FROM usuarios;

-- Seleccionar con alias
SELECT 
    nombre AS nombre_cliente,
    email AS correo_electronico
FROM usuarios;
```

#### SELECT con WHERE
**¿Para qué sirve?**
Filtrar registros según condiciones específicas.

```sql
-- Filtro simple
SELECT * FROM productos 
WHERE precio > 100;

-- Múltiples condiciones
SELECT * FROM productos 
WHERE precio > 100 AND categoria = 'Electrónica';

-- Condiciones con OR
SELECT * FROM productos 
WHERE categoria = 'Electrónica' OR categoria = 'Computación';

-- Búsqueda de texto
SELECT * FROM usuarios 
WHERE nombre LIKE 'Juan%';
```

#### SELECT con ORDER BY
**¿Para qué sirve?**
Ordenar los resultados.

```sql
-- Orden ascendente (predeterminado)
SELECT * FROM productos 
ORDER BY precio;

-- Orden descendente
SELECT * FROM productos 
ORDER BY precio DESC;

-- Múltiples columnas
SELECT * FROM productos 
ORDER BY categoria, precio DESC;
```

#### SELECT con JOIN
**¿Para qué sirve?**
Combinar datos de múltiples tablas.

```sql
-- INNER JOIN
SELECT 
    p.nombre AS producto,
    c.nombre AS categoria
FROM productos p
INNER JOIN categorias c ON p.categoria_id = c.id;

-- LEFT JOIN
SELECT 
    u.nombre AS usuario,
    p.id AS id_pedido
FROM usuarios u
LEFT JOIN pedidos p ON u.id = p.usuario_id;

-- Multiple JOIN
SELECT 
    u.nombre AS usuario,
    p.id AS pedido,
    pr.nombre AS producto
FROM usuarios u
INNER JOIN pedidos p ON u.id = p.usuario_id
INNER JOIN productos pr ON p.producto_id = pr.id;
```

### 2. INSERT
**¿Qué es?**
Comando para agregar nuevos registros a una tabla.

#### INSERT Simple
```sql
-- Insertar un registro
INSERT INTO usuarios (nombre, email) 
VALUES ('Juan Pérez', 'juan@email.com');

-- Insertar múltiples registros
INSERT INTO usuarios (nombre, email) 
VALUES 
    ('Ana López', 'ana@email.com'),
    ('Carlos Ruiz', 'carlos@email.com');
```

#### INSERT con SELECT
**¿Para qué sirve?**
Insertar datos desde otra tabla.

```sql
-- Copiar usuarios a tabla de respaldo
INSERT INTO usuarios_backup 
SELECT * FROM usuarios 
WHERE fecha_registro < '2023-01-01';

-- Insertar datos específicos
INSERT INTO usuarios_premium (nombre, email)
SELECT nombre, email 
FROM usuarios 
WHERE tipo = 'VIP';
```

### 3. UPDATE
**¿Qué es?**
Comando para modificar registros existentes.

#### UPDATE Simple
```sql
-- Actualizar un campo
UPDATE usuarios 
SET status = 'Activo' 
WHERE id = 1;

-- Actualizar múltiples campos
UPDATE usuarios 
SET 
    status = 'Activo',
    ultimo_login = CURRENT_TIMESTAMP
WHERE id = 1;
```

#### UPDATE con JOIN
```sql
-- Actualizar basado en otra tabla
UPDATE productos p
INNER JOIN categorias c ON p.categoria_id = c.id
SET p.precio = p.precio * 1.1
WHERE c.nombre = 'Electrónica';
```

### 4. DELETE
**¿Qué es?**
Comando para eliminar registros de una tabla.

#### DELETE Simple
```sql
-- Eliminar un registro
DELETE FROM usuarios 
WHERE id = 1;

-- Eliminar múltiples registros
DELETE FROM usuarios 
WHERE status = 'Inactivo';
```

#### DELETE con JOIN
```sql
-- Eliminar basado en otra tabla
DELETE p 
FROM productos p
INNER JOIN categorias c ON p.categoria_id = c.id
WHERE c.status = 'Descontinuado';
```

## Ejemplos Prácticos Combinados

### Gestión de una Tienda Online
```sql
-- 1. Insertar nuevo producto
INSERT INTO productos (nombre, precio, categoria_id)
VALUES ('Laptop HP', 999.99, 1);

-- 2. Buscar productos con detalles
SELECT 
    p.nombre AS producto,
    p.precio,
    c.nombre AS categoria,
    p.stock
FROM productos p
INNER JOIN categorias c ON p.categoria_id = c.id
WHERE p.precio < 1000
ORDER BY p.precio DESC;

-- 3. Actualizar stock después de una venta
UPDATE productos 
SET stock = stock - 1
WHERE id = 1;

-- 4. Eliminar productos sin stock
DELETE FROM productos 
WHERE stock = 0;
```

### Gestión de Usuarios y Pedidos
```sql
-- 1. Registrar nuevo usuario
INSERT INTO usuarios (nombre, email)
VALUES ('María García', 'maria@email.com');

-- 2. Crear pedido
INSERT INTO pedidos (usuario_id, total)
VALUES (LAST_INSERT_ID(), 150.00);

-- 3. Ver pedidos de usuarios
SELECT 
    u.nombre,
    COUNT(p.id) as total_pedidos,
    SUM(p.total) as total_gastado
FROM usuarios u
LEFT JOIN pedidos p ON u.id = p.usuario_id
GROUP BY u.id
HAVING total_pedidos > 0;
```

## Buenas Prácticas DML

1. **Consultas SELECT**
   - Especificar columnas en lugar de usar *
   - Usar alias para mejorar legibilidad
   - Limitar resultados cuando sea posible
   - Optimizar JOINs

2. **Inserciones y Actualizaciones**
   - Usar transacciones para operaciones múltiples
   - Verificar datos antes de insertar
   - Hacer backup antes de actualizaciones masivas

3. **Eliminaciones**
   - Usar WHERE para evitar eliminaciones accidentales
   - Considerar soft delete en lugar de DELETE
   - Verificar integridad referencial

4. **Rendimiento**
   - Usar índices apropiadamente
   - Evitar subconsultas cuando sea posible
   - Optimizar condiciones WHERE

# Consultas Agregadas y Restricciones de Datos

## 1. Consultas Agregadas (Aggregate Queries)

### ¿Qué son?
Son funciones que realizan cálculos sobre un conjunto de registros y devuelven un único valor. Permiten obtener estadísticas y resúmenes de datos.

### Funciones de Agregación Principales

#### COUNT
**¿Qué hace?** Cuenta el número de filas o valores.

```sql
-- Contar todos los registros
SELECT COUNT(*) FROM usuarios;

-- Contar valores no nulos
SELECT COUNT(email) FROM usuarios;

-- Contar valores únicos
SELECT COUNT(DISTINCT ciudad) FROM usuarios;
```

#### SUM
**¿Qué hace?** Suma valores numéricos.

```sql
-- Suma simple
SELECT SUM(total) FROM pedidos;

-- Suma con condición
SELECT SUM(total) 
FROM pedidos 
WHERE fecha >= '2024-01-01';

-- Suma por grupo
SELECT cliente_id, SUM(total) as total_gastado
FROM pedidos
GROUP BY cliente_id;
```

#### AVG
**¿Qué hace?** Calcula el promedio de valores numéricos.

```sql
-- Promedio simple
SELECT AVG(precio) FROM productos;

-- Promedio con redondeo
SELECT ROUND(AVG(precio), 2) 
FROM productos;

-- Promedio por categoría
SELECT categoria_id, AVG(precio) as precio_promedio
FROM productos
GROUP BY categoria_id;
```

#### MAX y MIN
**¿Qué hace?** Encuentra valores máximos y mínimos.

```sql
-- Valores máximo y mínimo
SELECT 
    MAX(precio) as precio_maximo,
    MIN(precio) as precio_minimo
FROM productos;

-- Por categoría
SELECT categoria_id,
    MAX(precio) as mas_caro,
    MIN(precio) as mas_barato
FROM productos
GROUP BY categoria_id;
```

### GROUP BY
**¿Qué hace?** Agrupa registros para aplicar funciones de agregación.

```sql
-- Agrupación simple
SELECT ciudad, COUNT(*) as total_usuarios
FROM usuarios
GROUP BY ciudad;

-- Múltiples columnas
SELECT 
    ciudad,
    status,
    COUNT(*) as total
FROM usuarios
GROUP BY ciudad, status;

-- Con cálculos
SELECT 
    categoria_id,
    COUNT(*) as total_productos,
    AVG(precio) as precio_promedio,
    SUM(stock) as stock_total
FROM productos
GROUP BY categoria_id;
```

### HAVING
**¿Qué hace?** Filtra resultados de grupos (como WHERE pero para grupos).

```sql
-- Filtrar grupos
SELECT ciudad, COUNT(*) as total
FROM usuarios
GROUP BY ciudad
HAVING total > 100;

-- Filtros complejos
SELECT 
    categoria_id,
    AVG(precio) as precio_promedio
FROM productos
GROUP BY categoria_id
HAVING precio_promedio > 500
    AND COUNT(*) > 10;
```

## 2. Restricciones de Datos (Data Constraints)

### ¿Qué son?
Son reglas que se aplican a las columnas de una tabla para mantener la integridad de los datos.

### Tipos de Restricciones

#### PRIMARY KEY
**¿Qué hace?** Define una columna o conjunto de columnas como identificador único.

```sql
-- En creación de tabla
CREATE TABLE usuarios (
    id INT PRIMARY KEY,
    nombre VARCHAR(100)
);

-- Clave primaria compuesta
CREATE TABLE detalle_pedido (
    pedido_id INT,
    producto_id INT,
    cantidad INT,
    PRIMARY KEY (pedido_id, producto_id)
);

-- Agregar después
ALTER TABLE usuarios
ADD PRIMARY KEY (id);
```

#### FOREIGN KEY
**¿Qué hace?** Establece una relación entre tablas.

```sql
-- En creación de tabla
CREATE TABLE pedidos (
    id INT PRIMARY KEY,
    usuario_id INT,
    FOREIGN KEY (usuario_id) 
        REFERENCES usuarios(id)
        ON DELETE RESTRICT
        ON UPDATE CASCADE
);

-- Agregar después
ALTER TABLE pedidos
ADD FOREIGN KEY (usuario_id) 
REFERENCES usuarios(id);
```

#### UNIQUE
**¿Qué hace?** Asegura valores únicos en una columna.

```sql
-- En columna individual
CREATE TABLE usuarios (
    id INT PRIMARY KEY,
    email VARCHAR(100) UNIQUE,
    username VARCHAR(50) UNIQUE
);

-- Restricción única compuesta
CREATE TABLE productos (
    id INT PRIMARY KEY,
    codigo VARCHAR(10),
    modelo VARCHAR(10),
    UNIQUE(codigo, modelo)
);
```

#### NOT NULL
**¿Qué hace?** Prohíbe valores nulos.

```sql
-- En creación de tabla
CREATE TABLE empleados (
    id INT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL
);

-- Modificar columna existente
ALTER TABLE empleados
MODIFY email VARCHAR(100) NOT NULL;
```

#### CHECK
**¿Qué hace?** Valida que los datos cumplan ciertas condiciones.

```sql
-- Restricción simple
CREATE TABLE productos (
    id INT PRIMARY KEY,
    precio DECIMAL(10,2) CHECK (precio > 0),
    stock INT CHECK (stock >= 0)
);

-- Restricciones complejas
CREATE TABLE empleados (
    id INT PRIMARY KEY,
    edad INT,
    salario DECIMAL(10,2),
    CHECK (edad >= 18),
    CHECK (salario >= 0)
);
```

#### DEFAULT
**¿Qué hace?** Establece un valor predeterminado.

```sql
-- Valores por defecto simples
CREATE TABLE articulos (
    id INT PRIMARY KEY,
    nombre VARCHAR(100),
    activo BOOLEAN DEFAULT true,
    fecha_creacion DATETIME DEFAULT CURRENT_TIMESTAMP
);

-- Con expresiones
CREATE TABLE pedidos (
    id INT PRIMARY KEY,
    total DECIMAL(10,2) DEFAULT 0.00,
    status VARCHAR(20) DEFAULT 'Pendiente'
);
```

### Ejemplos Combinados

```sql
-- Tabla completa con restricciones
CREATE TABLE empleados (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    departamento_id INT,
    salario DECIMAL(10,2) CHECK (salario >= 0),
    fecha_contrato DATE DEFAULT CURRENT_DATE,
    activo BOOLEAN DEFAULT true,
    FOREIGN KEY (departamento_id) 
        REFERENCES departamentos(id)
        ON DELETE RESTRICT
);

-- Consulta agregada con restricciones
SELECT 
    d.nombre as departamento,
    COUNT(*) as total_empleados,
    AVG(e.salario) as salario_promedio,
    MAX(e.salario) as salario_maximo
FROM empleados e
INNER JOIN departamentos d ON e.departamento_id = d.id
WHERE e.activo = true
GROUP BY d.nombre
HAVING AVG(e.salario) > 30000;
```

