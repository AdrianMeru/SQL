# DDL

## ÍNDICE 
- [Que es DDL](#Que-es-DDL)
- [CREATE](#CREATE)
  -  [CREATE SCHEMA](#CREATE-SCHEMA)
  -  [CREATE DOMAIN](#CREATE-DOMAIN)
   -  [CREATE TABLE](#CREATE-TABLE)
 - [CONSTRAINT](#CONSTRAINT)
  -  [PRIMAR KEY](#PRIMARY-KEY)
  -  [FOREIGN KEY](#FOREIGN-KEY)

## Que es DDL

Un lenguaje de base de datos o lenguaje de definición de datos (Data Definition Language, DDL por sus siglas en inglés) es un 
lenguaje proporcionado por el sistema de gestión de base de datos que permite a los programadores de la misma llevar a cabo las 
tareas de definición de las estructuras que almacenarán los datos así como de los procedimientos o funciones que permitan consultarlos.

## CREATE

A continuación vamos a ver los tres tipos diferentes de uso que tiene **create**

### CREATE SCHEMA

Para crear una bases de datos usaremos la la sentencia **SCHEMA**, se recomienda usar **IF NOT EXISTS** para evitar crear dos bases de datos con el mismo nombre

```sql
CREATE SCHEMA [IF NOT EXISTS] nombrebasesdedatos
```
### CREATE DOMAIN

Si queremos crear un dominio de base lo unico que necesitaremos es el nombre el dominio y el tipo de dato. Los domios se usan para facilitar el trabajo, ya que si se va a repetir un tipo de dato en varias partes de la base datos nos creamos un dominio y nos ahorramos especificar el dato en divesas veces,  y ademas en caso de que ese dato se modifique solo lo tendriamos que modificar en el dominio.

```sql
CREATE DOMAIN nombredominio VARCHAR(10)
```

### CREATE TABLE

Las tablas se crean de manera individual, fuera ponemos el nombre de la tabla y si queremos especificar que pertenece a una base de datos que no es en la que no estamos situados ponemos el nombre de esa base de datos entre **[]**. El contenido de la tabla se especifica todo entre **()** , de base solo se necesita el nombre del atributo y el tipo de dato. Si se requiere se le añadiran las **CONSTRAINT** las cuales veremos mas adelante.

```sql
CREATE TABLE nombre tabla(
nombreatributo tipodato [CONSTRAINT
);
```

## CONSTRAINT

Las **CONSTRAINT** se utilizan en el create table y con el alter el cual veremos mas adelante. Se utilizan para especificar las primary key, las foreing key, unique, not null y check.

### PRIMARY KEY

Sirve para especificar cual es la clave pricipal de una tabla, la  cual segun las reglas de entidad relacion no pueden ser nulas y sus valores no pueden repetirse.

```sql
CREATE TABLE nombre tabla(
nombreatributo tipodato PRIMARY KEY
);
```

### FOREIGN KEY
