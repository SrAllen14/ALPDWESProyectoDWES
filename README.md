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
#### is_empty()
#### isset()
#### date()

### Funciones de lectura y escritura de archivos.

#### basename()
#### json_encode()
#### json_decode()
#### file_put_contents()

### Funciones de Log in-Log out

#### header()