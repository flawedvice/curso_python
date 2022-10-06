# Introducción
En esta sección revisaremos la estructura más común en los lenguajes de programación: Listas.

Por otra parte, revisaremos un tipo especial de lista llamada 'string', o 'cadena de texto'.

&nbsp;


&nbsp;

# Listas
En las ciencias de la computación existe una estructura que ha recibido diversos nombres, dependiendo especialmente del lenguaje de programación:

Vector, '*Array*', Matriz, Lista, etc...

En general, se trata de la misma estructura: una collección de datos.

En Python, esta estructura es llamada '*List*', y la sintaxis para crear una **lista** es la siguiente:
```Python
my_list = []
# O utilizando su función constructora
my_other_list = list()
```
De cualquier manera, ambos métodos resultan en una lista vacía:

```Python
print(my_list)
# []
```

&nbsp;

## Características básicas de las Listas
Las listas pueden contener muchos elementos separados por una coma (,), así como pueden estar vacías:
```Python
empty = []
numbers = [1, 2, 3, 4]
bools = [True, False, False]
strings = ['Hello', 'World']
```
Los elementos no tiene por qué ser del mismo tipo. Pueden haber listas que utilicen combinaciones de ellos:
```Python
mix = ['Hello', 12, False, 43.2, None]
```

Cada vez que agregamos un elemento a una lista, se le asigna a dicho elemento un número llamado **índice**, el cual nos indica la ubicación del elemento al interior de la lista.

El primer elemento en una lista **siempre tendrá el índice `0`**, el segundo tendrá el índice `1` y así:

```Python
# index  0  1  2  3
list = [ 1, 2, 3, 4 ]
```

&nbsp;

## Operaciones básicas
Las listas tienen 4 operaciones básicas:
- Añadir elementos
- Leer elementos
- Actualizar valores
- Eliminar elementos

Veamos cada una de estas operaciones en detalle.

&nbsp;

### Añadir elementos:

Imaginemos que partimos con una lista vacía:
```Python
# Inicializamos una lista
my_list = []
```

Ahora, añadiremos la cadena de texto (`string`) `'Hello'` utilizando un método propio de las listas:
```Python
my_list.append('Hello')

print(my_list)
# [ 'Hello' ]
```
`append` (*adjuntar* en español) es un **método** de las listas para **añadir elementos al final** de la lista.

Si ahora agregamos un valor booleano `True` a la lista, obtendremos lo siguiente:
```Python
my_list.append(True)

print(my_list)
# [ 'Hello', True ]
```

&nbsp;

### Leer elementos:
¡Súper! Creamos una lista y le agregamos dos elementos, pero, ¿qué pasa si quiero utilizar los elementos que guardé?

¡Podemos **leer** los elementos de una lista si conocemos sus **índices**!

Para ello, utilizamos la siguiente notación:

```Python
my_list[index]
```
Digamos que queremos leer el primer elemento de nuestra lista para poder guardarlo en una variable:
```Python
my_var = my_list[0]

print(my_var)
# 'Hello'
```
***Importante:*** ¡Recuerda que el primer elemento siempre tiene el índice `0`!

&nbsp;

### Actualizar valores:
Recordando que nuestra lista es la siguiente:
```Python
[ 'Hello', True ]
```
Nos damos cuenta que el segundo valor no debía ser `True` sino `'World'`.

Podemos cambiar los valores de una lista de manera similar a la que leemos sus valores:

```Python
my_list[1] = 'World'

print(my_list)
# [ 'Hello', 'World' ]
```
Esta vez tomamos el segundo elemento de la lista (usando el índice 1) y le reasignamos un valor; en este caso, `'World'`.

&nbsp;

### Eliminar elementos:
Ya añadimos, leímos y cambiamos los elementos de nuestra lista, pero sucede que ahora queremos que vuelva a estar vacía.

Podemos eliminar elementos de una lista a través del método `pop()`:
```Python
# Eliminamos el último elemento:
my_list.pop()
print(my_list)
# [ 'Hello' ]

# Volvemos a eliminar el último elemento
my_list.pop()
print(my_list)
# []
```

### Nota Importante:
En programación suele existir más de una forma de hacer las cosas, y las operaciones en listas no son la excepción.

Existen más métodos para añadir y eliminar elementos, pero los revisaremos más adelante.

&nbsp;


&nbsp;

# Listas como estructuras "iterables"

Una iteración es, básicamente, una repetición o un ciclo.

Los ciclos como aquellos formados con un `for` nos permiten **iterar** sobre cierto componente.

En este punto es probable que estén familiarizados con un snippet como el siguiente:
```Python
for i in range(10):
    print(i)
    # Imprime todos los números del 0 al 9
```
Aquí **iteramos** sobre un rango del 0 al 9.

Ahora, podemos hablar de que existen **estructuras iterables**; esto es, estructuras que podemos **recorrer con un ciclo o *loop***.

