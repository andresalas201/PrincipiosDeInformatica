# Capítulo 2: Variables y valores

    Tipos de datos fundamentales: enteros, flotantes, booleanos, caracteres, cadenas de caracteres.
    
    Concepto de mutabilidad e inmutabilidad
    
    Variables: nombramiento, inicialización, asignación

    Conversión de tipos

## Tipos de Datos fundamentales

Los tipos de datos fundamentales son los tipos de datos más básicos que da un lenguaje de programación. También se les llama datos primitivos.

### Int

Los Int o integers contienen números enteros. En general estos tienen un número máximo, pero Python permite que el número siga creciendo hasta donde la memoria de la máquina lo permita. Pueden ser negativos o positivos.

### Float

Los Float o flotantes tienen la capacidad de contener números con decimales. Debido a las limitaciones de las computadoras, los flotantes pueden tener pequeños errores de precisión, por ejemplo: 0.1 + 0.1 + 0.1 no suele ser igual a 0.3. Mantienen un máximo de 15 a 17 digitos significativos.

### Bool

Los Bool o booleanos solamente pueden contener 2 valores: True (verdadero) o False (falso). Este tipo de dato es utilizado para el manejo de instrucciones condicionales.

### Char

Los Char o caracteres contienen un caracter ASCII (letras y simbolos). ASCII es una forma de representar letras y una serie de simbolos en una computadora, no es necesario para el curso, pero pueden revisar [La Tabla ASCCI completa](https://www.ascii-code.com/) en internet. Las Chars se denotan utilizando '(letra)', por ejemplo:

```
ch = 'a'
``` 

**NOTA:** En caracteres, a veces van a notar el uso del caracter "\", este es un caracter especial que activa comandos, estos comandos se llaman caracteres de escape, por ejemplo:

1. **\n:** Cambio de linea
2. **\t:** Agrega un espacio de tabulador
3. **\\:** Escribe un \

### Str

Las Str o string contienen una serie de Chars. Las string no son un tipo de dato fundamental, pero son lo suficientemente comunes para que en general se les trate como tal. Al contener una serie de Chars, los caracteres de escape pueden ser usados dentro de una string. La string se denota utilizando "", por ejemplo:

```
ch = "Hola!\t"
```

**Nota:** El comando input() retorna una string

## Mutabilidad e inmutabilidad

Mutabilidad se refiere a la capacidad de un tipo de dato de ser modificado sin tener que crear un objeto nuevo.

### Inmutables

Los tipos de datos vistos hasta ahora (int, float, bool, char y str) son inmutables, cada vez que asignamos un nuevo valor, que le sumamos un número, etc. se crea un nuevo objeto desde 0 el cuál es guardado en la variable que queramos.

### Mutables

Los mejores ejemplos de tipos mutables son los tipos que no contienen datos singulares, sino que guardan series de datos de diferentes tipos, estos son list (lista), set y dict (diccionarios). Estos tipos de datos serán explicados a fondo en el capítulo 8.

## Uso de variables

Las variables almacenan datos, funcionan como el nombre o identificador de un dato y permiten que guardemos y manipulemos el dato.

### Nomenclatura

Los nombres de las variables tienen una serie de reglas:

1. Inician con una letra o un _
2. Los nombres son sensibles a mayúsculas (N1 y n1 son variables diferentes)
3. No tienen espacios
4. No pueden ser iguales a los nombres reservados (print, if, elif, etc.)

### Inicialización

Las variables deben ser creadas, esto se logra simplemente escribiendo su nombre en el código:

```
n1 = 1
``` 

### Asignación

Utilizando el igual (=) podemos cambiar el dato que está de una variable:

```
n1 = 1
n1 = "hola"
n1 = 2.3
n1 = n1 + 1.0
``` 

Como se ve en la última linea, a la derecha del igual es posible realizar operaciones y utilizar variables (incluso la misma variable que estamos guardando).

En Python, una sola variable puede cambiar el tipo de dato que guarda, esto **NO** es posible en la mayoría de lenguajes de programación.

## Conversión

La conversión es el proceso de tomar un dato y convertirlo a su equivalente en otro tipo de dato sin directamente afectar su valor. Por ejemplo, si queremos convertir la string "123" al valor númerico 123 lo hacemos de la siguiente manera:

```
num = "123"
n1 = int(num)
``` 

También puede escribirse directamente el dato (sin usar una variable), esto se hace de la siguiente manera:

```
n1 = int("123")
``` 

Para los tipos de datos vistos, las conversiones se hacen de forma fácil escribiendo el tipo de dato al que queremos convertir seguido de parentesis, por ejemplo:

```
n1 = int("123")
n2 = float(15)
n3 = str(123.5)
```

**Nota:** En algunos casos puede que no sepan el tipo de un dato, en esos casos pueden usar el método type(), este se utiliza de la siguiente manera:

```
print(type(n1))
```