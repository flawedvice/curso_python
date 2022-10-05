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
## *List Comprehensions*
## *Slicing*

&nbsp;


&nbsp;

---

# *Strings*