Con un ejemplo, esta sería otra forma de imprimir los números del 0 al 9:
```Python
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

for n in numbers:
    print(n)
```
Puedes copiar ese código y correrlo en tu terminal. Verás que imprime lo mismo que el snippet que vimos antes.

Eso es porque las **listas** son objetos **iterables**.

Esto conlleva una serie de ventajas, como poder realizar fácilmente operaciones sobre todos los elementos de una lista, o incluso aplicar control de flujo.

&nbsp;


&nbsp;

# Propiedades de las listas
Las listas son unas de las estructuras más comunes y simples de Python, donde la propiedad de la que más se hará uso es su **longitud**, o cantidad de ítems.

Para saber la cantidad de ítems que posee una lista, podemos escribir:
```Python
print(len(my_list))
# len() retorna la "longitud" de la lista.
```

&nbsp;


&nbsp;

# Métodos de las listas
En cuanto a métodos, es decir, **funciones propias** de las listas, podemos describir los siguientes:

|Esencial|Método|Descripción|Modo de uso|
|--------|------|-----------|-----------|
|Sí|`append()`|Añade un ítem al final de la lista.|`my_list.append(new_item)`|
||`insert()`|Añade un ítem en el índice especificado.|`my_list.insert(index, new_item)`|
||`extend()`|Añade los ítems de otro iterable al final de la lista.|`my_list.extend(other_iterable)`|
||`remove()`|Elimina el ítem especificado.|`my_list.remove(item)`|
|Sí|`pop()`|Elimina el último ítem o aquel en el índice especificado.|`my_list.pop([index])`||
||`clear()`|Elimina todos los elementos de la lista.|`my_list.clear()`|
||`copy()`|Genera una copia de la lista.|`my_list.copy()`|
|Sí|`count()`|Retorna la cantidad de elementos con el valor especificado.|`my_list.count(item)`|
|Sí|`index()`|Retorna el índice del primer elemento con el valor especificado.|`my_list.index(item)`|
|Sí|`reverse()`|Invierte el orden de la lista.|`my_list.reverse()`|
|Sí|`sort()`|Ordena la lista de manera ascendente.|`my_list.sort([reverse=False],[ key=func])`|

**Nota:** Los corchetes al interior de los paréntesis de un método indican que el parámetro encerrado es **opcional**.

&nbsp;


&nbsp;

# Conceptos Avanzados

## Chequear elementos presentes:
Podemos chequear rápidamente si un elemento se halla en una lista con:
```Python
if 4 in [1,2,3,4]:
    print("Found!")
else:
    print("Not found")

# Found

if 37 in [1,2,3,4]:
    print("Found!")
else:
    print("Not found")

# Not found
```

&nbsp;

## *List Comprehensions*
Anteriormente vimos que habían dos maneras de crear una lista:
```Python
my_list = []
other_list = list()
```

Sin embargo, existe una tercera forma llamada ***list comprehensions***.
Inicialmente puede costar algo de trabajo entendiendo lo que está pasando, pero vamos paso a paso:

Imaginemos que queremos una lista con el cuadrado de los números del 1 al 10; algo así como esto:
```Python
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
Podríamos intentar algo como esto para lograrlo:
```Python
my_list = []

for i in range(1,11):
    result = i**2
    my_list.append(result)

print(my_list)
# [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

Eso funciona bastante bien, pero es una tarea bastante sencilla que muchas veces quisiéramos que ocupara el menor espacio posible y fuera rápida de hacer...

Bueno, podemos lograrlo con una *list comprehension*:

```Python
my_list = [ x**2 for x in range(1,11) ]

print(my_list)
# [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
Podemos leerlo como:
"Crea una lista con el cuadrado de cada *x* en un rango del 1 al 11."

&nbsp;

## Acceso avanzado en listas
Ya sabemos que podemos acceder a los valores de una lista con la notación &nbsp; `my_list[index]`, pero, ¿qué pasa si queremos acceder a un segmento más grande de la lista?

Utilizando una notación parecida, podemos tomar un segmento o rango de elementos de una lista:
```Python
my_list = [1, 4, 9, 16, 25, 36, 49]

