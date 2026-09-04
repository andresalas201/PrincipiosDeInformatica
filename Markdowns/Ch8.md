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

**.remove():** Elimina un dato, debe recibir uno igual para encontrar el que va a ser eliminado. Solamente borra el primero encontrado. Se usa de la siguiente forma:    


```
numeros = [1, 2, 3, 1]
print(numeros) # Este print imprime [1, 2, 3, 1]
numeros.remove(1)
print(numeros) # Este print imprime [2, 3, 1]
```

**.pop():** Elimina un dato, recibe una posición específica para eliminar. Si no se agrega un número, se elimina el último dato. Funciona de la siguiente manera:

```
numeros = [1, 2, 3]
print(numeros) # Este print imprime [1, 2, 3]
numeros.pop(0)
print(numeros) # Este print imprime [2, 3]
```

**.sort():** Ordena la lista, si se deja vacía la ordena de menor a mayor, si se escribe reverse=True se ordena de mayor a menor. Un ejemplo de su uso es:

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

**.index():** Busca un dato y retorna la posición en la que está. Si no existe, genera un error. Funciona de esta manera:

```
numeros = (1, 2, "H", 2.1)
print(numeros.index("H")) # Este print imprime 2
```

## Diccionarios

Los diccionarios (dicts) son otra forma de guardar múltiples datos bajo una sola variable. Los diccionarios, al igual que las listas, son ordenados y pueden cambiar, la mayor diferencia es que no es posible repetir datos. Los diccionarios no mantienen simplemente datos, si no que guardan los datos bajo un nombre, este nombre es llamado **llave** (key) y el dato que guarda la llave se denomina **valor**, las llaves no pueden repetirse, los valores sí.

Los diccionarios se declaran utilizando llaves **{ }** y las llaves se separan de sus valores utilizando 2 puntos (:). Un ejemplo de como crear un diccionario es:

```
datos = { "n1" : 1, "n2" : 2}
```

Es posible declarar los pares llave-valor del diccionario en diferentes líneas, esto se hace de la siguiente forma:

```
datos = { 
    "n1" : 1, 
    "n2" : 2
}
```

Las llaves pueden ser diferentes tipos de dato, no necesariamente strings. Los valores no necesariamente son datos primitivos, puede incluir todo tipo de datos. Un ejemplo de estos casos es:

```
datos = { 
    1 : 5, 
    "numeros" : [1, 2, 3]
}
```

### Comandos Relacionados

El comando **[ ]** funciona de forma diferentes en los diccionarios, simplemente usar un número no es posible, para acceder a un valor, es necesario utilizar su llave. Un ejemplo de como utilizar [ ] es:

```
datos = { 
    "n1" : 1, 
    "n2" : 2
}
print(datos["n2"]) # Este print imprime 2
```

Otra función de **[ ]** es agregar nuevos datos. Para agregar un nuevo dato simplemente escribir una llave dentro de [ ] y lo asignamos a su valor. Un ejemplo de esto es:

```
datos = { 
    "n1" : 1, 
    "n2" : 2
}
print(datos) # Este print imprime {"n1" : 1, "n2" : 2}
datos["n3"] = 3
print(datos) # Este print imprime {"n1" : 1, "n2" : 2, "n3" : 3}
```

**.keys():** La función keys() retorna todas las llaves contenidas dentro del diccionario. Se utiliza de la siguiente manera:

```
datos = { 
    "n1" : 1, 
    "n2" : 2
}
print(datos.keys()) # Este print imprime ["n1", "n2"]
```

**.values():** Hace lo mismo que keys, pero retorna los valores en vez de las llaves. Funciona de la siguiente manera:

```
datos = { 
    "n1" : 1, 
    "n2" : 2
}
print(datos.values()) # Este print imprime [1, 2]
```

**.items():** Retorna todo el diccionario como una lista en la que cada dato es una tupla de los pares llave-valor del diccionario. Si lo guardamos como variable, esta lista se actualiza con los cambios que ocurran en el diccionario original. Un ejemplo de su uso es:

```
datos = { 
    "n1" : 1, 
    "n2" : 2
}
datosItems = datos.items()
print(datosItems) # Este print imprime [("n1", 1), ("n2", 2)]
datos["n3"] = 3
print(datosItems) # Este print imprime [("n1", 1), ("n2", 2), ("n3", 3)]
```

**in:** La instrucción in nos permite revisar si una llave existe, retorna un booleano. Un ejemplo de su uso es:

```
datos = { 
    "n1" : 1, 
    "n2" : 2
}
print("n1" in datos) # Este print imprime True
print("n5" in datos) # Este print imprime False
```

