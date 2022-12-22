# Que es la metodología BEM y como se usa.

Si tu propósito al momento de crear Css es ser especifico, claro, legible, fácil de entender y por supuesto implementar una buena práctica al momento de crear estilos, la metodología BEM (Block Element Modifier) te será de gran ayuda para crecer en el ámbito profesional.

El propósito de BEM que en español seria modificador de bloques de elementos, es que tú puedas crear una estructura de codigo más consistente, no duplicar estilos y traer claridad al codigo definiendo y estableciendo mejor jerarquía en tu proyecto. Si quieres saber mas de como surgió esta metodología te recomiendo leer a fondo sobre su historia.

Lo anterior por supuestos nos ayuda a trabajar más de manera ágil y eficiente, tanto solo como en equipo, ya que como he dicho tendremos la oportunidad de crear un codigo totalmente legible hasta para los usuarios introvertidos que den clic derecho y en inspeccionar elemento.

Esta metodología surgiere incluir en la creación de estilos CSS y HTML una serie de reglas para el desarrollo del frontend de manera general, la cual consiste en crear o nombrar clases de elementos independientes haciendo las hojas de estilos más simples y fáciles de entender divididas en bloque, elemento y modificador. Las cuales describiré cada una.

# Bloque: 
Es esa parte independiente en la cual se escrutará nuestro proyecto y donde se verán contenidos todos los elementos de este. es decir, esos contenedores principales que nos ayudaran a dividir las partes de nuestro documento y que son fácilmente identificadas. Ejemplos de esto serian header, footer, contenedor principal, ítems y demás. En realidad, depende de ti y tu forma de estructurar resaltando que los bloque serán los contenedores de los elementos y así mismo deben ser nombrados de forma coherente.

Ejemplo de cómo nombrar bloques:

_.footer_

# Elemento: 

Es (valga la redundancia) el elemento que esta dentro de un bloque. En la metodología BEM no puede utilizarse por si solo si no se especifica a que bloque pertenece. Creando un marco de referencia general podemos resumir que el bloque contiene los elementos y así debe estructurarse el nombramiento de la clase. Estos se nombran con dos underscore después del nombre del bloque.
Ejemplo de cómo nombrar elementos

_.footer__information_

# Modificador:
 Este juega un papel muy importante ya que nos referimos a modificador cuando queremos cambiar la aparicencia especifica de un bloque o un elemento, por ejemplo: si tenemos un menú en el header y estos tienen los mismos nombres de clase para que cada uno tome propiedades iguales, pero hay uno que quieres que sea de otro color y tome otras propiedades como focus, active o hover, pues le agregas un modificador para así de simple modificarlo a tu gusto junto con las propiedades de los demás elementos del menú. para crear un modificador agregamos dos guiones y su nombre.
Ejemplo de como nombrar o hacer llamado a modificadores:

_.footer__information--aboutme_

De esta manera nuestro codigo estará limpio y reusable, además de una cascada impecable que te ahorrara mucho tiempo al momento de crear estilos, estudiarlos o revisarlos.

# Uso de custom properties o propiedades personalizadas (variables) de CSS:

Las propiedades personalizadas (a veces denominadas variables CSS o variables en cascada ) son entidades definidas por los autores de CSS que contienen valores específicos para reutilizar en un documento. Se establecen mediante la notación de propiedad personalizada 
(p. ej., --main-color: black;) y se accede a ellos mediante la var()función (p. ej., color: var(--main-color);).

Los sitios web complejos tienen una gran cantidad de CSS, a menudo con muchos valores repetidos. Por ejemplo, el mismo color puede usarse en cientos de lugares diferentes, lo que requiere una búsqueda global y reemplazo si ese color necesita cambiar. Las propiedades personalizadas permiten que un valor se almacene en un lugar y luego se haga referencia en muchos otros lugares. Un beneficio adicional son los identificadores semánticos. Por ejemplo, --main-text-colores más fácil de entender que #00ff00, especialmente si este mismo color también se usa en otros contextos.

Las propiedades personalizadas están sujetas a la cascada y heredan su valor de su padre.

Uso básico
La declaración de una propiedad personalizada se realiza mediante un nombre de propiedad personalizada que comienza con un guión doble ( --) y un valor de propiedad que puede ser cualquier valor CSS válido. Como cualquier otra propiedad, esto está escrito dentro de un conjunto de reglas, así:

element {
  --main-bg-color: brown;
}

Tenga en cuenta que el selector proporcionado al conjunto de reglas define el alcance en el que se puede usar la propiedad personalizada. Una práctica recomendada común es definir propiedades personalizadas en la :rootpseudoclase, de modo que se pueda aplicar globalmente en su documento HTML:

:root {
  --main-bg-color: brown;
}

Sin embargo, esto no siempre tiene que ser el caso: tal vez tenga una buena razón para limitar el alcance de sus propiedades personalizadas.

Cómo funciona var()
En primer lugar: las variables CSS pueden tener un alcance global o local.

Las variables globales se pueden acceder/usar a través de todo el documento, mientras que las variables locales se pueden usar solo dentro del selector donde se declara.

Para crear una variable con alcance global, declárela dentro del :root selector. El :root selector coincide con el elemento raíz del documento.

Para crear una variable con alcance local, declárela dentro del selector que la va a usar.

El siguiente ejemplo es igual al ejemplo anterior, pero aquí usamos la var()función.

Primero, declaramos dos variables globales (--blue y --white). Luego, usamos la var()función para insertar el valor de las variables más adelante en la hoja de estilo:

Las ventajas de usar var() son:

* hace que el código sea más fácil de leer (más comprensible)
* hace que sea mucho más fácil cambiar los valores de color