list_segment = my_list[1:4]
print(list_segment)
# [4, 9, 16]
```
Lo que acabamos de hacer es seleccionar los elementos que van desde el índice 1 (segundo elemento) hasta el índice 4 (exclusivo).

Si quisiéramos obtener los primeros 4 elementos podemos omitir el primer índice:
```Python
first_four = my_list[:4]
print(list_segment)
# [1, 4, 9, 16]
```

Si deseáramos obtener los últimos 3 elementos, omitimos el segundo índice **pero siempre mantenemos los puntos ":"**:
```Python
last_three = my_list[4:]
print(list_segment)
# [25, 36, 49]
```

&nbsp;
Por otra parte, un detalle importante a recalcar es que en una lista podemos acceder a sus elementos de atrás para adelante (los últimos a los primeros) utilizando índices negativos.

Por ejemplo, si deseamos obtener el último y penúltimo ítem:
```Python
last = my_list[-1]
second_to_last = my_list[-2]
print(last, second_to_last)
# [49, 36]
```
Y al igual que los índices positivos, también podemos utilizar índices negativos al tomar segmentos:
```Python
segment = my_list[4:-1]
print(segment)
# [25, 36]
```

&nbsp;


&nbsp;

---

&nbsp;


&nbsp;

# *Strings*
Finalmente, las ***Strings*** o *cadenas de texto*.

¿Por qué vemos esto al final de las listas si ya sabemos que son un tipo de dato en Python (primeras clases, dah)?

Bueno, si bien en Python "son" un tipo de dato, originalmente las *strings* no existían como tal, sino que para crear un texto debías crear una **lista de caracteres**.

Así es, las *strings* no son más que listas de caracteres, y en lugar de crearlas con corchetes (`[]`) las creamos con comillas (`"" ''`).

Por lo tanto, las *strings* poseen las mismas propiedades y métodos que las listas con algunas pocas excepciones.

Dichas excepciones son algunos métodos propios, los cuales son tantos y tan variados que dejaré un enlace a la documentación que los muestra en detalle:

[W3Schools Python Strings](https://www.w3schools.com/python/python_strings_methods.asp)

&nbsp;

## Cadenas Multilínea:
Podemos escribir una *string* multilínea usando triples comillas de la forma:
```Python
multiline = """This is
                a multiline
                string!"""
```

&nbsp;

## Formateo de *Strings*:
Como uso avanzado de las *strings* es necesario mostrar que podemos formatearlas para utilizar elementos dinámicos, como alguna variable, en su interior.

Por ejemplo, si quisiera saludar a un usuario por su nombre (el cual claramente no lo sé :p) puedo formatear una cadena para mostrarlo:
```Python
name = 'Ada Lovelace'

greetings = f"Welcome, {name}!"

print(greetings)
# Welcome, Ada Lovelace!
```

Existen otras formas de formatear una cadena, como las siguientes que tienen el mismo resultado:
```Python
name = 'Ada Lovelace'
print("Welcome, {}!".format(name))
# Welcome, Ada Lovelace!

print("Welcome, ", name, "!")
# Welcome, Ada Lovelace!
```
Sin embargo, la primera versión es la más sucinta y común, por tanto, la más recomendable.

&nbsp;

## Buscar palabras en cadenas:
Podemos, al igual que en las listas, chequear si palabras se hallan o no al interior de una *string* con el operando `in`:
```Python
if "Hello" in "Hello World!":
    print("Found!")
else:
    print("Not found")

# Found!

if "The Cake" not in "Hello World!":
    print("is real!")
else:
    print("is a lie")

# is real!
```

&nbsp;

## Splitting & Joining
Si bien las strings son un tipo especial de lista, podemos convertir a una string en una lista de substrings dividiéndola bajo algún criterio específico.

Por ejemplo, podemos dividir una cadena en subcadenas separándola en cada espacio:
```Python
my_str = 'the brown fox jumps over the lazy dog'

my_list = my_str.split()

print(my_list)
# ['the', 'brown', 'fox', 'jumps', 'over', 'the', 'lazy', 'dog']
```
Ese es el método `split()` de las cadenas.

Podemos especificar el caracter por el cual separar la cadena; por ejemplo, podemos separarla por cada coma (`,`):
```Python
'FAANG means Facebook, Apple, Amazon, Netflix and Google'.split(',')

# ['FAANG means Facebook', ' Apple', ' Amazon', ' Netflix and Google']
```
Por otra parte, podemos realizar el proceso inverso, esto es, convertir una lista en una cadena, utilizando el método `join()`.

Este método se utiliza de una manera diferente. Aquí debemos aplicar el método sobre la subcadena que servirá de "pegamento" para la lista, y esta última será el parámetro a utilizar:
```Python
",".join(['FAANG means Facebook', ' Apple', ' Amazon', ' Netflix and Google'])

# 'FAANG means Facebook, Apple, Amazon, Netflix and Google'
```

&nbsp;

## Concatenación
Un tópico importante cuando se habla de cadenas de texto es la concatenación; esto es, la unión consecutiva de cadenas.

En Python es bastante simple: Solo debemos "*sumar*" las cadenas:
```Python
'Hello' + ' ' + 'World' + '!'
# Hello World!
```

Recuerda que las cadenas de texto son listas especiales. También podemos concatenar listas de esa misma forma:
```Python
[ 1, 2, 3 ] + [ 4 ]
# [ 1, 2, 3, 4 ]
```

&nbsp;


&nbsp;

---

&nbsp;


&nbsp;

# Bonus: REGEX