# SQL  
  
# ÍNDICE
- [Qué es SQL](#Qué-es-sql) 
- [Conceptos básicos](#Conceptos-básicos)  
- [SELECT](#SELECT)
- [FROM](#FROM)  
- [WHERE](#WHERE)
- [BETWEEN y AND](#BETWEEN-y-AND)
- [< > y =](#<->-y-=)
- [LIKE,%,_](#LIKE-porcentaje-y-guion-bajo)
- [OR NOT](#OR-y-NOT)
## Qué es sql  
SQL es un lenguaje de programación que a día de hoy está dividido en 6 sublenguajes pero nos centraremos únicamente en DQL.  
Este lenguaje es de dominio específico, se utiliza para administrar y recuperar información de sistemas de gestión de bases de datos relacionales.  
  
  ## Conceptos básicos  
  1. Los **strings** tienen que estar entre comillas simples.  
  2. La \ sirve para hacer un espacio en blanco.
  3. Tiene que rematar con ; para que compile los datos.  
  4. Para poner mayor que o menor que más igual él = tiene que ir después que el > o el <.  
  5. Las **cláusulas** como SELECT, FROM, WHERE, ... Deben ir en mayúsculas.
  6. Los comentarios pueden ser en la misma línea utilizando -- o en diversas líneas utilizando /* */.
  7. Utilizamos **<>** para decir que es diferente
  8. Para renombrar algo del código utilizamos **AS**
    
## SELECT
Lo utilizamos para seleccionar los datos de las tablas que queremos mostrar.  
```sql
SELECT nombre, continente, población
FROM world;
```
En este código estamos diciendo que nos muestre el nombre, el continente y la población.  
  
## FROM
Se utiliza para seleccionar la tabla en la que están los datos que quieres mostrar.
```sql
SELECT personaje
FROM narauto;
```
Con este código estamos diciendo que seleccione la tabla narauto.  

## WHERE
Sirve para filtrar los datos seleccionados en el **SELECT**.  
```sql
SELECT población
FROM world
WHERE name = 'Alemania';
```
Con este código filtramos para que solo nos muestre la población de alemania.  
  
## IN  
Sirve para seleccionar al mismo tiempo varios elementos en un mismo filtro.
```sql
SELECT nombre, población 
FROM world
WHERE name IN ('España','Andorra', 'Portugal');
```
Con esto filtramos al mismo tiempo el  nombre y la población de España, Andorra y Portugal.  
  
## BETWEEN y AND
El **BETWEEN** lo utilizamos para filtrar entre dos números incluyendo los extremos, y el **AND** para que se tengan que cumplir dos condiciones para que funcione el filtrado.
```sql
SELECT nombre, area
FROM world
WHERE area BETWEEN 200000 AND 250000;
```
En este código filtramos los paises que estan entre 200000 y 250000.  
  
## < > y =
Se utilizan para hacer comparaciones entre datos de las tablas
```sql
SELECT nombre 
FROM world
WHERE population > 200000000;
```
Aqui estamos filtrando para que solo aparezcan los paises con más de 200000000 habitantes, si utilizaramos el < aparecieran los que tuvieran menos y si usaramos el = solo los que tengan el mismo número de inventarios.

## LIKE porcentaje y guion bajo
El **LIKE** se utiliza para filtrar los datos que tengan una estructura parecida, el **%** para decir que hay x caracteres y el _ para decir que hay un caracter.
```sql
SELECT name FROM world
  WHERE name LIKE '%United%';
```
En el codigo anterior filtramos los paises que contengan United.  
  
## OR y NOT
