# Fundamentos de la programación

## Objetivos

    Conceptos de algoritmo, software, programación, lenguaje de programación, construcción y ejecución

    Ciclo de desarrollo de software: análisis, diseño, implementación y prueba

    Metodología para el proceso de resolución de problemas usando pensamiento computacional: comprensión y descomposición del problema, especificación del algoritmo, codificación y validación

    Entorno de programación

    Concepto de instrucción y sus tipos: declaraciones, asignaciones, control (de flujo), entrada y salida.

## Definiciones

### Algoritmo

    Serie de instrucciones finita y ordenada que define una forma de arreglar un problema o realiza una tarea

    Una receta de cocina, pasos para hacer figuras origami son algoritmos

### Software

    Serie de instrucciones, datos y código que le dirigen a una computadora

    Zoom, Discord y Fortnite son software

### Hardware

    Componentes fisicos de la computadora

    Teclado, pantalla, procesador, memoria RAM

### Programación

    La acción de escribir instrucciones para que una computadora realice una acción deseada


### Lenguaje de Programación

    Es una serie de instrucciones y sintaxis definido que permite darle instrucciones a la máquina

    Python, Java, JavaScript, C, C++

## Python

Python es un lenguaje de programación de **alto nivel** **orientado a objetos** e **interpretado**. Actualmente es el lenguaje de programación más popular. Es usado para videojuegos, análisis de datos, aprendizaje de máquina, etc.

### Alto nivel vs bajo nivel

    En programación, el nivel se refiere a que tan directa es la interacción del software con el hardware, mientras más alto el nivel menor es el control.

    Python es considerado alto nivel debido a que al programar no se tiene ninguna clase de control directo sobre el uso de memoria, interacción con el teclado, etc.

### Programación orientada a objetos (POO)

    Los objetos son entidades de software que contienen datos y comportamientos. La definición es un poco técnica, por lo que es útil pensar en ejemplos:

    Un objeto Empleado contiene: Nombre, Cédula, Salario y Puesto (datos), también tiene una funcion que permite cambiar el valor de Salario y Puesto y debe poder Despedir y Contratar al empleado (comportamientos).

![Gráfico del Objeto Empleado](Graphs/ClaseEmpleado.svg)

    Un objeto Calculador debe tener la capacidad de realizar sumas, restas, divisiones, multiplicaciónes y otras operaciones (comportamientos) y deben guardar operaciones anteriores, la operación actual, resultados anteriores, etc. (datos). Incluso podríamos pensar en las operaciones como objetos que contienen operandos, tipo de operación, resultado, etc.

    La POO se basa en representar todo tipo de conceptos y comportamientos a partir de objetos, lo que significa que prácticamente todo nuestro código existe como parte de un objeto.

### Compilación vs Interpretación

    En los lenguajes compilados como C y C++, el código es revisado completamente y se es traducido en su completitud a instrucciones que la computadora puede correr directamente

    En los lenguajes interpretados como Python, el código se ejecuta directamente, traduciendo en tiempo real a instrucciones para la máquina

    El proceso de compilación puede ser largo, por lo que empezar a correr un programa compilado es más lento que uno interpretado. Igualmente, el proceso de convertir las el código a instrucciones en tiempo real es más lento a largo plazo y puede causar problemas si ocurre un error muy adelante en el código que podría haber sido detectado en un lenguaje compilado.

Con estos conceptos en mente, observe el siguiente gráfico:

![Gráfico del proceso de interpretado de Python](Graphs/ProcesoCorrida.svg)

Este gráfico describe el proceso en el que se da la construcción y ejecución de un programa de Python. Existe un programa escrito en un archivo .py (archivo hecho completamente de texto), el texto de este archivo es leído paso por paso por el interpretador de Python, el cual lo convierte a instrucciones que puede entender la computadora, con estos códigos, la computadora ejecuta lo pedido, en este caso imprime un "hola" a su pantalla para que el usuario lo vea.


## Ciclo de desarrollo de software

La creación del software no es simplemente sentarse y escribir código hasta que funcione, es necesario sentarse y planear concretamente lo que vamos a hacer antes de empezar a implementarlo.

### Análisis

Es el primer paso, se basa en analizar exactamente que debe hacer el software, sus limitaciones y requerimientos.

1. Entender **que necesita el usuario** de parte del software. Es necesario delimitar correctamente las necesidades del usuario, si el usuario quiere una calculadora no es necesario que agreguemos la opción de tomar fotos y subirlas a internet.
2. Teniendo en mente las necesidades del usuario, se procede a pensar en los **objetivos** del software. Específicamente, que funciones debe tener nuestro programa para que las necesidades de nuestro usuario sean satisfechas. Volviendo a la calculadora, es necesario que esta sume, reste, divida y multiplique, por lo que nuestro objetivo es que estas funciones esten correctamente implementadas en el código. 

