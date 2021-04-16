# Introducción a UML

## ¿Qué es UML?

- UML ó Unifield Modelling Language, Lenguaje de Modelado Uificado.

- **UML:** Es un lenguaje que nos provee la anotación, sintaxis y la semántica para modelar este tipo de problemas.

---

## Conceptos Generales de UML

- **Modelar:** Consiste en observar una realidad y a partir de esta, abstraer conceptos para representarlas en un modelo de nuestra elección.
 ```
    Observar | Abstraer | Representar
 ```

---

## Sintaxis básica de Diagrama de clases

Modelar atributos básicos con tipos de datos primitivos y comprender la diferencia entre una clase y objetos. 

Un diagrama de clases tiene clases y asociaciones. 
  
**Clase:** Representa un conjunto de objetos que comparten las mismas carcteristicas y compartimientos.

En UML para representar una clase utilizamos un rectángulo que está dividido en compartimientos.

> `1° compartimiento:` "**Nombre**" (siempre en mayusculas).

En UML representamos estos objetos que podemos instanciar a partir de la clase con rectángulos con esquinas redondeadas

> `1° compartimiento:` "**Nombramos a que clase partenece**" (todo tiene que ir subrayado).

**Atributos:** Los atributos de una clase representan la característica o propiedades que tendrán los objetos de la misma (esto nos permite modelar con mayor precisión la abstracción).

Los atibutos privados se representan (`-`) y los atributos publicos (`+`).

> `2° compartimiento:` "**Se escribiran los atributos**".

**Enumeración:** Son tipos de datos que el usuario define (Su rango de valores son un conjunto de constantes, cada una con nombre propio).

En UML las enumeraciones se representan en su propio rectángulo y arriba del nombre ponemos un estereotipo "**enumeration**" y su contenido son los nombres de cada una de las constantes.

**Métodos:** Son operaciones que están asociadas con la clase y que cada objeto de la clase podrá realizar.

Los métodos en UML van en nuestro tercer compartimiento del diagrama y al igual que los atributos, tendrán una visibilidad, un tipo de retorno que ahora puede no existir para los métodos que no van a devolver un valor y un nombre.

**Encapsulamiento:** Los objetos ocultan sus atributos y solo se manejan através de los métodos.

---

## Sintaxis Básicas de Asociaciones 

Las asociaciones representan las relaciones entre las diferentes clases. 

En UML una **asociación** se representa con una linea.

```
Un rol define como participa cada objeto en la relación, pero no el número de elementos.
```

La negabilidad es bidireccional, ya que la asociación no tiene puntas que indique lo contrario.

### **Herencia Parte 1**

La **herencia** es un mecanismo de reutilización fundamental en los sistemas orientados a objetos. Entender su sintaxis y sus implicaciones al modelar un problema.

Entonces **¿Que son?** Las relaciones de herencia también conocidas como de especialización, son un mecanismo por el cual una clase incorpora la estructura y comportamiento de otra clase más general a ello. A esta clase más general la llamaremos `superclase`. Mientas que la clase que incorpora la estructura y comportamiento de la `superclase` la llamaremos la `subclase`.

En UML para representar que una clase hereda de otra usamos una linea cuya terminación es un "**triángulo vacio**", la punta del triángulo está en el lado de la **superclase** y debe apuntar a está.

En las relaciones de herencia tenemos que: 

1. Las *subclases* heredan o tienen los atributos, asociaciones y o métodos de la *superclase*, es decir, las instacias de las *superclases* tienen además de los propios, las propiedades de la *superclase*.

```
Especializan | Superclase | Especializaciones |Heredan  | Subclases.
```

> Va una imagen.

2. Las *subclases* pueden tener nuevos atributos, asociaciones ó métodos, es decir, la *superclase* al agregar propiedades especializa a la *superclase*.

3. Las *subclases* pueden redefinir o implementar en la *subclase* métodos o atributos de la *superclase*.

### **Herencia Parte 2**

El proposito principal de una **clase abstracta** es ayudar a organizar una jerarquia de conceptos. Las *superclases* tienen entonces un nivel de abstracción mayor, allí podemos definir atributos y métodos que serán heredados por todas las *subclases*. También podemos declarar métodos, pero debemos indicar que quienes deben definir su implementación son las  *subclases*. Estos son los **métodos abstractos**.

Cuando implementamos un UML una clase abtracta, su nombre se escribe en ítalica, respetando las demás convenciones de nombramiento.

> Va una imagen.

```
Una clase abstracta no puede ser instanciada ya que tiene métodos no implementados y necesita, de sus subclases para ser totalmente declarada. 
```