**.pop():** Recibe una llave, borra esa llave y su valor del diccionario. Se utiliza de la siguiente manera:

```
datos = { 
    "n1" : 1, 
    "n2" : 2
}
print(datos) # Este print imprime {"n1" : 1, "n2" : 2}
datos.pop("n1")
print(datos) # Este print imprime {"n2" : 2}
```

**.clear():** Borra todos los datos del diccionario. Se usa de la siguiente forma:

```
datos = { 
    "n1" : 1, 
    "n2" : 2
}
print(datos) # Este print imprime {"n1" : 1, "n2" : 2}
datos.clear()
print(datos) # Este print imprime {}
```

**.copy():** La función copy() nos permite copiar los datos del diccionario a un nuevo diccionario. Si utilizamos dict2 = dict1, esto simplemente haría que las 2 variables contengan el mismo diccionario, por lo que un cambio posterior en dict1 se reflejaría en dict2. En caso de que no queramos compartir cambios entre variables, se utiliza copy(). copy() se utiliza de la siguiente forma:

```
datos = { 
    "n1" : 1, 
    "n2" : 2
}
print(datos) # Este print imprime {"n1" : 1, "n2" : 2}
datos2 = datos.copy()
datos.clear()
print(datos2) # Este print imprime {"n1" : 1, "n2" : 2}
```

### Uso de for

Los fors en un diccionario funcionan de una manera diferente. En primer lugar, el for-range que hemos visto hasta el momento no funciona con esta estructura. El for-in puede ser usado para los diccionarios, pero hay que tomar en cuenta que no nos retorna los datos directamente: **for-in, al usarse en un diccionario, nos retorna las llaves del diccionario**. La forma de utilizar el for-in es la siguiente:

```
datos = { 
    "n1" : 1, 
    "n2" : 2
}
for llave in datos:
    print(datos[llave])
# Este for imprime los valores del diccionario datos
```

## Conjuntos

Los conjuntos (sets) son otra forma de guardas múltiples datos dentro de una sola variable, se diferencia de las anteriores debido a que no es ordenada, no se pueden repetir valores y los valores no pueden cambiar (pueden agregarse o eliminarse, pero no editar lo que está adentro). Los sets se declaran utilizando llaves **{ }**, se diferencias de un diccionario debido a la falta de los dos puntos **:** que denotan la estructura llave-valor. La forma de crear un conjunto es:

```
datos = { 1, 2, 3}
```

**Nota:** Para los sets, el número 1 y el booleano True son el mismo valor, igualmente el 0 y el False. Esto es importante debido a que no se pueden repetir datos.

### Comandos relacionados

El comando len funciona como en listas y tuplas. El comando **[ ]** no puede ser usado en conjuntos, esto debido a que los conjuntos no tienen ningún tipo de orden o forma de indexar sus datos. Para acceder a los datos existen 2 formas:

**For:** Se puede utilizar un for-in para revisar uno por uno los datos del conjunto. Esto se hace de la siguiente manera:

```
datos = { 1, 2, 3}
for i in datos:
    print(i)
# Este print imprime 1, 2 y 3 en líneas separadas
```

**Revisión con in:** Se puede utilizar la instrucción in para revisar si un dato está en un conjunto. Esto se hace de la siguiente manera:

```
datos = { 1, 2, 3}
print(2 in datos) # Este print imprime True
```

Otros comandos importantes para el uso de conjuntos son:

**.add() y .update():** Agrega un dato nuevo en el caso de add() o una estructura de datos (tupla, lista, diccionario o conjunto) en el caso de update(). Solo se agregan datos que aún **NO** esten dentro del conjunto. Estos métodos se utilizan de la siguiente manera:

```
diccionario = { 
    "n1" : "a", 
    "n2" : "b"
}
datos = {1, 2 , 3}
datos.add(4)
datos.update(diccionario)
print(datos) # Este print imprime {1, 2, 3, 4, "n1", "n2"}
```

En el caso de los diccionarios, update() solo agrega las llaves, si queremos que guarde los valores se hace lo siguiente:

```
diccionario = { 
    "n1" : "a", 
    "n2" : "b"
}
datos = {1, 2 , 3}
datos.add(4)
datos.update(diccionario.values())
print(datos) # Este print imprime {1, 2, 3, 4, "a", "b"}
```

Existe la función **.union()** que funciona igual que update.

**remove() y discard():** Las 2 funciones reciben un dato que borrarán dentro del conjunto, la diferencia ocurre cuando no existe el dato que se intenta borrar: **remove() causa un error** si no encuentra el dato, **discard() no causa un error**. Estas funciones se usan de la siguiente forma:

