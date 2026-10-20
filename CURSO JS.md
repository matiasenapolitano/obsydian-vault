# UNIDAD 1
> ==🟡TIPOS DE DATOS==

Hay 9 tipos de datos que se dividen en 2 grupos, los primitivos y los no primitivos.

Primitivos:  BOOLEAN, NUMBER, STRING, UNDEFINED, SYMBOL, BIGINT, NULL,

number - 2, 3.5, infinity, 2,999e8 (x10 elevado a la 8)

Con number se pueden hacer operaciones aritmeticas
- suma +
- resta - 
- multiplicacion *
- division /
- modulo %
- exponente **

string - 'cadenas de texto' = "cadenas de texto" = ´cadena de texto´

Las string que utilizan ´tildes invertidas´ son multilinea por defecto, osea que puedes hacer saltos de renglon con **mayus+enter**
y en la devolucion de consola muestra un /n en donde va el salto de linea.

Tambien se puede contatenar cadenas de texto con un +
"cadenas de texto" + "cadenas de texto" = "cadenas de textocadenas de texto"

Booleanos - True o False

Undefined - Un calor que todavia no fue asignado, por ejemplo una variable que se creo pero no le asignaste ningun valor. Ej: number Total; si mostras por consola Total no va a mostrar nada xq no tiene nada asignado.

Null - A diferencia de undefined en este caso se le asigna el valor de NADA a esa variable, no es que olvidaste ponerle un valor, le pusiste un valor y es NADA o VACIO. 

Bigint - El tipo Number tiene un limite con el cual trabaja seguro manejando numeros enteros, por eso para numeros exageradamente grandes por ejemplo transacciones con crypto, se utiliza bigint, el cual se define poniendo una "n" al final del numero. Ej; let numeroGigante = 23341221312n

Symbol - Sirve para crear identificadores unicos para ese datos, por mas que haya 2 datos que sean por ejemplo dato1 = id1 y dato2 = id2 si son clase symbol, en el codigo quedan diferenciados.


> ==🔵OPERADORES DE COMPARACION== 

Son símbolos que te permiten comparar valores y te devuelve TRUE o FALSE 
```
mayor - 1 > 0 -> TRUE 
menor - 1 < 0 -> FALSE
mayor o igual 2 >= 2 -> TRUE 
menor o igual 3 <= 2 -> FALSE
exactamente igual 3 === 3 -> TRUE
distinto 3 !== 3 -> FALSE
```
!== y === se pueden usar tambien con cadenas de texto (SON CASE SENSITIVE)
```
"Java" === "java" -> FALSE
"Java" !== "JavasCript" -> TRUE 
```
Para comparar texto sin importar mayuscula y miniscula se utiliza las funciones TEXTO.toLowerCase() o TEXTO.toUperCase() para dejar todo en una misma tipo de letra. 
```
let texto1 = "JAVASCRIPT"
let texto2 = "javascript"

texto1 === texto2 -> FALSE
texto1.toUperCase() === texto2.toUperCase() -> TRUE
```
nos devuelve true ya que ambos textos dicen lo mismo y al poner ambos en mayuscula son iguales

Tambien estos se pueden usar con BOOLEANOS
```
let var1 = TRUE
let var2 = FALSE

var1 === var2 - FALSE
var1 !== var2 - TRUE

Se pueden usar >, <, >=, <= dado que true es 1 y false es 0
var1 > var2 - TRUE 

var1 === 1 -> FALSE ya que 1 es numero y var1 es boolean y el === compara que sea el mismo valor y mismo tipo.

var1 == 1 -> TRUE ya que al ser == es una igualdad debil o abstracta y ambos valores son 1 sin importar el tipo. (YA NO SE USA)
```

> ==🟡OPERADORES LOGICOS== 

Nos sirven para evaluar expresiones logicas
```
AND - && -> las dos cumples las condiciones ?
OR - || -> alguna de las dos cumple las condiciones ?
NOT - ! -> cambia el valor booleano al contrario
```
SE PUEDEN COMBINAR OPERACIONES ARITMETICAS, OPERADORES DE COMPARACION Y OPERADORES LOGICOS 
```
2 + 2 < 3 && 10 < 8 * 2
```
js esto lo resuelve en el siguiente orden

