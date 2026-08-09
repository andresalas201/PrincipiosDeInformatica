# Capítulo 5: Entrada y salida de datos

## Objetivos

    Entrada estándar y argumentos de línea de comandos 

    Salida estándar y salida formateada

    Manejo básico de errores en la entrada y salida

## Entrada

La entrada (input) de datos en el proceso mediante en el que se le da información externa a la computadora. La entrada puede venir del mouse, teclado, micrófono, etc. Cualquier información o dato recibido desde el exterior se considera una entrada.

En Python hay 2 formas principales de hacer entrada de datos a un programa, mediante el compando input() y mediante argumentos.

### input()

Como fue mencionado en capítulos anteriores, input() es un comando que permite recibir una entrada de teclado del usuario, este detiene el programa y espera a que el usuario presione **enter**, guardando lo escrito por el usuario como una string. Un ejemplo de su uso es:

```
nombre = input("Cuál es su nombre? ")
```

**Nota:** Incluir una string dentro de los paréntesis de input permite que un mensaje se imprima en pantalla justo antes de parar para esperar la entrada del usuario, es equivalente a escribir un print seguido de input.

### Argumentos

La otra forma de recibir entradas es mediante **argumentos** al llamar un código mediante la consola.

Para ejecutar código utilizando la consola, simplemente se debe guardar nuestro código en un archivo.py (en este caso vamos a llamarlo hola.py) y utilizar el siguiente comando en la consola:

```
python hola.py
```

En algunos casos puede que nuestra consola no este en la misma carpeta que nuestro archivo .py, en esos casos se pueden usar los siguientes comandos:

1. **cd**: Nos permite entrar a una carpeta, se utiliza escribiendo cd carpeta, si queremos salir de la carpeta actual se escribe cd ..
2. **dir**: Imprime en pantalla todas las carpetas y archivos en el directorio actual, especialmente útil si no sabemos como se llama exactamente la carpeta hacia la que vamos.

Para agregar argumentos a la llamada de python se escriben los datos después del nombre del archivo:

```
python hola.py 123 Hola
```

Los datos que entran argumentos **siempre se reciben como strings**, para manejarlos hay que hacerlo desde el código, esto se realiza de la siguiente manera:

```
import sys
argumentos = sys.argv[1:]
```

Esto nos dará una lista de todos los argumentos que recibimos de la consola, los operadores [] nos permiten acceder a un dato específico, tome en cuenta que en programación se cuenta desde 0, entonces primer dato está en argumentos[0] 

## Salida

La salida (output) es cuando tomamos datos del código y los llevamos afuera, generalmente se hace imprimiendo un mensaje en la consola, pero también se puede guardar en un archivo (Esto será visto en el capítulo 11). 

Para imprimir algo en la consola, se utiliza el comando print(), este se utiliza de la siguiente manera:

```
print("Hola")
```

También es posible sumar diferentes strings para generar un mensaje nuevo, por ejemplo:

```
nombre = input("Cuál es su nombre? ")
print("Buenos días " + nombre)
```

A la hora de imprimir variables como en el ejemplo anterior, es más recomendable utilizar una string formateada.

### Formatear string

La forma más común de formatear string es incluir una **f** antes de la primer " de la string, por ejemplo: 

```
nombre = input("Cuál es su nombre? ")
print(f"Buenos días {nombre}")
```

Esto es especialente útil a la hora de imprimir un float, porque nos permite imprimir con una cantidad limitada de decimales, esto se hace de la siguiente manera:

```
pi = 3.14159265
print(f"Pi = {pi:.2f}")
```

En este ejemplo se imprimen solamente los primeros 2 decimales, si quisieramos imprimir una cantidad diferente de decimales simplemente cambiamos el 2 por el número deseado. Por ej. pi:.4f imprimiría 3.1416.

**Nota:** Al cortar decimales, se redondea, por eso 3.14159 se vuelve 3.1416 al tomar 4 decimales.

## Manejo de errores en Input/Output

Al recibir una entrada del usuario, en realidad no siempre vamos a recibir el formato que buscamos, puede que el usuario sea malicioso o directamente que haya leído mal lo que le pedimos, debido a esto hay que realizar cierto nivel de manejo de errores cuando tratamos con datos de un usuario.

La forma más fácil de hacerlo es utilizando **try**, **except** y **finally**, estos comandos hacen que cuando un error de ejecución ocurre el código no se detenga, sino que es manejado y el programa puede seguir. Veamoslo mediante un ejemplo:


```
edad = input("Cuál es su edad? ")
edad = int(edad)
print(f"Tienes {edad} años")
```

En este ejemplo, le pedimos al usuario su edad y la convertimos en un int (número entero), pero podría darse que el usuario escriba su edad en letras (veinticinco), esta entrada causaría un error, porque "veinticinco" no es un número. Una forma de evitar estos problemas es:

```
try:
    edad = input("Cuál es su edad? ")
    edad = int(edad)
    print(f"Tienes {edad} años")
except:
    print(f"{edad} no es una entrada valida")
```

Esta nueva versión del código posiciona la instrucción edad = int(edad) dentro del try, esto significa que si se genera un error, el programa detiene su ejecución de las instrucciones que están dentro del try y empiezan a ejecutar lo que esté dentro del except.

Por otra parte, el comando **finally** se utiliza cuando hay una sección de código que se debe ejecutar haya o no un error, por ejemplo:

```
try:
    edad = input("Cuál es su edad? ")
    edad = int(edad)
    print(f"Tienes {edad} años")
except:
    print(f"{edad} no es una entrada valida")
finally:
    print("Adios")
```

En este caso, el mensaje "Adios" se va a imprimir en consola haya o no un error