### Diseño

En este paso pensamos directamente en como queremos escribir el código.

1. Que estructuras vamos a usar, que clases, en que lenguaje, etc. Pensando en la calculadora, queremos que las operaciones seas un objeto además del objeto Calculadora o que la Calculadora guarde operaciones de otra manera.
2. Que algoritmos vamos a usar para el programa. Como vamos a programar el menú que decide el tipo de operación, como vamos a leer los numeros que escribe el usuario, etc.

Este paso a veces puede parecer innecesario, pero el realizarlo correctamente simplifica enormemente el proceso de escribir el código en si.

### Implementación

En este paso se da la creación del código

1. Se toma el diseño y lo convertimos en código real

### Prueba

Se revisa que el código funcione correctamente y que cumpla con los objetivos iniciales.

1. Se buscan errores (bugs) en el código. Pueden ser cosas simples como instrucciones mal escritas o cosas más serias como algoritmos enteros que no hacen lo que deberían.
2. Asegurarse de que el código cumple con todos los objetivos iniciales. En el ejemplo de la calculadora, nos aseguramos que el usuario pueda realizar todas las operaciones realizadas y que sus resultados sean correctos.
3. En caso de encontrarse bugs o que hayan objetivos sin cumplir, volvemos a repetir el ciclo de desarrollo, arreglando y agregando funciones, tras lo cuál repetimos la etapa de prueba.


En resumen, estos 4 pasos son un ciclo constante que se debe realizar para el desarrollo de software y es muy esperable que para llegar a un programa final sea necesario realizar múltiples vueltas al ciclo

![Gráfico del ciclo de desarrollo de software](Graphs/CicloSoftware.svg)

## Resolución de problemas

La programación es generalmente basada en crear código que resuelve un problema, una parte importante de programar es saber como manejar estos problemas, que en muchos casos pueden ser complejos y tener múltiples partes que tomar en cuenta. Esta explicación va a continuar con el ejemplo de crear un código que simula una calculadora.

### Comprensión

El primer paso es comprender el problema en su completidad, esto se basa en contestar preguntas como: ¿Cuál es el problema a resolver?, ¿Que debe hacer el código?, ¿Que información respecto al problema tengo? y ¿Que necesito para resolver el problema?. Esta sección es muy similar a la etapa de analisis del ciclo de desarrollo de software.

En el ejemplo de la calculadora, las respuestas son:

1. El problema es recrear una calculadora en código. 
2. El código debe recibir operaciones del usuario, resolverlas y enseñar el resultado.
3. La calculadora debe sumar, restar, dividir y multiplicar números.
4. Necesito programar un menú para recibir la operación y la habilidad de sumar, restar, dividir o multiplicar lo recibido.

### Descomposición

Los problemas pueden llegar a tener muchas partes, las cuales son por si mismas lo suficientemente difíciles de manejar, por lo tanto es preferible separarlos en piezas un poco más manejables. Se suele usar la frase **divide y vencerás** para describir esta estrategia.

En el caso de la calculadora, esta estrategia es muy útil. No es necesario pensar en toda la calculadora como una sola entidad, sino que la dividimos en sus diferentes funciones, primero nos centramos la forma de sumar, luego las restas, multiplicaciones y divisiones, terminando con el manejo de las operaciones que escribe el usuario. Esto evita que nos quedemos pegados en pensar todo el problema y podamos centrarnos en simplemente manejar cada pieza por si misma, tras lo cuál unirnos estas secciones es relativamente fácil (especialmente si las creamos con la idea de unirlas en el futuro)

### Especificación

Empezamos a pensar directamente en los algoritmos que van a ser parte de nuestro código. Hay muchas formas diferentes de realizar este paso, pueden hacerse diagramas, pseudocódigo o incluso describirlo en palabras normales.

Volviendo a la calculadora, estos son ejemplos de especificación:

#### Gráfico de flujo

![Gráfico de flujo de la calculadora](Graphs/DiagramaFCalculadora.svg)

#### Pseudocódigo

```
A = input()
B = input()
tipo = input()
if tipo == "+"
    resultado = A + B
elif tipo == "-"
    resultado = A - B
elif tipo == "*"
    resultado = A * B
elif tipo == "/"
    resultado = A / B
return resultado
``` 

#### Lenguaje natural