```
1ro operaciones aritmeticas
4<3 && 10 < 16

2do operadores de comparacion
false && true

3ro operadores logicos
false - dado que no los dos resultados son true 
```


> ==🟢VARIABLES==

Una variable se puede entender como una caja en donde guardas un valor para poder usarlo cada vez que llames esa caja. En js esa caja se suele declarar con la palabra reservada LET.
*una variable no puede comenzar su nombre con un numero, puede contener letras, numero y _ , son case sensitive y se debe poner un nombre descriptivo a las variables como buena practica*

```
let number = 4
let Number = 5
```

esto lo que quiere decir es que number tiene el valor asignado de 4, dado que = es asignacion lo cual es distinto a == o === y que son dos variables distintas
```
let 1number = 1 = 1 tiraria error de sintaxis al igual que si declaramos la variable con un nombre que comienze con algun simbolo que no este permitido.  
```
se le puede reasignar un valor por ejemplo de una suma 
```
number = number * 10 (no se vuelve a escribir let sino tira error de sintaxis)
esto le asigna el valor de 40 a la variable number (esto claramente no se puede hacer sin antes haber asignado un valor inicial)
```
las variables creados con la palabra reservada CONST, no se le puede reasignar el valor. Se usa por ejemplo para cosas que nunca van a cambiar en todo el codigo. Por ejemplo el valor de pi o la velocidad de la luz. Estas siempre deben inicializarse con algun valor
```
const VALOR_PI = 3,14
```
Podes crear una variable sin asignarle un valor y esto le asiganara el tipo undefined a la variable.

```
let sinDefinir - undefined
let texto = "Hola" - string
let itsOk = TRUE - boolean
let valor = 4 - number
let vacio = NULL - null
let cryptoChain = 124812381218293n - bigInt
```

El unico tipo de dato que no se "autoasigna" es el symbol dado que se usa para cosas muy especificas. 

global scope -> en todo el codigo
Function scope -> dentro de una funcion
block scope -> dentro de un bloque de codigo (if, while, etc)

````
const PERRO = "Firulais (Global)"; // Variable global

if (true) {
    const PERRO = "Guau (Bloque)"; // Variable local de bloque
    console.log(PERRO); // 👉 Imprime: "Guau (Bloque)" (¡Oculta a la global!)
}

console.log(PERRO); // 👉 Imprime: "Firulais (Global)" (La global sigue intacta afuera)
````

SHADOWING --> Este comportamiento en el cual la variable de bloque o funcion sobreescribe la global dentro de la ejecucion en el bloque o funcion se conoce como shadowing, de igual forma que suceda esto, es una mala practica.

VAR --> Tambien existe el tipo de variable VAR, pero este ya no se utiliza y una de los principales causas de que no se use es que no respeta el Block Scope, pero si el Function scope. Es decir si declaramos una variable tipo var en una bloque , esa misma se puede llamar desde el global.

SCOPE CHAIN --> El motor primero busca la variable en el entorno donde esta parado por ejemplo si ejecutamos un codigo que es un if, dentro de una funcion. El motor primero busca la variable en el if, luego en la funcion y por ultimo en el global, en caso de no encontrarla mostrara ReferenceError. 

> ==🟠TIPOS DE NOMENCLATURA EN VARIABLES==

```
camelCase - la mas usada en js

snake_case - se sigue utilizando pero no mucho , mas que nada en nombres de archivos

kebab-case - no se puede utilizar para nombrar variables pero se suele utilizar para nombrar archivos.

SCREAMING_CASE - se suele utilizar para variables constantes, para distinguirlas mas facilmente. 
```

> ==🟣COMENTARIOS==

Los comentarios son texto que se puede poner en el codigo el cual es ignorado al ejecutar el programa, se suele utilizar para explicar el funcionamiento del codigo o para que se asigno una variable.  Se crean poniendo // comentario en el mismo renglon o / * comentario  de mas de un renglon $*/$ en js 

