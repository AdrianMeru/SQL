# DML

## ÍNDICE

- [Que es DML](#Que-es-DML)
- [INSERT](#INSERT)
- [UPDATE](#UPDATE)
- [DELETE](#DELETE)

## Que es DML

Lenguaje de Manipulación de Datos **(Data Manipulation Language, DML)** es un lenguaje proporcionado por los sistemas gestores de bases 
de datos que permite a los usuarios de la misma llevar a cabo las tareas de consulta o modificación de los datos contenidos en las 
Bases de Datos del Sistema Gestor de Bases de Datos.Las tres sentencias más importantes de este sublenguaje son
**INSERT**, **UPDATE** y **DELETE**.

## INSERT

Esta sentencia se utiliza para añadir datos a una tabla, estos datos pueden ser nuevos o provenientes de otra tabla. Para añadir varias tuplas solo se tiene que separar cadan valor por una coma. Si se quiere declarar un valor nulo solo se tiene que dejar en blanco una parte del valor.Para crear una tabla con las tuplas por defecto lo unico que tienes que hacer es poner INSERT INTO <paises> DEFAULT VALUES.
  
```sql
INSERT INTO mundo
(pais, capital)
VALUE
('España', 'Madrid'),
('Alemania', 'Berlin')
...
```