1. Se le pide el operando A al usuario
2. Se le pide el operando B al usuario
3. Se le pide el tipo de operación al usuario
4. Dependiendo del tipo de operación, calcular el resultado corresponidente
5. Retornar el resultado obtenido

### Codificación

En esta estapa se hace la escritura del código en si, se traduce el tipo de especificación que hayamos realizado a código real, en el caso de este curso todo se realizara en Python.

### Validación

En esta etapa se hacen las revisiones finales del código, esto generalmente se trata de ejecutarlo y usarlos, revisando si funciona de la manera correcta. En general se busca probar todas las funciones del mismo, incluso intentando buscar formas de romperlo, esto con el objetivo de corregir los errores encontrados.

En el ejemplo de la calculadora, probamos la suma, resta, multiplicación y división y nos aseguramos que sus resultados son correctos. Podemos probar a escribir letras cuando se nos piden los número o escribiendo un tipo de operación que no existe. 

## Entorno de Programación

La creación y uso del código que hacemos debe darse a traves de software creado anteriormente, desde un programa que nos permita escribir y guardar el texto del código a programas que nos permitan convertir el código en un programa que nuestra máquina pueda ejecutar.

### Editor de texto

Es un programa que nos permite crear, modificar y guardar documentos de texto. El código en general es guardado en archivos con extensiones como .c, .java o .py, pero estos son en realidad archivos de texto normales que programas como el bloc de notas pueden manipular.

### Intérprete o compilador

Es el programa que convierte el archivo de texto con código en un programa ejecutable por la máquina o en el caso del interprete que directamente convierte el texto en instrucciones a ejecutar.

### Consola

El lugar en el que se muestran los resultados de ejecutar nuestro código o en algunos casos se le puede pedir al usuario que escriba dentro de la consola.

### Entorno de Desarrollo Integrado (IDE)

Un Entorno de Desarrollo Integrado (IDE en por sus siglas en inglés) es un programa que puede realizar las funciones del editor de texto, interprete y consola dentro de si. La gran mayoría de programadores utilizan uno de estos programas para su código, incluso existen versiones que corren completamente online como Google Colab y Replit.

Algunos de los IDEs más populares son Visual Studio, PyCharm e IntelliJ.

## Instrucciones

Es la unidad más básica del programa, es el equivalente de programación de una oración. Las instrucciones pueden realizar funciones muy diferentes, por lo que estas se dividen en tipos.

Los tipos de instrucciones son:

### Declaración

Declaran una variable. Su función es simplemente decir que existe una variable con un número específico. En el caso de Python estas son muy simples, esto debido a que las variables en Python no tienen que declararse con un tipo (los tipos de variable serán explicado más adelante). Una declaración en python se ve de la siguiente manera:

```
numero1
``` 

### Asignación

Le dan un valor a una variable, contienen un **=**. El valor que está a la derecha del = se guarda en la variable de la izquierda. En Python se escriben de la siguiente manera:

```
numero1 = 5
``` 

### Control

Instrucciones que pueden alterar la forma en la que se ejecutan instrucciones. Pueden tanto decidir que instrucciones se ejecutan (if, else) o repetir instrucciones (for, while).

1. **if** ejecuta código si se cumple cierta condición.
2. **elif** solo existe después de un if, funciona igual que el if.
3. **else** solo existe despues de if y no pueden haber elif despueés del mismo. Se activa solamente si los if y elif anteriores no cumplen sus condiciones.

```
if (numero1 > 5):
    numero1 = 2
elif (numero1 < 5):
    numero1 = 1
else:
    numero2 = 3
``` 

1. **for** ejecuta una sección de código una cantidad N de veces. En el ejemplo posterior, ejecutaría la suma hasta que i sea igual que numero1, agregando 1 a i cada vez que repite el código. Es importante saber que en programación el conteo empieza en 0.
```
for i in range(numero1)
    numero2 = numero2 + i
```

1. ***while** repite una sección de código siempre y cuando se cumpla su condición. En el ejemplo, la resta se realizara hasta que numero2 deje de ser mayor que numero1.
```
while (numero2 > numero1):
    numero2 = numero2 - numero1
``` 

**Nota Importante:** En Python, el código que esta dentro de una instrucción de control debe tener una indentación extra que la instrucción de la que forma parte. 

Estos temas van a ser explicados más a fondo en los siguientes capitulos, no se estresen por entender perfectamente el código.

### Entrada y Salida

Son instrucciones que interactuan directamente con el usuario. Pueden ser instrucciones que imprimen una salida (output) a pantalla como **print()** o que más bien reciben una entrada (input) de datos del usuario como la instrucción **input()**. Se usan de la siguiente manera:

```
texto = input()
print(texto)
```
