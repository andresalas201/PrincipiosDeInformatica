# Capítulo 6: Control de flujo

## Objetivos

    Secuencia de instrucciones

    Bloques de instrucciones

    Estructuras condicionales

    Ciclos por condición, por contador y por colección

    Estructura para el manejo de excepciones

## Orden de ejecución

En Python, las instrucciones son ejecutadas de arriba para abajo, llevando a cabo la instrucción y luego pasando a la siguiente. Esto solo cambia cuando se presentan instrucciones que afectan de una u otra manera el orden de ejecución, como las instrucciones try - except del capítulo anterior.

## Bloques de instrucciones

Una serie de instrucciones que se ejecutan de forma continua, en Python estas tienen que estar al mismo nivel de indentación y son precedidas por el uso de **:** (exceptuando el bloque inicial del archivo). Los bloques suelen crearse cuando existe una instrucción que crea un bloque debajo de si, como las antes vistas try y except. Un ejemplo de esto es:

![Gráfico de bloques de instrucciones](Graphs/BloquesDeInstruc.svg)

En este caso podemos ver que tanto **if** como **else** crean **nuevos bloques de instrucciones**, mientras que siguen siendo del bloque original.

Existen diferentes tipos de instrucciones con la capacidad de crear bloques de instrucciones y que, por lo tanto, pueden afectar el orden en el que se ejecutan las instrucciones. 2 de estos tipos son los **condicionales** y los **ciclos**

## Condicionales

Las instrucciones condicionales revisan si una condición es verdadera o falsa, ejecutando su bloque de instrucciones en caso de que la condición sea verdadera. Existen 3 instrucciones: **if**, **elif** y **else**. Estas instrucciones deben usarse de forma seguida, una instrucción if puede ser usada en cualquier momento, pero **elif y else solo pueden usarse si ya existe un if**.

Las instrucciones condicionales vienen en series de condicionales, los if inician la serie, seguido opcionalmente por elif (pueden ser 0 o infinitos) y finaliza con un único else (pueden haber 0 o 1).

Dentro de una serie de condicionales, **cuando una condición se cumpla, no se revisan el resto de condicionales que sigan después del que se cumple**, por lo tanto, si más de una condición puede cumplirse al mismo tiempo, es necesario prestarle atención al orden de la serie.

### if

La instrucción if es la primera instrucción de una serie de condicionales, su uso crea una nueva serie de condicionales, por lo que si usamos un if después de otro, estos son 2 series de condicionales. Por ejemplo:

![Grafico if](Graphs/EjemploIF.svg)

### elif

La instrucción elif funciona de una forma muy similar al if, la diferencia es: Solo puede existir después de un if o de otro elif, puede repetirse infinitamente y su existencia es opcional, es válido crear una serie de condicionales solamente con if y else. Un ejemplo de su uso es:

```
if n > 5:
    print("Es mayor a 5")
elif n < 5 and n > 0:
    print("Es menor a 5 y positivo")
elif n < 0:
    print("Es negativo")
elif n == 0:
    print("Es 0")
```

### else

La instrucción else siempre debe ir de última en la serie de condicionales y si se llega a ella siempre se activa, es el equivalente a decir  **si nada de lo anterior se cumple, haga esto**. Al igual que el elif, es opcional, por lo que se puede crear una serie de condicionales utilizando if-elif o simplemente if. Un ejemplo de su uso es:

```
if n > 5:
    print("Es mayor a 5")
elif n < 5 and n > 0:
    print("Es menor a 5 y positivo")
elif n < 0:
    print("Es negativo")
else:
    print("Es 0")
```

## Ciclos

Los ciclos son un tipo de instrucción que nos permite repetir un bloque de instrucciones múltiples veces. Existen 2 tipos de ciclos: iterativos (for) y condicionales (while).

### for

El for es un ciclo que busca iterar, puede realizarse iterando una cantidad determinada de veces (range) o iterando por una serie de datos (in).

#### range

Se itera una cantidad determinada de veces, creando una variable que sube hasta ser igual al range dado. Un ejemplo de este tipo de for es:

```
for i in range(5):
    print(f"iteración {i}")
```

**Nota:** En programación siempre se cuenta desde 0, por lo que i empieza en 0 y luego empieza a subir

**Nota:** En los for de range el ciclo termina en el momento que i es igual o mayor al numero de range, por lo que en el ejemplo dado solo se imprimiría hasta iteración 4

#### in

Se itera pasando por una serie de datos, se termina cuando se revisa completamente la serie de datos revisada, por ejemplo:

```
for letra in "HOLA":
    print(f"{letra}")
```

Este código imprimiría:

```
H
O
L
A
```

Este tipo de for es útil cuando queremos revisar por completo una serie de datos y aplicar operaciones sobre cada uno de sus datos.

### while

Los while son ciclos condicionales, es decir, es un ciclo que se repite hasta que se deje de cumplir una condición. Un ejemplo de este tipo es:

```
x = 5
y = 0
while (x > y):
    print(f"{x} es mayor que {y}")
    y += 1
```

**Nota:** Al utilizar estos ciclos es necesario asegurarnos que la condición puede ser afecta desde dentro del ciclo, de lo contrario podría generarse un ciclo infinito.

### Instrucciones relacionadas

Hay 2 instrucciones importantes relacionadas a ciclos pero que no son ciclos en si, estas son:

1. **break:** Sale completamente del ciclo, no importa si no se cumplen las condiciones de salida.
2. **continue:** Terminan la iteración actual del ciclo, es el equivalente de llegar al bloque de instrucciones del ciclo y empezar desde arriba.

## Manejo de errores

En general, manejar errores dentro de ciclos en Python es fácil, pero existen algunos ejemplos importantes que hay que tomar en cuenta a la hora de utilizarlos:

1. Asegurarse que los ciclos sean capaces de terminar, esto es más común al usar while, pero en algunos casos puede crearse un for-range en el que se cambia el valor de i, creando un posible ciclo.
2. Al utilizar un for-range y accesar a una serie de datos, es necesario asegurarse de que nunca se acceda a una posición invalida, esto se puede evitar revisando si i es mayor que el length de la serie de datos, por ejemplo:

```
datos = (1,2,3)
for i in range(5):
    if i >= len(datos):
        break
    print(datos[i])
```
