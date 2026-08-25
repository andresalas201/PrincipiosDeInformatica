# Capítulo 7: Subrutinas

## Objetivos

    Importancia de subrutinas para la modularización y la reutilización
    
    Definición de subrutinas y sus componentes

    Retorno de valores

    Invocación y paso de argumentos

    Diferencias entre objetos mutables e inmutables en el paso de argumentos

## Subrutinas

Las subrutinas (también llamadas métodos o funciones) son bloques de instrucciones que no corren por si mismas, sino que deben ser llamadas. Un ejemplo son las funciones **print** e **input**.

### Declaración

Para crear una subrutina, este debe ser declarada, esto se logra utilizando el comando **def** seguido de un **nombre**, paréntesis  izquierdo "**(**", paréntesis  derecho "**)**" y luego 2 puntos "**:**", tras lo cual se puede empezar a escribir el bloque de instrucciones. Un ejemplo de declarar funciones es:

```
def saludar():
    print("Hola")
```

### Llamado

Para utilizar una función, simplemente se debe escribir su nombre seguido de los paréntesis "**()**, como cuando utilizamos print e input. Por ejemplo:

```
def saludar():
    print("Hola")

saludar()
```

### Argumentos

Es posible darle datos a una función, estos se llaman argumentos. Los argumentos se declaran entre los paréntesis al crear la función y se envian de la misma manera, en caso de existir múltiples argumentos, se utilizan comas "**,**" para separarlos. Por ejemplo:

```
def saludar(nombre):
    print(f"Hola {nombre}")

saludar("André")
```

### Retornar

Una función no solo puede recibir datos, sino que puede devolverlos, a este se llama retornar. Recordemos el funcionamiento de la función **input** que nos retorna una string con lo escrito por el usuario. Para retornar simplemente se utiliza el comando **return**, por ejemplo:

```
def suma(n1, n2):
    return n1 + n2

n3 = suma(n1, n2)
```

### Importancia

Las subrutinas nos permiten guardar bloques de instrucciones que queremos reutilizar o para darle un mejor orden al código. En un código real, prácticamente todo el código debe estar dentro de subrutinas. Un ejemplo simple es en una calculadora, sin usar subrutinas el código de la misma es:

```
if tipoOperacion == "+":
    resultado = n1 + n2
elif tipoOperacion == "-":
    resultado = n1 - n2
elif tipoOperacion == "*":
    resultado = n1 * n2
elif tipoOperacion == "/":
    resultado = n1 / n2
```

Una versión con subrutinas:

```
def suma(n1, n2):
    return n1 + n2

def resta(n1, n2):
    return n1 - n2

def mult(n1, n2):
    return n1 * n2

def div(n1, n2):
    return n1 / n2

def calculadora(tipoOperacion, n1, n2):
    if tipoOperacion == "+":
        return suma(n1, n2)
    elif tipoOperacion == "-":
        return resta(n1, n2)
    elif tipoOperacion == "*":
        return mult(n1, n2)
    elif tipoOperacion == "/":
        return div(n1, n2)
```

En muchos casos, el uso de subrutinas puede alargar el código, pero es buena práctica de programación utilizarlas lo más posible. 

## Inmutables y Mutables en subrutinas

Al recibir datos como argumentos en variables, se debe tomar en cuenta la inmutabilidad o mutabilidad de los mismos. Si editamos un dato mutable dentro de una función, este se verá afectado dentro de la misma, esto no es el caso con los datos inmutables, por ejemplo:

```
def hola(n1):
    n1 = 5
    print("hola")

x = 1
hola(x)
print(x)
```

En este caso, print(x) va a imprimir un 1, porque la versión que es alterada dentro de la función hola no afecta al x exterior.