```
const IS_ADULT = 18

un comentario adecuado para esto seria: }

const IS_ADULT = 18 // La mayoria de edad en xsi pais es 18
```

> ==🔴CONSOLE.LOG==

console.log() --> es una funcion integrada en js , la cual permite imprimir mensajes en consola ya sea del navegador o editor de codigo. 
```
let textoConsola = "texto consola de ejemplo "
let textoDos = "dos"
let number = 45

- console.log("texto") - mostraria la palabra "texto" en consola

- console.log(textoConsola) - mostraria "texto consola de ejemplo " en la consola

- console.log(textoConsola + "concatenado") - mostraria "texto consola de ejemploconcatenado" en la consola

- console.log(textoConsola, textoDos) - mostraria "texto consola de ejemplo dos" tiene un espacio ya que la , agrega un espacio de separacion entre variable

- console.log(textoDos + `${number}` ) - mostraria "dos45"

- console.log(textoDos , `${number}`) - mostraria "dos 45" 

- console.log(`${textoDos} ${number}`)  - mostria "dos 45"
```

CONCATENACION +
TEMPLATELITERAL ${variable}
SEPARACION ,

Tambien existen console.error() que muestra un mensaje de error en la consola, console.warn que muestra una advertencia y console.info que muestra un mensaje de informacion. Todos se muestran con una estetica distinta dentro de la consola para diferenciarlos. 

```text
> console.error(44)
❌ 44
> console.warn(55)
⚠️ 55
> console.info(45)
45
```


==🔵OPERADOR TYPEOF==

typeof es un operador incluido dentro de js el cual nos permite identificar el tipo de la variable a la cual estamos apuntando. Typeof devuelve un "texto" con el tipo de dato de la variable

```
let number = 45;

console.log(typeof number);
> number
```

historicamente hay un bug en el codigo fuente de js el cual si tiramos typeof a una variable null nos devuelve tipo object, lo cual esta mal. Entonces para comprobar si una variable es null se debe usar el === 

```
let dato = null

console.log(typeof dato)
> object 

dato === null -> true lo cual nos verifica que dato es null
```

el operador typeof es muy util para utilizar juntol con operadores de comparacion por ejemplo para verificar una edad ingresada en un input, primero se verifica que sea un numero el daro ingreado con typeof y luego se verifica por ejemplo que sea mayor de edad con > 18 

```
let edad = 20
let edadMenor = 12

typeof edad === "number" -> true
typeof edadMenor === "number" -> true

typeof edad === "number" && edad > 18 
> true
typeof edadMenor === "number" && edadMenor > 18 
> false
```

==🔴CONDICIONALES==

`IF (CONDICION)`
`{`
`EL CODIGO SE EJECUTA SI ES TRUE`
`}`
`ELSE IF(CONDICION)`
`{`
`SE EJECUTA CUANDO SE CUMPLE ESTA PERO NO LA DE ARRIBA`
`}`
`ELSE`
`{`
`EL CODIGO QUE SE EJECUTA SI NO ES TRUE`
`}`

En caso de que cumpla el primer if. tambien se podria cumplir el segundo, pero se ejecutaria el codigo del primer f ya que es de mayor gerarquia.

