# Capitulo 4: Errores y pruebas

## Objetivos

    Conceptos de error lógico y error de ejecución

    Importancia de la corrección de programas

    Pruebas de software de caja negra

## Errores

Los errores (bugs) en programación se refieren a problemas en el código que hacen que este no se ejecute de la manera debida. Un bug puede causar todo tipo de problemas, desde guardar un dato en la variable incorrecta hasta causar que el programa deje de seguir en su totalidad.

### Error lógico

Es un tipo de error que se da cuando el programa puede correr correctamente, pero no genera los resultados que se querían. Este tipo de errores pueden ser causados por todo tipo de errores, algunos de los más comunes son:

1. Escribir mal la variable
2. Usar el operador incorrecto
3. Entender mal una sección del problema

La gran mayoría del tiempo que pasen buscando y arreglando bugs va a ser debido a bugs de este tipo, son especialmente difíciles de encontrar porque hay que revisar todo el código buscando la fuente del error.

### Error de ejecución

Es un tipo de error que causa que la ejecución pare completamente, ocurren cuando el código intenta hacer algo que no es posible. Algunas de las formas de causar este error son:

1. División entre cero
2. Acceder a una posición inexistente en una lista
3. Uso inválido de un tipo de dato

Estos errores son fáciles de detectar, Python genera todo un mensaje de error que nos dice la línea donde pasa el error, el tipo de error y su causa. Existen muchos tipos diferentes de errores de ejecución, si quisieran saber más al respecto pueden [revisar este link](https://www.w3schools.com/python/python_ref_exceptions.asp).

### Importancia del manejo de errores

Hoy en día, las computadoras y el software son necesarias para todo. El software maneja muchas de las funciones de la sociedad moderna, entre estos están el pago con tarjeta, el vuelo de los aviones, historiales médicos, etc.

Errores en muchos de estos casos pueden llevar a perdidas enormes de dinero o incluso directamente a la muerte de seres humanos. Algunos ejemplos famosos son:

1. **Ariane V:** Un error de código hace que el cohete Ariane V se auto destruyera unos segundos después del despegue.
2. **Red de AT&T:** Una mal manejo de reinicio en los routers de la red de larga distancia de AT&T causa un fallo en cascada que termina en perdidas de decenas de millones de dólares para AT&T
3. **Error de Crowdstrike:** Una actualización a un software de la compañía Crowdstrike causa un error en manejo de memoria que afecta a millones de sistemas Windows, esto causa perdidas de miles de millones de dólares.
4. **Therac-25:** Un bug causa que una máquina de radiación emitiera mucha más radiación de la debida, causando la muerte de pacientes.

## Pruebas de caja negra

Una prueba de caja negra consiste en hacer revisiones de un código basandose en una serie de entradas con respuestas correctas conocidas. Por ejemplo, probamos una calculadora enviandole la entrada "1 + 1", a lo cuál esta debe responder "2". Este tipo de pruebas buscan hacer revisiones de código sin la necesidad de ver o conocer directamente el código, simplemente se basan en lo que el código debería de hacer.

### Uso

Las combinaciones entrada-salida con las que se hacen las pruebas son llamadas **casos**. En general, mientras más complicado sea el código más casos deberían probarse, pero en general se buscan probar 3 casos:

1. **Caso normal:** Un caso completamente normal para el software probado, en el caso de la calculadora podemos usar cualquier operación como el caso "1 + 1" - "2" mencionado anteriormente.
2. **Caso de borde (edge case):** Un caso poco común que suele generar algún problema si no pensamos directamente en él. En el caso de la calculadora, podemos utilizar un caso como "1 + 2 / 2" - "1", este podría causar problemas si no manejamos correctamente el orden de operaciones.
3. **Caso de error:** Un caso que no debería servir o que causa un error (que debe ser manejado), este tipo de caso permite revisar si nuestro código está preparado para recibir datos incorrectos y puede manejarlos sin causar problemas serios. En el caso de la calculadora, podemos agregar un caso como "2 / 0" - "error", esto debido a que la calculadora debería ser capaz de detectar la división entre 0 sin problemas.