```
datos = {1, 2 , 3}
datos.remove(2)
print(datos) # Este print imprime {1, 3}
datos.discard(3)
print(datos) # Este print imprime {1}
datos.discard(3) # Este discard no hace nada
datos.remove(3) # Este remove causa un error
```

**.intersection():** Une 2 conjuntos, manteniendo solamente los datos que se repiten entre ellos. Funciona de la siguiente manera:

```
datos1 = {1, 2, 3}
datos2 = {3, 4, 5}
datos3 = datos1.intersection(datos2)
print(datos3) # Este print imprime {3}
```

**.difference():** Guarda los datos de un conjunto1 que no están en el conjunto2. Un ejemplo de esta función es:

```
datos1 = {1, 2, 3}
datos2 = {3, 4, 5}
datos3 = datos1.difference(datos2)
print(datos3) # Este print imprime {1, 2}
```

**.symmetric_difference():** Es el opuesto a intersection, guarda todos los datos que no se repiten. Un ejemplo de su uso es:

```
datos1 = {1, 2, 3}
datos2 = {3, 4, 5}
datos3 = datos1.symmetric_difference(datos2)
print(datos3) # Este print imprime {1, 2, 4, 5}
```

## Aplicaciones

### Listas

Son útiles cuando necesitamos mantener una lista de datos a la que constantemente estamos añadiendo o alterando datos y necesitamos que tengan un orden específico y controlado. Algunos ejemplos de usos de listas son:

1. Mantener historiales: Si tuvieramos que programar un historial de personas que entran a un edificio, del uso de una máquina o situaciones similares.

2. Serie de datos iterable: En algunos casos va a ser necesario tener una lista de datos sobre la cuál se van a aplicar operaciones, la lista, debido a su capacidad de alteración, es ideal para esta clase de funciones.

3. Representación de matrices: En muchos casos, es necesario simular matrices o estructuras similares, en estos caso las listas son perfectas.

### Tuplas

Son útiles para mantener una lista de datos constante, la cuál no debemos tocar, pero en la cuál el orden es un factor importante y por lo tanto necesita estar indexada. Algunos ejemplos de estos usos son:

1. Guardar una lista de constantes: En ciertos casos es útil mantener una lista de constantes que no puede cambiar, por ejemplo: Una tupla que contiene resultados de la función seno ya calculados en los que la posición dentro del array denota los grados (ej. sen[0] retorna un 0)

2. Guardar una lista de datos válidos: Existen casos en los que queremos mantener una lista de datos que consideramos válidos. Por ejemplo un código en el que se pida a un usuario un día de la semana, en este caso guardamos los 7 días de la semana en una tupla y si la entrada del usuario no existe dentro de la tupla, es inválida.

### Diccionarios

Se utilizan cuando necesitamos una lista de datos que tienen un identificador importante (llave) la cuál queremos utilizar en vez de un índice númerico. Algunos ejemplos de su uso son:

1. Una lista de personas: Al guardar una lista de personas, el manejo (principalmente la búsqueda) es más simple si utilizamos un identificador específico (como un nombre o cédula) en vez de un número arbitrario que solo denota la posición. Esto es muy útil para guardar una lista de empleados, donde debe entrar y salir gente de la lista sin afectar el identificador de una persona específica.

2. Una lista de nombres de constantes: En algunos casos, vamos a tener que manejar una lista de constantes cada una con un nombre o identificador específico, el diccionario es una forma fácil de traducir ese nombre a un valor (literalmente usamos el diccionario como un diccionario). Un ejemplo es tener un diccionario con constantes númericas como pi, euler, etc. y poder usar constantes["pi"] para poder accesarla directamente.

### Conjuntos

Son usados para manejar listas de datos en las que el orden no nos importa de ninguna manera y en las cuales no se repiten datos. Algunos usos son:

1. Manejo de conjuntos: Funciones como union, difference e intersection nos permite realizar operaciones de conjuntos. Esto es útil cuando queremos revisar combinaciones de diferentes listas de datos. Un ejemplo es si tenemos una lista de invitados a 2 fiestas diferentes y estoy interesado en saber cuales personas están invitadas a ambas fiestas.

2. Mantener datos sin orden: En algunos casos, vamos a necesitar tener una lista de datos cuyo orden no importa, sino que solamente nos importa la pertenencia de un dato a la lista. En caso como este, los conjuntos son perfectos. Un ejemplo de esto sería tener un conjunto que contiene una lista de términos que no se permite usar como nombre de usuario, al recibir un nuevo nombre de usuario simplemente revisamos si este nombre está dentro del conjunto para saber si es permitido.