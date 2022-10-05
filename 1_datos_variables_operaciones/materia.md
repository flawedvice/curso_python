# Introducción
En esta sección revisaremos los tipos de datos, las variables y las operaciones que podemos realizar sobre estas.

&nbsp;

# Tipos de datos en Python
Lo primero a notar es que aquí estaremos hablando de los tipos de datos específicos de Python.

Como ya se habló en la introducción, existen varios lenguajes de programación, cada uno con sus pros y contras, y cada lenguaje tiene algunas diferencias sutiles en torno a los tipos de datos que maneja de manera nativa.

Si bien hay más tipos de los que mostraremos a continuación, estos son los más utilizados y básicos:

- Datos Numéricos:
    - `int`: Representa números enteros. Ej.: 1, -4, 132
    - `float`: Representa números de punto flotante, es decir, con decimales. Ej.: 1.2, -4.0, 132.009
- Texto:
    - `str`: Representa "strings" o, en español, cadenas de texto.
- Booleanos:
    - `bool`: Un booleano representa un valor lógico, es decir, puede representar que algo es verdadero (`True`) o falso (`False`)
- Nulo o Nada:
    - `NoneType`: Por simplicidad, utilizaremos "nulo" y "nada" de manera intercambiable. Para ello, este valor será escrito como `None`.

&nbsp;

Todo esto toma tiempo entenderlo; especialmente los datos booleanos y "Nada", pero lo desglozaremos con ejemplos para que se entiendan con facilidad.

&nbsp;

## Ejemplos prácticos:
### Números en Python:
Si nos presentan los siguientes valores:

```Python
1, 43, -123, 4390, 43.2, -12.5, 1243.01, 5.
```

Sabemos que se trata de valores numéricos, pero ¿cómo discernimos si son de tipo `int` o `float`?
Al igual que en las matemáticas del día a día, los valores enteros son `int` y aquellos con decimales (aunque el decimal sea `0` o no haya un número) serán de tipo `float`:

```Python
int = 1, 43, -123, 4390
float = 43.2, -12.5, 1234.01, 5.
```
Aquí no nos importa el signo que tengan; ya sean números positivos o negativos, lo que nos importa es saber si tienen la coma (o punto) decimal o no.

&nbsp;

### Texto en Python
En Python, una cadena de texto o 'string' es cualquier conjunto de caracteres encerrados en comillas simples (`''`) o dobles (`""`).

Algunos ejemplos de cadenas de texto son:
```Python
"Curso de Python para principiantes"
'Aprendiendo Python'
"123"
"True"
```
Es importante destacar que, si bien `123` es de tipo `int` y `True` (más adelante lo veremos) es de tipo `bool`, ambos están encerrados entre comillas, por lo que son en realidad cadenas de texto.

Ejemplos erróneos de cadenas de texto son:
```Python
'Las comillas deben ser iguales"

"Deben haber comillas al inicio y al final
```

&nbsp;

### Booleanos en Python:
Los booleanos surgen de lo que se conoce como "Álgebra Booleana", donde básicamente se trabaja con expresiones lógicas como "Hoy está nublado" o "Mi guitarra es roja".

Estas expresiones pueden traducirse al lenguaje booleano:

$$
\text{Verdadero o Falso}
$$

Una expresión booleana siempre se traduce a uno de dos valores, $Verdad$ o $Falso$ en español, `True` o `False` respectivamente en Python.

Ejemplos:
```Python
True
False
```

&nbsp;

### La Nada en Python:
La mejor manera de entender cómo Python maneja "la nada" y por qué se hace necesario es con un ejemplo de la vida real.

Imagina que tienes una mesa frente a ti. No hay **nada** encima. Si alguien te pregunta "¿Qué hay en la mesa?", ¿qué le responderías?

Nos podríamos poner creativos y decir que "hay **0 cosas**", pero lo normal es que respondamos con "**Nada**".

De la misma forma, en programación muchas veces necesitaremos decirle al computador que algo "contiene **nada**".

Ejemplo:
```Python
None
```

&nbsp;


&nbsp;

---

&nbsp;


&nbsp;

# Variables
Las variables son la forma más básica de almacenar valores.

Una variable es como una caja en la que podemos almacenar distintos **datos**.

Decimos que las variables son de cierto **tipo de dato** dependiendo del dato que albergue; en otras palabras, una variable es de tipo `str` si el valor que contiene es, por ejemplo, "abc".

Al igual que una caja, una variable puede estar **vacía**.

&nbsp;

## Sintaxis:
Para definir una variable en Python se debe cumplir con lo siguiente:

- Solo puede contener caracteres alfanuméricos y guiones bajos (A-Z, 0-9 y _).
- No puede empezar por un número.

Por otra parte, se suelen seguir convenciones propias de Python:

- Para variables largas se utiliza la notación "*snake_case*", donde se reemplazan los espacios por guiones bajos.
- Para variables que no sean "*clases*" (los veremos en la sección 8 sobre Programación Orientada a Objetos), deben ser escritas en minúscula.

Podemos **definir** una variable con tan solo escribir:
```Python
name
```
¡Con eso tenemos una variable llamada `name`! Así de simple.

Ahora, **definimos** una variable, pero la gracia está cuando a las variables les **asignamos** un valor.

Esto lo hacemos de la siguiente forma:

```Python
name = "Alex"
```
A la variable `name` le **asignamos** el valor `"Alex"`, el cual es de tipo `str`.


Algunos ejemplos de variables correctamente definidas:
```Python
name = "Alex"       # str
age = 19            # int
height = 1.78       # float
is_student = True   # bool
courses_chosen = None      # NoneType
```
En el código anterior **definimos** 5 variables con diferentes tipos de datos a las que **asignamos** diferentes valores.

A continuación tenemos variables definidas de forma incorrecta y otras de manera no recomendable:
```Python
# Variables mal definidas:

n@me = "Alex"       # No puede tener símbolos.
4ge = 19            # No puede empezar con un número.
is-student = True   # No puede usar guión simple.


# Variables no recomendadas:

Height = 1.78   # Las mayúsculas se suelen reservar para clases.
coursesChosen = None    # El estándar es snake_case, no camelCase.
```

&nbsp;


&nbsp;

---

&nbsp;


&nbsp;

# Operaciones:

Ya tenemos datos almacenados en variables, por lo que ahora veremos cómo podemos **manipular** dichos datos.

En Python existen lo que se llama **Operadores**. Estos son símbolos que representan operaciones aritméticas (como la *suma*, la *resta*, *multiplicación*, etc...), nos permiten asignar y comparar valores, y aplicar lógica.

Veremos los principales operadores en cada uno de estos grupos para luego dar ejemplos de sus usos.

&nbsp;

## Operadores aritméticos:

|Operador|Descripción|
|--------|-----------|
|+       |Suma
|-       |Resta
|*       |Multiplicación
|/       |División
|%       |Módulo
|**      |Exponenciación
|//      |División Entera

&nbsp;

### Ejemplos:
```Python
# Suma
1+2     # 3

# Resta
4-2     # 2

# Multiplicación
2*3     # 6

# División
9/3     # 3

# Módulo
5%2     # 1 , si dividimos 5 entre 2, nos sobra 1

# Exponenciación
2**3    # 8 , dos al cubo

# División Entera
7//3    # 2 , 3 cabe solo 2 veces en el 7
```