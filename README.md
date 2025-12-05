# Funciones y clases principales de PHP

## Funciones de PHP

Una función en PHP es un bloque de código reutilizable que realiza una tarea específica. Sirve para reutilizar de una manera "limpia" el código.
Igual que muchos otros lenguajes de programación una función se carateriza por tener

> **Nombre**: para poder 'llamar' a la función a lo largo del código. Esta característica es obligatoria a la hora de definir la función.\
> **Parámetros**: son los datos de entrada que recibe la función a la hora de ser 'llamada'. No siempre son necesarios a la hora de definir una función.\
> **Retorno (return)**: es el valor que la función devuelve al final de su ejecución. En PHP no es necesario especificar el tipo del valor que se retorna y tampoco es necesario devolver un dato.

Usando las funciones se consigue la modularización y la limpieza del código, y dichas funciones pueden
ser creadas por el usuario o usar las que ya están creadas de serie y podemos encontrar en el manual de PHP.\
Aquí explicaré con detalle las más usadas en mis ejercicios:

### Funciones de impresión en pantalla
El siguiente listado trata sobre aquellas funciones usadas para la impresión en pantalla de valores de variables, cadenas de caracteres con la posisibilidad de estructurar con uso de etiquetas HTML una página web.\
Aquí están las funciones más usadas para imprimir por pantalla:

#### echo()
Es la función más sencilla para mostrar contenido, y es bastante flexible a la hora de usarla.\
Esta función no devuelve ningún valor.\
**Forma de uso**
```php
    echo "Hola mundo. Me llamo ".$nombre;\
    echo ("Hola mundo. Me llamo ".$nombre);\
```

#### print(), print_r(), printf()
En este apartado trataremos varias funciones ya que se diferencian en pequeños detalles.\
A diferencia de echo() estas funciones son capaces de mostrar arrays y estructuras complejas.\
**Forma de uso print()**\
Solo imprime valores de las variables.\
Devuelve 1, por lo que se puede usarse en expresiones.
```php
print("Hola mundo. Me llamo ".$nombre); 
```
**Forma de uso print_r()**\
Esta función puede mostrar el contenido de una estructura compleja como un array.\
Se le puede pasar como segundo parámetro el valor 'true' y en vez de imprimir por pantalla, nos devolverá el resultado.
```php
print_r("Los valores de este array son: ". $aVector);
```
**Forma de uso printf()**\
Esta función sirve para formatear la salida por lo que es muy útil para mostrar números.\
Para mostrar el valor de las variables se debe usar %d,%s,%f dependiendo del tipo de valor que queremos mostrar.
```php
printf("Mi nombres es %s, mi edad es %d y mi altura en metros es %f", $nombre, $edad, $altura);
```

### Funciones de formularios
Dicho de una manera correcta, las siguientes funciones son las que más usamos a la hora de realizar un formulario y de tratar
(validar) los datos que se envían en ellas.\

#### is_null()
La función is_null() es usada en muchos casos para comprobar si una variable o un array está definida como null o no.\
>**Parámetro:** variable la cual se quiere evaluar.\
>**Return:** true en caso de que sea null y false en caso de que no sea null.

#### empty()
La función empty() sirve para comprobar si una variable está vacía. Que una variable esté vacía implica que no exista, o que su valor sea igual a false.\
En caso de que la variable no exista, la función no manda alerta ninguna.\
>**Parámetros:** variable la cual se quiere evaluar.\
>**Return:** en caso de estar vacia true y en caso de tener un valor que no sea igual a "false" devuelve false.

#### isset()
La función isset() determina si una variable es considerada definida, lo que significa que está declara y es diferente a null.\
Si una variable ha sido destruida con la función unset(), ya no se considera como definida.\
**Parámetro:** variable o variables (sin límite) las cuales se quieren evaluar.\
**Return:** en caso de estar definida y ser desigual a null devuelve true y al contrario, si no ha sido definida o es igual a null, devuelve false.