*¿Cómo podemos entonces declarar la visibilidad de los atributos sin comprometer el encapsulamiento?* Recuerda que si los declaramos como públicos todos podrán accederlos; y si son privados, sus *subclases* no tendrían acceso a ellos.

En UML existe un tercer tipo de visibilidad protegida. Los atributos protegidos no se indican con un símbolo de menos o con un símbolo de más, sino con un numeral.

```
La visibilidad protegida, marcada con un (#), permite que sus subclases puedan acceder a los atributos de la superclase sin comprometer el encapsulamiento. 
```

Como mencionamos anteriormente, las *clases abstractas* pueden determinar que sus *subclases* deben declarar e implementar ciertos métodos de los que ellos solo proveen el nombre, tipo y los parametros; esto es a lo que llamamos **método abstracto**. 

Ahora, existe un caso particular algo particular de las *clases abstractas* del que debemos hablar, las **interfaces**.

Las *interfaces* son clases que no proveen implementación de ninguno de sus métodos. Esto es, todos sus métodos son abstractos. Adicionalmente, sus atributos no son protegidos, si no publicos. Y mientras las *clases abtractas* nos permite especializar y clasificar los elementos de nuestro modelo, las interfaces están más orientadas a proveer un contenido funcional con el que todas las clases que la implementan, si, que la implementan, no que la especializan, deben comprometerse.

Esta es la diferencia de cuando representamos *clases abstractas* utilizando el mecanismo de *herencia*. En este caso, a diferencia de la *herencia tradicional*, no podemos crear instancias de la *superclase* y solo instancias de las *superclases*.

Examinemos ahora el **polimorfismo**.

Una de las concecuencias más interesantes en las relaciones de *herencia* cuando vamos a programar en un lenguaje orientado a objetos.

> Va una imagen.

```
Primero que todo, el polimorfismo es la propiedad que tienen todos los objetos en una relación de herencia, para poderse instanciar como objetos de su misma clase o superclase.
```

### **Otras Asociaciones**

Las *asociaciones compuestas* o *composite*, por su nombre en inglés. 

Las asociaciones de tipo **compuesto** representan relaciones de tipo agregación y una agregación representa una *asociación* entre dos clases en las que una es un todo, es decir *las partes de un todo*. 

*¿Como representamos en UML una asociación compuesta?*

> Va una imagen.

La restrinción de cardinalidad del todo es que sea 1, el otro extremo puede ser asignado con cualquier opción de cardinalidad.

Está es la característica principal de las asociaciones de agregación de tipo *compuesto* en la que la existencia de las instancias de una clase, dependerán  de la existencia de las instancias del todo, y en las que solo pueden haber un único todo.

Debido a la naturaleza de las asociaciones, hay ciertas restrinciones que debemos cumplir, la mas importante es que del lado de la asociación que representa la clase del todo, la cardinalidad debe ser 1, mientras que del lado de las partes puede ser cualquiera de las que hemos visto. Y sus convenciones de nombramiento para las asociaciones de tipo *compuesto* para los objetos.

**Implicaciones de una asociación compuesta**

1. Todos los objetos instancias de la clase que tiene el rol de parte de, están ligadas al lado.

### **Asociaciones 2**

Ahora hablaremos de las **asociaciones de agregación** de tipo compartidas, *share* en inglés.

Las asociaciones de tipo compartido representan relaciones de tipo de *agregación*. Una *agregación* representa una asociación entre dos clases en las que es un todo y la otra es una parte de dicho todo; en otras palabras, las partes de un todo. Las *asociaciones compartidas* según la especificación de UML 2.5 tiene menos restricciones que las compuestas.

Cómo representa una asociación compartida en UML, Usamos una línea, pero en el extremo que corresponde a la clase que hace las veces del todo.

> Va una imagen.

```
La dependencia, al no ser una asiciación, solo tiene una dirección que va desde el cliente hacia el proveedor.
```

Al igual que las *asociaciones compuestas*, es una asociación compartida las partes pueden tener cualquier cardinalidad, en este caso, será muchas. 

> Va una imagen.

Vale la pena mencionar un tipo muy especial de relaciones entre las clases, las *dependecias*.

Las *dependencias* modelan la relación la relación entre dos clases, una de las cuales necesita de otra para su implementación, ya que sea a *nivel semántico* o a *nivel estructural*. Las relaciones de dependencia también de le conoce como **"relaciones de cliente - provedor"**, ya que hay una clase que posee los elementos, el *proveedor*, a otra para su implementación, el *cliente*.
# Introduccion-a-UML
