# Expresiones Regulares
Al enfrentar un problema con expresiones regulares, muchas personas afirman que se tienen dos problemas, debido a que las expresiones regulares son muy tediosas de trabajar en algunos casos pero en realidad si se resuelve una problemática con expresiones regulares implica simplemente pensar un poco mas, pero se consiguen resultados bastante potentes y duraderos puesto que ya tenemos una solución que obedece patrones. Efectivamente con cualquier lenguaje de programación es posible implementarlas pero cada uno tiene una manera puntual o especifica de representarlas, sin embargo el significado de la mayoría de símbolos es el mismo en casi todos los lenguajes.  

**Pagina para testear expresiones regulares**
https://regex101.com/

## ¿Que es una expresión regular?
Es una secuencia de caracteres que conforma un patrón de búsqueda. Se utilizan principalmente para búsqueda de patrones de cadenas de caracteres u operaciones de sustitución.

## Simbología de Expresiones Regulares

**.**  
Es el símbolo para representar un carácter cualquiera. Puede ser alfanumérico, símbolo de pesos, diagonales, porcentaje, dos puntos, cualquier cosa que sea un carácter, incluyendo el carácter de espacio en blanco.

### Tokens  
Los tokens equivalen a encontrarlos por carácter, es decir, si yo busco [a-z] el match equivale a encontrar una sola letra de la a a la z minúscula una sola vez
en cualquier parte del documento.

**\d** ~ **[0-9]**  
Encuentra todos los dígitos, **SOLO NÚMEROS**

**\D**  
Cualquier carácter que no sea un dígito.

**\w** ~ **[a-zA-Z0-9_]**  
**CUALQUIER CARÁCTER ALFANUMÉRICO**, (cualquier carácter de palabra) no va a buscar caracteres especiales, ni espacios, **EL GUION BAJO ESTA INCLUIDO**.

**\W**
Cualquier carácter que no sea carácter de palabra, es decir cualquier cosa que no sea una letra, un numero, o un guion bajo (es una especie de negación).

**\s**  
Espacios en blanco y saltos de linea.

**\S**  
No es un espacio, Tab o nueva linea.

**\b**  
Limite de Palabra

**\B**  
No es un Limite de Palabra

*NOTA:*
*Todo lo que tiene significado para una expresion regular que lleve caracteres en minusculas si lo encontramos en MAYUSCULAS como \W \D \S denota que esta negando ese significado, entonces \D va a encontrar todo lo que no sea un numeoro*

**^**   
1. Al inicio de una expresion regular, siempre denota que lo que sea que vayamos a encontrar empiece con un inicio de linea.
2. Al inicio de una clase de expresiones regulares denota, negar lo que sea que contenga esa clase.

**$**  
Final de una linea de texto, siempre que una sola linea termine.

*NOTA:*    
*los caracteres que pertenecen a las expresiones regulares pueden escaparse mediante el BackSlash Ej. ```\.``` denota que lo que queremos es encontrar el carácter punto.*

- ## Cuantificadores

*NOTA:*
*Los operandos realizan ciertos cambios sobre los tokens que los anteceden, recordar siempre que para alterar a los token especificados debemos colocar los operandos después de esos tokens (efecto sufijo)*

**\***  
El Asterisco sirve para encontrar un token **0 o N veces**.

**\+**  
El Más o *plus* sirve para encontrar un token **1 o N veces**.

**?**  
El símbolo de interrogación sirve pra encontrar un token **0 o 1 vez**

**{n}**  
Especifica el numero de veces que debe encontrarse un caracter, clase o grupo.

**{n,m}**  
Permite especificar un mínimo y un máximo de veces que puede encontrarse un caracter, clase o grupo.

## Ejemplos de Expresiones regulares

**Expresión regular para encontrar colores representados en Hexadecimal**  

```
 #([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})
```

**Expresión regular para encontrar el numero total de caracteres de un archivo (faltan mas pruebas)**  

```
 .?
```

**Expresión regular para encontrar URLs validas, sin importar el dominio**

```
https?:\/\/[\w\-\.]+\.\w{2,5}\/?\S*
```
**Explicación:**  
1. Forzosamente tiene que estar el http
2. El caracter de la "s" puede o no estar
3. Los dos puntos son obligatorios
4. Forzosamente tiene que haber dos slash y para esto hay que escaparlos.
5. que siga una clase que consiste en cualquier caracter de palabra, incluidos guiones y puntos, y de esta clase podemos encontrar mínimo uno máximo varios
6. Tiene que haber un punto
7. De 2 a 5 caracteres de palabra
8. Un slash que puede o no estar por lo menos una vez
9. Cualquier cosa que no sea un espacio en blanco y esto ultimo puede o no estar varias veces

## Expresión regular para encontrar correos electrónicos validos

```
[\w-.]+@[\w-.]+\.[\w]{2,5}
```

## Expresión regular para encontrar URLs

```
(https?:\/\/[\w\-\.]+\.\w{2,5}\/?\S*)|(w{3}\.[\w\-\.]+\.\w{2,5}\/?\S*)|([\w\-\.]+\.\w{2,5}\/?\S*)
```


## Expresión regular para encontrar números de teléfono
```
^((\d{3})[\s\-]?){2}((\d{2})[\s\-]?){2}$
```