````
if (edad >= 18)
{
console.log("es mayor")
}
else if(edad >= 16)
{
console.log("es casi mayor")
}
else
{
console.log("el usuario es menor")
}
`````

Dentro de una condicional, se pueden poner mas condicionales. Pero no es muy recomendable ni es buena practica anidar tantas condiciones una con otra. por eso se recomienda usar operadores logiocs AND OR NOT.

Por ejemplo para saber si puede conducir es recomendable que la condicional sea si es mayor y si tiene carnet. No que dentro de si es mayor tenga un if que consulte si tiene carnet. Dado que estamos dandole un escalon mas que es innecesario a la condicional.  --> CALLBACK HELL

````
if (EDAD > 18 && carnet)
{
console.log("puede conducir")
}
else
{
console.log("No puede conducir")
}
````

Esto se puede simplificar todavia mas si guardamos ambas condiciones dentro de una sola variable y luego validamos esa variable. --> ABSTRACCION DE VARIABLE BOOLEANA
Se pueden ignorar las llaves si el codigo es corto haciendo asi mas limpio el codigo.

````
const edad = 19;
const carnet = true;
const puedeConducir = edad >= 18 && carnet

if (puedeConducir) console.log ("Puede conducir");
else console.log ("No puede conducir");
````

OPERACIONES TERNARIAS --> Son bloques if comprimidos en una sola linea de codigo, por ejemplo para asignar un valor a una variable segun la condicion.

````
asignacion = condicion ? true : false
````
si cumple con la condicion toma el primer valor, sino el segundo

````
let precioEnvio = precio > 2000 ? 0:1000
````
Esto quiere decir que si precio es mayor a 2000 el valor asignado a precioEnvio es 0, sino es 1000.


# UNIDAD 2
==🔴WHILE==

Un bucle es una estructura de control que te permite repetir una tarea x cantidad de veces mientras se cumpla con una condicion, tiene la misma estructura que un IF. Esto se realiza con la palabra reservada WHILE.

````
let numero = 10;

if (typeof numero === "number") {

  while (numero > 0) {
    console.log(numero + "seg.");
    numero = numero - 1;
  }
  console.log("El numero actual es 0")

} else console.log("no se ingreso un numero");
````

Este codigo lo que hace es analizar si el dato es un numero y si es un numero comienza a ejecutar un bucle while, este bucle lo que hace es mostrar por consola el numero hasta que sea 0 mas la palabra seg., luego le resta 1 al numero y vuelve a iniciar la misma accion hastas que llega a 0. En caso de que sea 0 el numero se ejecuta el codigo de debajo que esta fuera del bucle. 

El metodo while tiene 2 palabras clave asignadas BREAK y CONTINUE. 
BREAK --> Para el bucle y continua con el siguiente codigo que este fuera del while.
CONTINUE --> Ignora la iteracion y continua con la siguiente. 
````
let numero2 = 20;

while (numero2 > 0) {

  console.log(numero2 + "seg.");

  numero2 = numero2 - 1;

  if (numero2 === 3) {

    break; // rompe el ciclo cuando numero2 es igual a 3

  }

}

console.log("BUCLE 2 LLEGO A 3 Y SE ROMPIO");

  

let numero3 = 30;

while (numero3 > 0) {

  numero3 = numero3 - 1;

  if (numero3 % 2 === 0) {

    continue; // salta la iteración cuando numero3 es par

  }

  console.log(numero3 + "seg.");

}

console.log("BUCLE 3 TERMINO, SOLO SE MOSTRARON LOS IMPARES");
````

==🟣DO WHILE==

Esta estructura de codigo lo que hace es ejecutar un bucle al igual que el while mientras se cumpla una condicion, la diferencia es que este primero ejecuta el codigo dentro del bucle y despues compara. 

````
let resultado --> resultado es true
DO {
resultado = confirm("Quieres seguir en el bucle?")
}WHILE(resultado) --> el bucle se vuelve a ejecutar si resultado es true
````

Este codigo lo que es que la primera vez se ejecuta normalmente y muestra el cartel dado que entra como TRUE y manda un confirm, si damos a aceptar resultado agarra el valor de ese confirm que seria TRUE y se ejecuta nuevamente, en caso de darle a aceptar de nuevo, pasa lo mismo. En caso de darle a cancelar confirm toma el valor de FALSE por lo tanto resultado toma ese valor y se cancela el bucle dado que no cumple con la condicion. 

==🟢EXPRESIONES Y DECLARACIONES==

Crear una variable con valor 2+2 es una declaracion ya que estamos declarando que queremos crear algo con un valor de 2+2, no es que le estemos dando un valor a algo. En cambio poner 2+2 si esta generando un valor ya que nos devuelve 4 y eso es una Expresion. 

Una expresion es cualquier pedazo de código que produce o evalúa a un valor.
Una declaracion es una instrucción completa que ejecuta una acción como crear una variable.

Estas se diferencian facil con la consola, dado que si ponemos por ejemplo:

`````
let numero = 2+2; muestra por consola undefined dado que el codgioe esta ejecutando la accion de guardar la variable numero.

