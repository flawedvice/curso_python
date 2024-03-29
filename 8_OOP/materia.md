# Introducción
**OOP** o *Programación Orientada a Objetos* es un paradigma común de programación soportado por una mayoría de los lenguajes de programación modernos.

En esta sección, exploraremos cómo podemos crear clases, objetos y revisaremos en detalles sus atributos, propiedades y métodos.

&nbsp;

# Clases
Imaginemos que tenemos una tienda de automóviles y queremos desarrollar un software para conocer los autos que tenemos, sus características y, bueno, porque tenemos tiempo de sobra (casi).

La programación orientada a objetos (de aquí en adelante **OOP** por sus siglas en inglés), nos permite representar conceptos como "auto" en nuestro código tal como si fuera un objeto de la vida real.

¿Cómo así? Bueno, un auto tiene características como su precio de venta, su color, kilometraje, así como también puede ejecutar acciones como ser conducido, cargar gasolina, etc...

En la OOP, podemos definir un objeto que represente a un auto, darle esas características (**atributos**), y atribuirle ciertas acciones (**métodos**).

Vamos con un ejemplo:

```Python
# Creamos una clase llamada Auto
class Auto:

    # Este auto tiene ciertos atributos
    color = 'white'
    model = 'Chevrolet Cruze'
    mileage = 111000
    price = 4000000

    # Y puede ejecutar ciertos métodos
    def get_painted(color):
        print(f'Painting {color}')
    
    def apply_discount(percentage):
        print(f'Applying {percentage}% discount')
```

Primera pregunta: Si hablamos tanto de "objetos", ¿por qué escribimos una "*clase*"?

Digamos que hay una sutil diferencia entre un objeto y una clase.

Podemos tomarlo como que la clase es un *concepto*, en este caso, el *concepto* de lo que es un auto.

Por otra parte, un objeto es algo concreto, una ***instancia*** de una clase; en este caso, sería el auto real, no el concepto.

Entonces, hasta ahora no hemos creado ningún objeto, sino que le "enseñamos" al computador el *concepto* (muy simplificado) de un auto.

Digamos que, sin más rodeos, queremos crear un objeto; es decir, queremos crear un auto:
```Python
# Habiendo creado la clase Auto, generamos
# una instancia de esta clase:

my_car = Auto()
```
Antes dijimos que los objetos tienen atributos y métodos. Podemos acceder a ellos de la siguiente manera:
```Python
my_car.color
# 'white'

my_car.price
# 4000000

my_car.get_painted('black')
# 'Painting black'
```

También podemos modificar los atributos de nuestro objeto de la siguiente manera:
```Python
# Habiendo creado la clase Auto, generamos
# una instancia de esta clase:

my_car = Auto()
```
Los objetos tienen atributos y métodos. Podemos acceder a ellos de la siguiente manera:
```Python
my_car.color = 'red'

my_car.color
# 'red'
```

Pero pronto nos daremos cuenta de las limitaciones de nuestra clase.

¿Qué pasa si queremos crear varios autos?
Pues, ¡todos serán iguales!

```Python
car_a = Auto()

car_b = Auto()

car_c = Auto()

print(car_a.color, car_b.color, car_c.color)

# 'white' 'white' 'white'
```

Si queremos que nuestras clases sean versátiles, deberemos hacer algo mejor que esto.

&nbsp;

# Constructores
Los **constructores** o **funciones constructoras** son aquellas que manejan la creación o *construcción* de las instancias de una clase (recordemos que las instancias de una clase son objetos).

Revisitemos la clase `Auto`:
```Python
class Auto:
    color = 'white'
    model = 'Chevrolet Cruze'
    mileage = 111000
    price = 4000000

    
    def get_painted(color):
        print(f'Painting {color}')
    
    def apply_discount(percentage):
        print(f'Applying {percentage}% discount')
```
Si nos fijamos, las variables o atributos de la clase son *variables de la clase* (obvio, ¿o no?). El problema está en que estas variables serán iguales para todas las instancias de la clase.

Podemos mejorarlo escribiendo una *función constructora* `__init__()`:
```Python
class Auto:
    def __init__(self, color, model, mileage, price):
        self.color = color
        self.model = model
        self.mileage = mileage
        self.price = price

    
    def get_painted(color):
        print(f'Painting {color}')
    
    def apply_discount(percentage):
        print(f'Applying {percentage}% discount')
```
¿Qué significa lo anterior?

`__init__` es una función especial, muchas veces apodada "***dunder***" (*dunder* == "*double underscores*").

Dicha función se activa al momento de crear cada objeto.

La siguiente pregunta es: ¿Qué es ese `self` metido ahí?

