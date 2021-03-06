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
- [LENGTH](#LENGTH)
- [LEFT y <>](#LEFT-y-NOT-EQUALS)
- [Subconsultas](#Subconsultas)
- [ORDER BY](#ORDER-BY)
- [COUNT](#COUNT)
- [GROUP BY](#GROUP-BY)
- [HAVING y SUM](#HAVING-y-SUM)
- [DISTINCT](#DISTINCT)
- [JOIN](#JOIN)
- [NULL](#NULL)
- [RIGHT JOIN LEFT JOIN](#RIGHT-JOIN-LEFT-JOIN)
- [COALESCE](#COALESCE)
- [Agradecimientos](#Agradecimientos)
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
En este código filtramos los países que están entre 200000 y 250000.  
  
## menor que mayor que igual
Se utilizan para hacer comparaciones entre datos de las tablas
```sql
SELECT nombre 
FROM world
WHERE population > 200000000;
```
Aqui estamos filtrando para que solo aparezcan los países con más de 200000000 habitantes, si utilizaramos el < aparecieran los que tuvieran menos y si usaramos el = solo los que tengan el mismo número de inventarios.

## LIKE porcentaje y guión bajo
El **LIKE** se utiliza para filtrar los datos que tengan una estructura parecida, el **%** para decir que hay x caracteres y el _ para decir que hay un carácter.
```sql
SELECT name FROM world
  WHERE name LIKE '%United%';
```
En el código anterior filtramos los países que contengan United.  
  
## OR y NOT
El **OR** se utiliza para decir que se tiene que cumplir una condición u otra y el **NOT** se utiliza con el **OR** o el **AND** para indicar negación en la condición.
```sql
SELECT nombre, poblacion, area
FROM world
WHERE
(population>250000000 OR area>3000000)
AND NOT(population>250000000 AND area>3000000);
```
Este nos filtra los países que tengan una población mayor que 50000000 o un área mayor que 3000000 y no tengan una población mayor que 50000000 y un área mayor que 3000000.  
  
## ROUND
Sirve para redondear cifras se puede redondear a decimales utilizando una coma e indicando el número de estos.
```sql
SELECT name, ROUND(population/1000000,2)
FROM world;
```
Con este código redondeamos la población entre 1000000 y la aproximamos a 2 decimales.

## LENGTH
Se usa para filtrar por el largo de los elementos de las tuplas.
```sql
SELECT nombre, capital
FROM world
WHERE LENGTH(name) = LENGTH(capital);
```
En el código anterior filtramos los países que tengan el mismo número de caracteres en su nombre que en su capital.

## LEFT y NOT EQUALS
El **LEFT** lo utilizamos para comparar por la derecha caracteres y se especifica el número de caracteres con una , y poniendo el número de caracteres que vamos a comparar y **<>** se usa para decir que es distinto.
```sql
SELECT nombre,capital
FROM world
WHERE LEFT(name,1)=LEFT(capital,1)
AND name<>capital;
```
Con este código filtramos los países que tengan la misma primera letra que su capital y no sea el mismo nombre.

## Subconsultas
Tal y como indica su nombre son consultas dentro de consultas.
```sql
SELECT nombre 
FROM world
WHERE population >
     (SELECT poblacion FROM world
      WHERE nombre='Rusia');
```
En este código seleccionamos los países con más población que Rusia.

## ORDER BY
Se utiliza para ordenar el resultado segun un criterio especifico, se utliliza **ASC** para ordenar de manera ascendente y **DESC** para ordenarlo de manera descendente.
```sql
SELECT nombre, continente
FROM world
WHERE continente IN (
  SELECT continente
  FROM world
  WHERE name IN ('Australia','Argentina'))
ORDER BY name ASC;
```
Este codigo muestra los paises que estan en Americaa del sur y Oceania de manera ascendete.

## COUNT
Sirve para contar el número de tuplas.
```sql
SELECT COUNT(nombre)
FROM world;
```
Con esto sacamos el número de tuplas que tiene nombre

## GROUP BY
Se utiliza para agrupar los atributos.
```sql
SELECT continente, COUNT(nombre)
FROM world
GROUP BY(continente) 
ORDER BY continente ASC;
```
En este codigo te dice el numero de paises que tiene cada continente de manera ascendente

## HAVING y SUM
La cláusula **HAVING** se aplica a continuación de las filas del conjunto de resultados. Solo aparecen en el resultado de la consulta los grupos que cumplen las condiciones **HAVING**. Solo puede aplicar una cláusula HAVING a las columnas que también aparecen en la cláusula **GROUP BY** o en una función de agregado y el **SUM** se utiliza para sumar tuplas.
```sql
SELECT continent
FROM world
GROUP BY continent
HAVING SUM(population)>= 100000000;
```
Nos muestra los continentes que la suma de su población es mayor o igual a 100000000

## DISTINCT
Se utiliza para que no se repitan los resultados.
```sql
SELECT DISTINCT(matchid), player 
FROM goal
WHERE teamid LIKE 'GER';
```
Nos dice los jugadores de alemania que marcaron gol.

## JOIN
Se utiliza  para unir dos tablas.
```sql
SELECT jugador,equipoid,estadio,fechap
  FROM partido JOIN gol ON (id=matchid)
 WHERE equipoid='ALE';
```
Este código nos muestra nos muestra los jugadores, el nombre del equipo, el estadio y la fecha del partido de los jugadores de alemania que marcaron gol.

## NULL
Son las tuplas que no tienen un resultado.
```sql
SELECT nombre
FROM profesor
WHERE dept IS NULL;
```
Con esta consulta nos muestra  los profesores que no tienen departamento.

## RIGHT JOIN LEFT JOIN
Se utiliza para seleccionar una tabla del JOIN y la seleccionada mostrará todos sus resultados aunque en la otra sean nulos.
```sql
SELECT profesor.nombre, dept.nombre
FROM dept RIGHT JOIN profesor ON (profesor.dept=dept.id)
```
En la consulta anterior se muestran todos los profesores aunque su departamento sea nulo.

## COALESCE
Se utiliza para sustituir un nulo por un texto.
```sql
SELECT nombre, COALESCE(movil,'07986 444 2266') AS movil
FROM profesor
```
Esta consulta nos muestra el móvil de los profesores y en caso de que no tenga pone el número 07986 444 2266.

## Agradecimientos
**Alejandro Becerra Suarez**
