# Capítulo 8: Estructuras de datos fundamentales

## Objetivos

    Listas: estructura, indexación y métodos básicos

    Tuplas: estructura, inmutabilidad, empaquetado y desempaquetado

    Diccionarios: estructura clave-valor, métodos básicos

    Conjuntos: estructura de valores únicos, métodos básicos

    Aplicaciones de cada estructura en el procesamiento de datos

## Listas

Las listas (list) son variables que contiene muchos datos dentro de si, son ordenadas y permiten modificación. Pueden contener diferentes tipos de variables. Se declaran de la siguiente manera:

```
numeros = [1, 2, 3]
palabras = ["Hola", "Perro"]
datos = [1, "Hola", 2.0]
```

### Comandos relacionados

Existe una serie de comandos que son útiles para el manejo de las listas, estos son:

**[ ]:** Los operadores [] nos permiten accesar un dato específico de la lista, las posiciones se cuentan a partir de 0. Los números negativos retornan los valores finales (ej. [-1] nos da el último valor de la lista). El uso de [] nos permite alterar el dato guardado. Se utilizan de la siguiente manera:

```
numeros = [1, 2, 3]
print(numeros[1]) # Este print imprime 2
numeros[0] = "Hola"
print(numeros) # Este print imprime ["Hola", 2, 3]
```

**[:]:** Si queremos tomar secciones de la lista en vez de un solo dato, podemos usar el comando [N1:N2], este toma de la posición de N1 hasta la de N2. Es posible utilizar negativos, al igual que en el [] normal. Es posible reemplazar secciones de la lista por nuevas secciones. Si se deja vacío el espacio izquierdo, se toma desde el inicio (ej: [:1]), si se deja vacío el derecho, se toma hasta el final (ej: [2:]). Un ejemplo de su uso es:

```
numeros = [1, 2, 3, 4, 5]
print(numeros[1:3]) # Este print imprime [2,3,4]
numeros[0:2] = [6,7,8]
print(numeros) # Este print imprime [6, 7, 8, 4, 5]
# No poner un número va a hacer que se tomen todos los datos en esa dirección
```

**len():** La función len() nos dice cuantos datos contiene la lista. Se utiliza de la siguiente manera:

```
numeros = [1, 2, 3]
print(len(numeros)) # Este print va a imprimir "3"
```

**.append():** Es un método que nos permite agregar nuevos valores a la lista, los valores nuevos son agregados al final de la misma, funciona de la siguiente forma:

```
numeros = [1, 2, 3]
print(numeros) # Este print imprime [1, 2, 3]
numeros.append(4)
print(numeros) # Este print imprime [1, 2, 3, 4]
```

**.insert():** Similar al append, pero insert el dato nuevo en una posición específica. Recibe un número entero y el dato a insertar. Un ejemplo de su uso es:

```
numeros = [1, 2, 3]
print(numeros) # Este print imprime [1, 2, 3]
numeros.insert(1, 4.2) # El método funciona con posición, dato
print(numeros) # Este print imprime [1, 4.2, 2, 3]
```

**remove():** Elimina un dato, debe recibir uno igual para encontrar el que va a ser eliminado. Solamente borra el primero encontrado. Se usa de la siguiente forma:    


```
numeros = [1, 2, 3, 1]
print(numeros) # Este print imprime [1, 2, 3, 1]
numeros.remove(1)
print(numeros) # Este print imprime [2, 3, 1]
```

**pop():** Elimina un dato, recibe una posición específica para eliminar. Si no se agrega un número, se elimina el último dato. Funciona de la siguiente manera:

```
numeros = [1, 2, 3]
print(numeros) # Este print imprime [1, 2, 3]
numeros.pop(0)
print(numeros) # Este print imprime [2, 3]
```

**sort():** Ordena la lista, si se deja vacía la ordena de menor a mayor, si se escribe reverse=True se ordena de mayor a menor. Un ejemplo de su uso es:

```
numeros = [5, 2, 3, 4]
numeros.sort()
print(numeros) # Este print imprime [2, 3, 4, 5]
numeros.sort(reverse=True) 
print(numeros) # Este print imprime [5, 4, 3, 2]
```

**Lista1 + Lista2:"" Se puede utilizar el operador + para agregar una lista a otra. Un ejemplo de esto es:

```
numeros1 = [1, 2, 3]
numeros2 = [4, 5, 6]
numeros3 = numeros1 + numeros2
print(numeros3) # Este print imprime [1, 2, 3, 4, 5, 6]
```

## Tuplas

Las tuplas (tuple) son un tipo de dato que nos permiten guardar múltiples datos, estos son guardados de forma ordenada pero la tupla no puede ser modificado. En general son iguales a las listas, excepto que no pueden modificarse. Las tuplas se declaran utilizando paréntesis **( )**, esto se hace de la siguiente manera:

```
numeros = (1, 2, 3)
```

### Comandos relacionados

Se pueden utilizar **len()**, **[ ]**, **[:]** con una tupla de la misma manera que los utilizamos con una lista.

Existen 2 formas de modificar una tupla que ya fue creada:

1. **Conversión a lista:** Se convierte la tupla a una lista, se le realizan los cambios necesarios y luego se convierte a tupla de nuevo. Un ejemplo de este proceso es:

```
numeros = (1, 2, 3)
numeros = list(numeros)
numeros.append(4)
numeros = tuple(numeros)
print(numeros) # Este print imprime (1, 2, 3, 4)
```

2. **Suma de tuplas:** Se le suma una tupla a otra, creando una nueva tupla que contiene la combinación de las 2. Una forma de hacerlo es:

```
numeros = (1, 2, 3)
num = (4,) # Las tuplas no pueden crearse utilizando solo (4), se agrega la coma (,) para que se cree una tupla
numeros = numeros + num # También se puede utilizar numeros += num
print(numeros) # Este print imprime (1, 2, 3, 4)
```

Otros comando interesantes de tuplas son:

**.count():** Cuenta la cantidad de veces que se repite un dato dentro de la tupla. Se utiliza de la siguiente forma:

```
numeros = (1, 2, 3, 1)
print(numeros.count(1)) # Este print imprime 2
```

**.index():** Busca un dato y retorna la posición en la que está. Funciona de esta manera:

```
numeros = (1, 2, "H", 2.1)
print(numeros.index("H")) # Este print imprime 2
```

## Diccionarios

## Conjuntos

## Aplicaciones