Bueno, resulta que el primer argumento que se le pasa a las funciones constructoras es una variable que ***represente al objeto siendo creado***.

Por ejemplo, si creamos el auto `my_car`, al momento de crearlo `self == my_car`.

Cuando creemos `car_a`, `self == car_a` y así.

Siempre se refiere a *ese objeto en concreto*.

Es una cosa de perspectiva.

Luego, vemos que estamos asignando valores:
```Python
def __init__(self, color, model, mileage, price):
    self.color = color
    self.model = model
    self.mileage = mileage
    self.price = price
```
Esto puede verse como que le asignamos, al objeto que está siendo creado, las variables `color`, `model`, `mileage` y `price`.

De esta forma, sólo ese auto tendrá esos valores, mientras que otro auto tendrá, bueno, otros valores.

Finalmente (por fin), queda la duda: ¿de dónde saca `__init__` esos parámetros?

Nosotros se los entregamos al crear los objetos.

Funciona así:
```Python
my_car = Auto('red', 'Chevrolet Camaro', 0, 9999999)

my_car.color
# red

my_car.price
# 9999999
```
**Nota:** No necesitamos pasarle un argumento para `self`; Python lo agrega solo.

&nbsp;

# Variables privadas
Las clases y, por consecuencia, los objetos, nos ofrecen una agradable interfaz donde no necesitamos saber cómo funcionan, sino solo qué es lo que retornan.

Pero hay momentos en donde querremos que ciertos atributos o métodos no sean accesibles desde afuera, esto es, que no sean accesibles desde otras partes del código.

Pero, ¿cómo logramos lo anterior?

Lamentablemente (o por suerte), Python no provee un mecanismo para evitar el acceso a todas las las variables de un objeto.

Sin embargo, existe la convención de crear **variables privadas**, donde nombraremos las variables que queremos restringir de una manera ligeramente diferente: anteponiendo un guión bajo (`_`).
Por ejemplo, deberemos saber que **no debemos** acceder a miembros (aka variables) de un objeto que empiecen con `_`:

```Python
class Auto:

    # Variable privada
    _previous_owner = 'Ada Lovelace'

    def __init__(self, color, model, mileage, price):
        self.color = color
        self.model = model
        self.mileage = mileage
        self.price = price

    
    def get_painted(color):
        print(f'Painting {color}')
    
    def apply_discount(percentage):
        print(f'Applying {percentage}% discount')
```
Aquí **podemos, pero no debemos** acceder a la variable `_previous_owner`.

&nbsp;

# Principios de OOP, Parte 1
Preguntas clásicas en los cursos de OOP, que es bueno conocer pero, principalmente, es importante solo entender estos principios.

Hasta ahora hemos observado dos de estos cuatro principios:
- **Abstracción**
- **Encapsulamiento**
- Herencia
- Polimorfismo

## Abstracción
La **abstracción** tiene que ver con que un objeto bien representa un *concepto*; no nos interesa cómo funciona o qué tiene dentro, pero sí nos importa lo que puede ayudarnos a hacer.

Con la abstracción, un objeto esconde esos detalles técnicos y nos permite realizar acciones sin preocuparnos del cómo lo hace.

Un ejemplo de la vida: Cuando queremos sacar dinero desde un cajero automático, no sabemos cómo nos lo entrega, pero sí conocemos lo suficiente como para realizar el proceso.

El cajero automático ***esconde su implementación interna***.

## Encapsulamiento
El **encapsulamiento** significa que "*lo que pasa en los objetos, se queda en los objetos*". Básicamente, cuando interactuemos con un objeto, sabremos que lo único que puede ser modificado es el objeto mismo. En otras palabras, si arruinamos algo dentro del objeto no habremos arruinado nada fuera de este; el resto del código estará seguro.

Cada objeto es una *cápsula* que encierra su propio mundo, lógica y reglas de funcionamiento.

&nbsp;

# Herencia
Todo súper hasta ahora, pero nuestro concepto de auto no contempla todos los detalles que nos gustaría.

Sería ideal poder diferenciar entre diferentes tipos de auto; por ejemplo, tener camionetas, SUVs, sedans, etc...

¿Cómo podemos lograr esto?

Una opción es agregar la variable `car_type` en la clase `Auto`, pero no queremos acceder a cada objeto para saber de qué tipo es.

Otra opción, **nuestra opción**, es crear nuevas clases que hereden las características de `Auto`.

¿Qué significa que hereden? Tal como funciona en la vida real con padres e hijas/os, un descendiente puede obtener características de sus progenitores.

Veamos cómo funciona esto en Python:
```Python
# Creamos una nueva clase "Camioneta"
class Camioneta:
    
```


&nbsp;

# Principios de OOP, Parte 2
## Polimorfismo

## Herencia