#### date()
La función date() devuelve una cadena formateada según el formato indicado usando el integer timestamp (marca de tiempo) dado.
En caso de no indicar parámetro devuelve el momento actual del servidor.\
>**Parámetros:** format que indica el formato de la fecha usando expresiones como %s%h%m%M%d%i etc... y el timestamp que 
es un parámetro opcional cuyo valor es un número entero con el valor de marca temporal.\
>**Return:** cadena con la fecha formateada.

### Funciones de lectura y escritura de archivos.
El siguiente listado pertenece a las funciones usadas para la importación y exportación de archivos, es decir, a la lectura de un archivo (json, xml, csv, etc...) y la creación y escritura de un archivo.

#### basename()
La función basename() devuelve el nombre del archivo según la ruta especificada.\
>**Parámetros:** cadena de carateres con la ruta de un archivo. Puede ser ruta relativa o absoluta. suffix que es un parámetro opcional el cual nos quita el sufijo del archivo dejando solo el nombre del archivo.\
>**Return:** cadena de carateres con el nombre del archivo de la ruta especificada.

#### json_encode()
La función json_encode() retorna una cadena de carateres que contiene la representación JSON del valor de una variable, un objeto, un array, etc... En el caso del objeto solo se codifican las propiedades públicas de éste.\
>**Parámetros:**\
> - Value: puede ser desde un entero, hasta un string pasando por objetos, variables y arrays.\
> - Flag: que indica la máscara de bits.\
> - Depth: define la profundidad máxima que debe ser mayor que cero.\
>**Return:** un JSON codificado como STRING en caso de éxito. Si hay algún error en el proceso se devuelve false.

#### json_decode()
La función json_decode() recupera una cadena codificada en JSON y la convierte en un valor PHP.
>**Parámetros:**
> - json: un string json a codificar.
> - asociative: en caso de ser true, los objetos JSON serán devueltos como arrays asociativos. Si es false, serán devueltos como objetos. En caso de ser null dependerá de los flags.
> - depth: profundidad máxima de anidamiento de la estructura en proceso de decodificación.\
>**Return:** ninguno.
#### file_put_contents()

### Funciones de Log in-Log out

#### header()
La función header() permite especificar el encabezado HTTP string al enviar los ficheros HTML.\
Nunca se olvide que la función debe ser llamada antes de que se envíe cualquier contenido, ya sea por líneas HTML habituales en el fichero, o por salidas PHP.
>**Parámetros:**\
> - Existen dos tipos: HTTP/ y Location\
> - Location: devuelve un encabezado al cliente y, a mayores, envía un estado REDIRECT(302) al navegador siempre que no se haya envaido un código de estado 201 o 3xx.\
>**Return:** ninguno.\

**Ejemplo:**
```bash
<?php
header("Location: http://www.example.com/"); /* Redirección del navegador */
/* Asegúrese de que el código siguiente no se ejecute una vez realizada la redirección. */
exit;
?>
```

## Clases de PHP
### DateTime
La clase DateTime realiza, en esencia, la representación de la fecha y hora. Permite crear, manipular y formatear fechas y horas de forma flexible y orientada a objetos.\
Esta clase nos permite:
>- Crear un fechas a partir de cadenas, timestamps o la fecha actual con **new DateTime()**. (En caso de no pasar parámetros se crea un objeto con la fecha actual)\
>- Modificar fechas usando métodos como **modify() add() y sub()** que, respectivamente, modificar la fecha pasada como parámetro, añadir una cantidad de tiempo a la fecha pasada por parámetro y restar una cantidad de tiempo igual que con add().\
>- Formatear fechas mediante el uso de **format()** y %h, %m, %Y, etc...\
>- Comparar fechas directamente con operadores o con métodos como **diff()** que devuelve un objeto DateInterval el cual especifica la diferencia entre las dos fechas.\

Esta clase es más potente y segura que las funciones procedimentales tradicionales como date() y strtotime().
### PDO
### PDOStatement
### PDOException
### DOMDocument