2+2; muestra por consola 4 porque esta generando ese valor
`````

==🟡BUCLES FOR==

Es una estructura de codigo con la palabra reservada FOR, que permite realizar un bucle un numero determinado de veces, se realiza cierta accion que aumenta o disminuye el contador hasta que ese contador llega a cumplir la condicion deseada. 

````
for (INICIALIZACION; CONDICION; ACTUALIZACION)
{
CODIGO
}
````

En inicializacion se declara una variable por ejemplo si queremos contar, se declara let cantidad = 1, la condicion por ejemplo si queremos contar hasta 10 seria numero <= 10 y luego la actualizacion en este caso seria numero++ (numero ++ es lo mismo que poner numero = numero +1). 

Se puede utilizar variables ya creadas en la iniciaizacion o crearla en el for mismo, la actualizacion puede ser con lo que definas vos, ++ suma 1 , -- resta 1. Pero se puede utilizar += para sumar, -= para restar,  `*=` para multiplicar, /= para dividir en el numero que se desee. 

````
let pi = 3.14;

for (pi; pi > 1; pi -= 0.01) {

  console.log(pi);

}
````

Por ejemplo este for, esta utilizando la variable ya creada pi, tiene la condicion que mientras pi sea mayor que 1 se le reste 0,01 y lo muestre en consola.

Al igual que en el for, tambien se puede usar las palabras reservadas break y continue con el mismo accionar que en los otros bucles. 

````
for (let i = 0; i < 10; i++) {

  const esImpar = i % 2 !== 0;

  if (esImpar) {

    continue; // salta la iteración cuando i es impar

  }

  console.log(i + "seg. // es par ");

}
````

````
for (let i = 0; i < 70; i++) {

  console.log(i + "seg.");

  if (i === 66) {

    console.log("SIX SEVENN");

    break; // rompe el ciclo cuando i es igual a 66

  }

}
````

==🟣SWITCH==

El switch es una estructura de codigo tiene el cual evalua una expresion y le asigna el bloque de codigo que coincida con la condicional que cumpla esa expresion. 

````
switch (expresion)
case valor1:
	codigo
	break
case valor2:
	codigo
	break
default
	break
````

Se envia la expresion, si coincide con el caso 1 realiza el codgio del caso 1, si coincide con el 2 realiza la del 2  y si no coincide con ninguna, realiza la opcion por default. 

FALL-THROUGH --> Dentro de un switch el codigo se ejecuta en cascada por eso para "detenerlo" se utiliza el break, si no tenemos el break y por ejemplo entra en el case 1 pero este no tiene break, ejecutara el codigo del case 1 pero seguira con el case 2 y asi sucesivamente hasta que se encuentre con un break o termine el codigo. 

Esto si no se hace intensionalmente es un bug y mala practica. Una "buena" forma de aplicarlo es cuando queres agrupar las opciones.  Por ejemplo tenemos la opcion de ingresar un mes y nos dice que estacion es. 

````
let mes = "enero";

switch (mes) {
    case "diciembre":
    case "enero":
    case "febrero":
        console.log("Es verano (en el hemisferio sur)");
        break;
    default
    break;
}
````

En este caso utilizamos el fall-through con los cases diciemebre enero y febrero para que si entra en cualquiera de esos muestre que es verano.  (no se pone el console log en cada case ya quie al no tener el break lo mostraria en cada caso).

Para switch existe un patron, Switch(true), que consiste en que utiliza el primer bloque de codigo del case que la condicion sea true. 

````
let mes = "junio";

switch (true) {

  case mes === "enero" || mes === "febrero" || mes === "diciembre":

    console.log("Es verano");

    break;

  case mes === "marzo" || mes === "abril" || mes === "mayo":

    console.log("Es otoño");

    break;

  case mes === "junio" || mes === "julio" || mes === "agosto":

    console.log("Es invierno");

    break;

  case mes === "septiembre" || mes === "octubre" || mes === "noviembre":

    console.log("Es primavera");

    break;

  default:

    console.log("No es un mes valido");

}
````

# UNIDAD 3
==🔵FUNCIONES== 

Una funcion es un bloque de codigo que cumple una funcion especifica cuando se llama y se le pasan ciertos parametros previamente delimitados o no segun sea. Utiliza la palabra reservada FUNCTION. 

````
function saludar() 
{
	console.log("Hola")
}

saludar();
````

Esta funcion cada vez que sea llamada con la linea saludar() , que en este caso no tiene nada entre parentesis xq no tiene ningun parametro asignado la funcion, mostrara en la consola "Hola", solo eso y no devuelve nada solo UNDEFINED.

Para hacer que una funcion devuelva algo, se debe usar la palabra reserva RETURN, esto se usa por ejemplo para asignarle el valor a una variable.,

````
function suma()
{
return 2+2
}

let resultado = suma()
````

Esta funcion va a retornar el valor de 2+2 osea 4 y ese 4 podemos guardarlo en una variable por ejemplo resultado que al hacer console log mostrara que vale 4. 

==🟠FUNCIONES CON PARAMETROS==

Un PARAMETRO es lo que se estable en la funcion que esta necesita  para poder ser ejecutada, por ejemplo si queremos realizar una funcion que salude a x nombre debemos pasarle como ARGUMENTO ese nombre, si no le pasamos un nombre dira Hola undefined

````
function saludar(nombre) {
console.log(`Hola, " + ${nombre}`)
}
saludar("matias")
````
Para funciones que tengan mas de un parametro, los argumentos se deben pasar separados con una , y en el  mismo orden que son solicitados.  Como parametro se pueden pasar inclusive otra funcion.

