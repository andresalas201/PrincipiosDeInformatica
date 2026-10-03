# Capitulo 9: Introducción al uso de bibliotecas

## Objetivos

    Concepto de bibliotecas

    Exploración de documentación de bibliotecas

    Importación de bibliotecas a un programa de elaboración propia

## Concepto

Una biblioteca (muchas veces traducida de forma incorrecta como librería) es una colección de código que puede ser importada y ser usada dentro de código propio. Las bibliotecas nos permiten reutilizar código y funcionalidades ya creadas y usarlas en nuestro código sin necesidad de escribir esas funcionalidades a mano.

Las bibliotecas pueden tener todo tipo de usos, desde temas simples como agregar Pi y Euler, hasta dar la capacidad de entrenar modelos de inteligencia artificial de alta complejidad. Una de las mayores razones del uso de Python en la actualidad es la alta cantidad de bibliotecas disponibles.

## Documentación

Las bibliotecas suelen tener una página que contiene explicaciones a fondo de las diferentes subtrutinas o estructuras de datos que existen en la biblioteca. Esta serie de explicaciones es llamada documentación y es un parte importante de toda biblioteca. Desde el punto de vista de un usuario de la biblioteca, siempre es útil darle una ojeada a la documentación cuando no entendemos el funcionamiento de algo dentro de una biblioteca. Es importante saber que prácticamente toda la documentación está escrita en inglés, en este curso se les dará mucha de esta información en español, pero no es verdaderamente posible traducirles toda la documentación de todas las bibliotecas que se usarán durante el curso.

Algunos ejemplos de documentación en página web de las bibliotecas que usaremos durante el curso son:

- [Math](https://docs.python.org/3/library/math.html)
- [NumPy](https://numpy.org/doc/2.5/)
- [Pandas](https://pandas.pydata.org/docs/user_guide/index.html)
- [MatPlotLib](https://matplotlib.org/stable/users/index)

## Uso

Para usar una biblioteca, es necesario instalarla primero, esto se logra mediante un programa llamado **pip**, el cuál fue su instalado junto con Python. Para instalar la biblioteca, simplemente se abre una consola y se utiliza el comando pip install [nombre]. Incluso se pueden instalar múltiples bibliotecasen un solo comando. Por ejemplo, para instalar las bibliotecas mencionadas anteriormente, simplemente se usa el siguiente comando:

```
pip install numpy pandas matplotlib
```

### Import

Teniendo la biblioteca instalada, simplemente se debe importar para utilizarla dentro de nuestro código. La importación se hace con el comando **import**, esto funciona de la siguiente manera:

```
import math
```

Al importar de esta manera, debemos utilizar el prefijo **math.** para utilizar cualquier función de la biblioteca. Por ejemplo, si queremos calcular el resultado de un coseno de 90, utilizamos el siguiente código:

```
import math

print(math.cos(90))
```

En algunos casos, las bibliotecas tienen nombres muy largos o simplemente queremos usar un nombre específico para llamarlas, en ese caso, se usa el comando **as**. Un ejemplo de este comando es:

```
import math as m

print(m.cos(90))
```

Este nuevo código hace lo mismo que el anterior, pero como le damos a math el alias de m, todos los llamados **math.** se cambian a **m.**.

### From

Existen casos en los que queremos importar una sección especifica de una biblioteca grande, en ese caso utilizamos el comando **from**. Por ejemplo, imaginen que queremos importar math, pero solamente la capacidad de calcular senos y cosenos. Esto se logra con el siguiente código:

```
from math import sin, cos

print(cos(90))
print(sin(90))
```

Como pueden notas, al importar con from, no es necesario usar el nombre de la biblioteca ni su alias.

### Importación de código propio

Python también permite importar nuestro propio código, por ejemplo, imaginemos que tengo una serie de funciones matématicas en un archivo llamado funciones.py:

```
def suma(a, b):
    return a + b

def resta(a, b):
    return a - b
```

Si yo quisiera llamar este código desde un archivo separado, puede utilizar un import. Esto se hace de la siguiente manera:

```
import funciones as f

print(f.suma(1, 5))
```

Si funciones.py no está en el mismo directorio, se utiliza import [Nombre de carpeta].funciones para importarlo. Por ejemplo, imaginemos que funciones.py está en una carpeta llamada codigos, para importarla utilizamos el siguiente código:

```
import codigos.funciones as f

print(f.suma(1, 5))
```