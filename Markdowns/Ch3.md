# Capitulo 3: Operadores y expresiones

## Objetivos

    Operadores aritméticos, relacionales, lógicos, de asignación, de membresía y de identidad.

    Evaluación de expresiones: precedencia y asociatividad

## Operadores

Los operadores son simbolos especiales que se utilizan para aplicar operaciones sobre datos y variables. Todas las operaciones deben tener la forma: operando1 **operador** operando2

### Aritméticos

Se utilizan para operaciones matemáticas 

| Simbolo  | Uso                  | Ejemplo     | Nota             |
|----------|----------------------|-------------|------------------|
| **+**    | Suma                 | 1 + 1 = 2   | Funciona con str |
| **-**    | Resta                | 2 - 1 = 1   |                  |
| **\***   | Multiplicación       | 2 * 3 = 6   | Funciona con str |
| **/**    | División             | 3 / 3 = 1.0 | Retorna un float |
| **%**    | Resto de división    | 3 % 2 = 1   |                  |
| **\*\*** | Potencia             | 2 ** 3 = 8  |                  |
| **//**   | División sin decimal | 5 / 2 = 2   | Retorna un int   |

### Relacionales

Se utilizan para comparar diferentes variables, siempre generan un bool. Permiten incluir operaciones como operandos

| Simbolo | Uso               | Ejemplo       |
|---------|-------------------|---------------|
| **==**  | Igual que         | n1 == 2       |
| **!=**  | No es igual que   | n1 % 2 != 0   |
| **>**   | Mayor que         | n1 > n2       |
| **<**   | Menor que         | n1 < n2 + 1   |
| **>=**  | Mayor o igual que | n1 >= n2 + n3 |
| **<=**  | Menor o igual que | n0 * n1 <= n2 * n3 |

**Nota:** Pueden usarse para comparar 2 datos, pero no tienen sentido porque sería equivalente a simplemente utilizar True o False.

**Nota:** Al agregar operaciones como operandos lo que se compara son sus resultados, realizandose las operaciones antes de aplicar el operador relacional, por ejemplo: **n0 * n1 <= n2 * n3**, se toma como **(n0 * n1) <= (n2 * n3)**

### Lógicos

Operadores que conectan o afectan booleanos para generar un nuevo bool. Todas las operaciones de relacionales puede utilizarse dentro de una operación de lógicos

| Simbolo | Uso                                | Ejemplo                        |
|---------|------------------------------------|--------------------------------|
| and     | Retorna True si los 2 son True     | n1 > 0 and n1 < 10             |
| or      | Retorna True si al menos 1 es True | n1 == 1 or n1 == 10            |
| not     | Retorna el opuesto                 | not (n1 <= n2 and n1 % 2 == 0) |

**Nota:** Si tuvieramos variables que se usan como bools, estas también son permitidas dentro de una operación de lógicos, por ejemplo:

```
var = True
n1 = int(input())
res = var and n1 <= 10
``` 

### De Asignación

Operadores que guardan el resultado del segundo operando en una variable (la cual debe ser el primer operando). La mayoría de estos puede ser representado por un equivalente utilizando =, existen formas de asignación de todos los operadores aritméticos.

| Simbolo | Ejemplo       | Equivalente         |
|---------|---------------|---------------------|
| =       | n1 = 5        |                     |
| +=      | n1 += 5       | n1 = n1 + 5         |
| -=      | n1 -= 6       | n1 = n1 - 6         |
| *=      | n1 *= 2       | n1 = n1 * 2         |
| /=      | n1 /= 2 * n2  | n1 = n1 / (2 * n2)  |
| %=      | n1 %= 3       | n1 = n1 % 3         |
| //=     | n1 //= 3 * n2 | n1 = n1 // (3 * n2) |
| **=     | n1 **= 2 + n2 | n1 = n1 ** (2 + n2) |

### De Membresía

Operadores que revisan si un dato o variable pertenece a una lista

| Simbolo | Uso                                         | Ejemplo               |
|---------|---------------------------------------------|-----------------------|
| in      | Retorna True si op1 está en la lista        | res = n1 in lista     |
| not in  | Retorna True si op1 **NO** está en la lista | res = n1 not in lista |

### De identidad

Operadores que revisan si los operandos son iguales

| Simbolo | Uso                                       | Ejemplo            |
|---------|-------------------------------------------|--------------------|
| is      | Retorna True si op1 y op2 son iguales     | res = n1 is n2     |
| is not  | Retorna True si op1 **NO** es igual a op2 | res = n1 is not n2 |

**Nota:** En este momento estos operadores son redundantes, esto es porque principalmente se usan con objetos, no con variables normales

## Evaluación de operaciones

Existen ciertas reglas dentro del lenguaje para decidir el orden en el que se realizan las operaciones

### Precedencia

La precedencia elije cuál operación se realiza primero, el orden de primero a último es:

1. ()
2. **
3. *, /, //, %
4. +, -
5. Relacionales, de membresía y de identidad.
6. not
7. and
8. or

### Asociatividad

Si se da un empate en precedencia, la asociatividad decide cuál operación se realiza primero. 

La asociatividad es **de izquierda a derecha** en todos los operadores **excepto la potencia**, en ese caso es de derecha a izquierda, por ejemplo:

n1 = n1 ** 2 ** 3 => n1 = n1 ** (2 ** 3)

