# SQL  
  
# ÍNDICE
- [Que es SQL](#Que-es-sql) 
- [Conceptos básicos](#Conceptos-básicos)  
- [SELECT](#SELECT)
- [FROM](#FROM)  
- [WHERE](#WHERE)
## Que es sql  
SQL es un lenguaje de programación que a día d hoy esta debidido en 6 sublenguajes pero nos centraremos unicamente en DQL.  
Este lenguaje es de dominio específico, se utliza para administrar y recuperar información de sistemas de gestión de bases de datos relacionales.  
  
  ## Conceptos básicos  
  1. Los **strings** tienen que estar entre comillas simples.  
  2. La \ sirve para hacer un espacio en blanco.
  3. Tiene que rematar con ; para que compile los datos.  
  4. Para poner mayor que o menor que mas igual él = tiene que ir después que el > o el <.  
  5. Las **cláusulas** como SELECT, FROM, WHERE, ... Deben ir en mayúsculas.
  6. Los comentarios pueden ser en la misma linea utilizando -- o en diversas lineas utilizando /* */.
  7. Utlizamos **<>** para decir que es diferente
    
## SELECT
Lo utilizamos para seleccionar los datos de las tablas que queremos mostrar.  
```sql
SELECT nombre, continente, poblacion
FROM world;
```
En este codigo estamos diciendo que nos muestre el nombre, el continent y la población.  
  
## FROM
Se utiliza para seleccionar la tabla en la que estan los datos que quieres mostrar.
```sql
SELECT personaje
FROM narauto;
```
Con este condigo estamos diciendo que seleccione la tabla narauto.  

## WHERE
Sirve para filtrar los datos seleccionados en el **SELECT**.  
```sql
SELECT población
FROM world
WHERE name = 'Alemania';
```
Con este codigo filtramos para que solo nos muestre la población de alemania.  
  
## IN  
Sirve para seleccionar al mismo tiempo varios elementos en un mismo filtro.
```sql
SELECT name, population 
FROM world
WHERE name IN ('Sweden','Norway', 'Denmark');
```
