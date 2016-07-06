Encapsulación y modificadores de acceso
=======================================

La encapsulación es una de las características fundamentales en la programación orientada a objetos.
En Lide vamos a tener a nuestra disposición los tres modificadores básicos: ``private``, ``protected``
y ``public``. Podemos acceder a éstos modificadores sólo desde dentro del constructor de la clase.

Seguramente aquellos que estén familiarizados con algún lenguaje de programación le resultarán 
conocidos estos modificadores, para aquellos que no, es una buena ocasión para tener una primera toma 
de contacto con conceptos fundamentales dentro de la programación orientada a objetos.

MODIFICADOR PUBLIC
******************

Este modificador es el más permisivo de los tres, puesto que indica que el método, o la propiedad, es accesible desde cualquier otra parte de nuestra aplicación.
Este es el modificador aplicado por defecto en caso de que no especifiquemos lo contrario.

MODIFICADOR PRIVATE
*******************

Este modificador establece el nivel más restrictivo, puesto que las propiedades o métodos que declaremos 
como private solo serán accesibles desde el interior de la clase.

MODIFICADOR PROTECTED
*********************

Este modificador establece un nivel de restricción medio, esto quiere decir que las propiedades o 
métodos declarados como protected sólo serán accesibles desde la clase base o las clases hijas que hereden de la clase base.

 
Estos modificadores no cambian ni la forma de acceso ni el comportamiento, únicamente controlan 
desde dónde se pueden usar los miembros de la clase:

**public:** desde cualquier sitio.
**private:** desde los métodos de la clase.
**protected:** desde los métodos de la clase y desde los métodos de las clases derivadas.

Una explicación con código de cómo funciona la encapsulación en Lide.

.. code-block:: lua

	class 'Window'
	function Window:Window ( fields )
	     private {
	        Flags = fields.Flags
	     }
	     protected {
	        PosX = fields.PosX, PosY = fields.PosY,
	        Width = fields.Width, Height = fields.Height
	     }
	     public {
	        onShow = Event:new ('onShow', self)
	     }
	end

De ésta manera tendremos una nueva clase llamada “Window” con diferentes atributos que son accesibles 
desde lugares diferentes, por ejemplo:

Si creamos una instancia de ésta clase va a ser posible para nosotros acceder al campo “onShow” que 
corresponde a un objeto de la clase “Event” desde la propia instancia, es decir fuera de la clase,
aquí un ejemplo: 

.. code-block:: lua 

	form1 = Window:new {
	   Flags = WIN_STYLE_DEFALUT,
	   PosX  = 10, PosY = 30,
	   Width = 300, Height = 500,
	}
	print( form1 .onClick )         ---> prints [event: onClick]
	print( form1 .Flags )           ---> prints nil

En éste ejemplo podemos notar que al intentar acceder al campo público “onClick” desde fuera de la 
clase el sistema nos devuelve el valor requerido, pero si intentamos hacer lo mismo con un valor 
privado como “Flags” o protegido no vamos a tener el mismo resultado y no se puede acceder al valor.

La manera correcta de hacerlo es definiendo métodos que nos permitan trabajar con estos valores y 
para esto tenemos los famosos getters/setters.

En el siguiente ejemplo vamos a definir un método que nos permita acceder al campo “Flags” de la clase:

.. code-block:: lua 

	function Window:getFlags()
	   return self.Flags
	end
	...
  	print( form1 .Flags )           ---> prints nil
  	print( form1:getFlags() )        --> prints WIN_STYLE_DEFALUT
	...

 
Al ser un campo privado sólo podremos acceder a este llamando al método Window::getFlags desde una 
instancia directa de la propia clase “Window” es decir que si intentamos acceder a éste valor desde 
una subclase de “Window” el resultado será nulo.

Si en realidad deseas compartir un campo entre una clase y sus subclases debes usar el modificador 
“protected“. Así entonces el valor será accesible desde la propia clase y sus subclases, éste tipo de
modificador nos sería útil por ejemplo para los campos que tienen que ver con el tamaño y posición de 
la ventana puesto que pueden ser valores que se necesiten en otras subclases de “Window” como un “Dialog” 
o un formulario especial.

.. code-block:: lua 

	...
	 class 'Dialog' : subclassof 'Window'
	-- definimos el método que obtendrá el valor para la clase:
	function Dialog:getWidth()
	   return self.Width  -- funciona. Width es protected.
	end
	...

De ésta forma cuando creemos una instancia de la clase “Dialog” vamos a poder acceder al campo “Width” definido en la superclase utilizando el método “getWidth”.

.. code-block:: lua 

	myDLG = Dialog:new {
	   Flags = WIN_STYLE_DEFALUT,
	   PosX  = 10, PosY = 30,
	   Width = 300, Height = 500,
	}

	print( myDLG .onClick )         ---> prints [event: onClick]
	print( myDLG :getWidth() )      ---> prints 300

De ésta manera podemos controlar el acceso a los diferentes campos de nuestras clases, la idea es 
hacer una correcta abstracción y que cada uno de las instancias trabaje sólo con los valores que son útiles para sí.