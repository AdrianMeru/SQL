# SQL  
  
# ÍNDICE
- [Qué es SQL](#Qué-es-sql) 
- [Conceptos básicos](#Conceptos-básicos)  
- [SELECT](#SELECT)
- [FROM](#FROM)  
- [WHERE](#WHERE)
- [BETWEEN y AND](#BETWEEN-y-AND)
- [< > y =](#menor-que-mayor-que-igual)
- [LIKE,%,_](#LIKE-porcentaje-y-guion-bajo)
- [OR NOT](#OR-y-NOT)
- [ROUND](#ROUND)
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
  
## menor que mayor que igual
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
El **OR** se utiliza para decir que se tiene que cumplir una condicion u otra y el **NOT** se utila con el **OR** o el **AND** para indicar negacion en la condicion.
```sql
SELECT nombre, poblacion, area
FROM world
WHERE
(population>250000000 OR area>3000000)
AND NOT(population>250000000 AND area>3000000)
```
Este nos filtra los paises que tengan una población mayor que 50000000 o un area mayor que 3000000 y no tengan una población mayor que 50000000 y un area mayor que 3000000.  
  
## ROUND