````
function sumar(a, b) {
  let resultado = a + b;
  console.log("Sumando " + a + " y " + b + " el resultado es: " + resultado);
  return resultado;
}
sumar(5, 10);
````

Se pueden utilizar otros bloques de codigo dentro de funciones ya sea bucles, funciones, condicionales. 

````
function calcularTotalCompra(preciobase, esVIP, tipoEnvio) {

  let precioEnvio;

  if (esVIP) {

    preciobase *= 0.85;

  }

  switch (tipoEnvio) {
    case "estandar":
      if (preciobase > 40000) {
        precioEnvio = 0;
      } else precioEnvio = 1500;
      break;
    case "express":
      precioEnvio = 3500;
      break;
    default:
      precioEnvio = 1500;
      break;
  }
  resultado = preciobase + precioEnvio;

  console.log("El total de la compra es: " + resultado);

  return resultado;

}
calcularTotalCompra(45000, true, "estandar");
````

En esta funcion le estamos pasando 3 argumentos, el preciobase, un booleano que dice si es vip o no y el tipo de envio en forma de string. Lo que hace es que si es vip es true le restas el 15% al precio base, luego con un switch se dan los 2 casos, si es standar o express el envio y se verifica si cumple los requisitos para envio gratis, por ultimo se suma estos 2 numeros obtenidos para obtener el valor total en la variable resultado que se muestra en consola.

HOISTING --> Js al momento de compilar el codigo asigana el principio de la memoria para las funciones , eso nos permite ejecutar funciones antes de declararlas. 

```
sum(1,4); 
function sum(a,b){
return a+b
}
```

esta suma 1 + 4 funcionaria por el hoisting dado que como coloca en memoria primero las funciones, por mas que ejecute el codigo en cascada ya sabe lo que hace la funcion sum y puede ejecutarla. 

==🔴FUNCTIONS EXPRESSIONS==
Es una funcion que esta asignada en una variable, estas function expresions no tienen el hoisting, dado quea al estar creadas como una variable pierde esa propiedad.  Por eso si sum(1.4) estuviese sobre la funcion no funcionaria. 

```
let sum = function(a,b) {
return a+b
}
sum(1,4)
```

==🟡ARROW FUNCTIONS== 
