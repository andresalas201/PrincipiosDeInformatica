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

    Un objeto Empleado contiene: Nombre, Cédula, Salario y Puesto (datos), también tiene una funcion que permite cambiar el valor de Salario y Puesto (comportamientos)

    Un objeto Calculador debe tener la capacidad de realizar sumas, restas, divisiones, multiplicaciónes y otras operaciones (comportamientos) y deben guardar operaciones anteriores, la operación actual, resultados anteriores, etc. (datos). Incluso podríamos pensar en las operaciones como objetos que contienen operandos, tipo de operación, resultado, etc.

    La POO se basa en representar todo tipo de conceptos y comportamientos a partir de objetos, lo que significa que prácticamente todo nuestro código existe como parte de un objeto.

### Compilación vs Interpretación

    En los lenguajes compilados como C y C++, el código es revisado completamente y se es traducido en su completitud a instrucciones que la computadora puede correr directamente

    En los lenguajes interpretados como Python y JavaScript, el código se ejecuta directamente, traduciendo en tiempo real a instrucciones para la máquina

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
2. Que algoritmos vamos a usar para el prgorama. Como vamos a programar el menú que decide el tipo de operación, como vamos a leer los numeros que escribe el usuario, etc.

Este paso a veces puede parecer innecesario, pero el realizarlo correctamente simplifica enormemente el proceso de escribir el código en si.

### Implementación

En este paso se da la creación del código

1. Se toma el diseño y lo convertimos en código real

### Prueba

Se revisa que el código funcione correctamente y que cumpla con los objetivos iniciales.

1. Se buscan errores (bugs) en el código. Pueden ser cosas simples como instrucciones mal escritas o cosas más serias como algoritmos enteros que no hacen lo que deberían.
2. Asegurarse de que el código cumple con todos los objetivos iniciales. En el ejemplo de la calculadora, nos aseguramos que el usuario pueda realizar todas las operaciones realizadas y que sus resultados sean correctos.
3. En caso de encontrarse bugs o que hayan objetivos sin cumplir, volvemos a la etapa de implementación, arreglando y agregando funciones, tras lo cuál repetimos la etapa de prueba.

## Resolución de problemas

### Comprensión

### Descomposición

### Especificación

### Codificación

### Validación



## Entorno de Programación

### Editor de texto

### Interprete o compilador

### Consola

### Entorno de Desarrollo Integrado (IDE)



## Instrucciones

<Definicion>

Los tipos de instrucciones son:

### Declaración

### Asignación

### Control

### Entrada y Salida
