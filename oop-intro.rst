Referencia de clases
===================

A modo de tutorial, en este documento trataré de explicar en qué consiste la programación orientada a objetos en Lide y las adaptaciones que se hicieron en el lenguaje base (Lua) para que el programador pueda diseñar e implementar sus propias clases o incluso modificar aspectos del framework Lide.

Dentro del mundo de LUA encontramos diferentes implementaciones/adaptaciones de programación orientada a objetos, unos son proyectos conformados y otros son simples scripts que nos ayudan a interactuar con clases, subclases, métodos y propiedades dentro del lenguaje de programación.
Por diversos motivos decidimos adoptar una librería pequeña pero altamente customizable y escalable que se adapta a nuestras necesidades como proyecto, dicha implementación fue llamada `yaci.lua <http://lua-users.org/wiki/YetAnotherClassImplementation>`_ (por `Julien Patte <https://github.com/jpatte>`_) la incluimos dentro del core e hicimos algunas modificaciones menores para que se adecuara a lo que nosotros queríamos.

Creación de una clase:
**********************

Básicamente hay dos formas de definir una nueva clase:

Llamando la función ``newclass()`` o usando el método ``BaseObject:subclass()``

Cuando usted está creando una clase debe especificar un nombre para ella, esto no es absolutamente necesario, pero puede ser de mucha ayuda en el momento de debuggear sus aplicaciones. **Si usted no especifica ningún nombre la clase será llamada “Unnamed”.**
Cuando usted use ``Object:subclass()``, la nueva clase será directamente una subclase de :ref:`Object<ClassObject>`, por otro lado ``newclass()`` acepta un segundo argumento, el cual será otra superclase para su objeto, si usted no especifica ninguna superclase, la :ref:`clase Object<ClassObject>` será elegida.

.. note::

  Esto quiere decir que todas las clases son subclases de :ref:`Object<ClassObject>`.


Un ejemplo puede ilustrarlo mejor:

.. code-block:: lua

 -- 'Humano' es una subclase de 'BaseObject'
 Humano = newclass("Humano")
 -- 'Ingeniero' es una subclase de 'Humano'
 Ingeniero = newclass("Ingeniero", Humano)
 -- 'Estudiante' es otra subclase de 'Humano'
 Estudiante = Humano:subclass("Estudiante")

Definición de nuestra clase:
****************************

Constructor
+++++++++++

Naturalmente nuestras clases pueden definir un constructor, o no…
La forma de definir nuestros constructores es la siguiente:

.. code-block:: lua

  function Humano:Humano(nombre, edad)
       self.nombre = nombre
       self.edad   = edad
  end

  function Ingeniero:Ingeniero(nombre, edad, titulo)
      self.super:init(nombre, edad)   --> Nótese que esto llama el constructor de la superclase
      self.titulo = titulo
  end


.. important::

  Las subclases pueden llamar el constructor de sus superclases a través del campo super ``self.super:init()``.

  Nótese que ``Object:init()`` existe sin embargo, se recomienda nunca usarlo.

Métodos
+++++++

Los métodos pueden ser definidos de una manera muy sencilla:

.. code-block:: lua 

  function Humano:Saludar()
      print(“Hola Mundo”)
  end
  function Ingeniero:Leer( libro )
      print(“Leyendo: ”..libro)
  end

Eventos lua (meta-métodos)
++++++++++++++++++++++++++

No confundir éstos eventos con la *clase Event*, éstos eventos corresponden a las interacciones entre los objetos dentro del lenguaje de programación, algunos de éstos pueden ser: ``__tostring``, ``__add``, ``__eq``.
Para más información sobre meta-methods y meta-tables en Lua véase la referencia del lenguaje.

Usted también puede definir eventos para las instancias de la clase, exactamente de la misma manera que define los métodos:

.. code-block:: lua
  
  function Humano:__tostring ()
      return “Un Humano llamado: ” .. self.nombre .. “, que tiene “ .. self.edad .. “ años.”
  end

  function Ingeniero:__tostring()
      return “Un Ingeniero de “.. self.titulo .. “ llamado: ” .. self.nombre .. “, que tiene “ .. self.edad .. “ años.”
  end

Cualquier evento puede ser usado, exceptuando ``__index`` y ``__newindex`` los cuales son necesarios para el funcionamiento de la librería.

Usted puede usar esta característica para definir operadores como: ``__add``, ``__eq``, etc. ``__tostring`` es un evento realmente útil, la clase :ref:`Object<ClassObject>` implementa una versión estándar para ella que simplemente retorna "a xxx" donde 'xxx' es el nombre de la clase de dicha instancia.


Instanciación
+++++++++++++

Toda clase tiene el método ``new()``, usado para la instanciación. Todos los argumentos que pasemos a éste métodos son pasados al constructor:

.. code-block:: lua

  Anthony = Humano:new (“Anthony”, 33)
  Camila  = Ingeniero:new (“Camila”, 21, “Electrónica”)

El resultado es el mismo que si usted “llama” las clases directamente:

.. code-block:: lua

  Julieth = Humano (“Julieth”, 13)
  Jefferson = Ingeniero (“Jefferson”, 23, “Sistemas”)


Métodos de las clases
+++++++++++++++++++++

Así como ``subclass()`` y ``new()``, las clases tienen algunos otros métodos:

* ``inherits()`` Puede ser usado para chequear si una clase hereda de otra clase:
  Por ejemplo: ``Ingeniero:inherits(Humano)`` retorna ``true``, y ``Estudiante:inherits(Ingeniero)`` retorna ``false``. (Generalmente usado para propósitos internos)

* ``name()`` Retorna el nombre de la clase (El que usted especifico cuando la creó).

* ``super()`` Retorna la superclase.

* ``made()`` Es usado para chequear si una instancia implementa ésta clase o no. 
  Por ejemplo, ``Humano:made(Anthony)`` retorna true Mientras que ``Estudiante:made(Jefferson)`` retorna ``false``.

* ``virtual()`` Es usado para declarar métodos abstractos y virtuales explícitamente, ver abajo.

* ``cast()`` & ``trycast()`` son usados para casting. Ver abajo para más detalles.


Ejecución
*********

Métodos de las instancias
+++++++++++++++++++++++++

Todas las instancias permiten accesar a las variables definidas en el constructor de su clase (y de sus superclases). Ellos también tienen un método ``class()`` que retorna la clase, y un campo ``super`` que es usado para acceder a la superclase por si usted sobrescribió el método, veamos:

.. code-block:: lua

  A = newclass("A")
  function A:test() print(self.a) end
  A:virtual("test") -- declare test() as being virtual; see below
  function A:init(a) self.a = a end

  B = newclass("B", A)
  function B:test() print(self.a .. "+" .. self.b) end
  function B:init(b) self.super:init(5) self.b = b end

  b = B:new(3)
  b:test()         -- prints "5+3"
  b.super:test()   -- prints "5"
  print(b.a)       -- prints "5"
  print(b.super.a) -- prints "5"

Los miembros de la superclase son creados (e inicializados) cuando el método ``self.super:init()`` es llamado. Usted generalmente debe llamar este método al principio del constructor para inicializarlo. Nótese que b es una instancia de ``B``, ``b.super`` es simplemente una instancia de ``A`` (entonces tenga cuidado, aquí ``super`` es dinámico, no estático).

Variables estáticas
+++++++++++++++++++

Cada vez que usted define un nuevo método para una clase, éste es registrado en una tabla ``static``; de esta manera nosotros no vamos a mezclar los métodos de las clases con los servicios de las clases. Ésta tabla es accesible mediante el campo ``static``. Esto generalmente permite acceso a variables estáticas en las clases, por ejemplo:

.. code-block:: lua

  A = newclass("A")
  function A:init(a) self.a = a end
  A.test = 5   -- a static variable in A

  a = A(3)
  prints(a.a)           -- prints 3
  prints(a.test)        -- prints 5
  prints(A.test)        -- prints nil (!)
  prints(A.static.test) -- prints 5


Métodos virtuales
+++++++++++++++++

Los métodos de las clases no son virtuales por defecto, lo que quiere decir que ellos no son implícitamente sobre-escritos por potenciales implementaciones de las subclases. Para declarar un método como virtual usted tiene que declararlo explícitamente usando el método ``virtual()`` de su clase. La llamada a ``virtual()`` debe estar escrita fuera de cualquier método, y antes de la definición del método:

.. code-block:: lua

  A = newclass("A")

  function A:whoami()
    return "A"
  end
  A:virtual("whoami") -- whoami() is declared virtual

  function A:test()
    print(self:whoami())
  end

  B = newclass("B", A)

  function B:whoami()
    return "B"
  end
    -- no need to use B:virtual() here
  myB = B()
  myB:test() -- prints "B"

Con esto también es posible declarar algunos métodos como abstractos (p.e. métodos puramente virtuales); usted solo tiene que llamar ``A:virtual()`` con el nombre del método sin definirlo.

Un error ocurrirá si usted intenta llamarlo sin definirlo antes en la jerarquía.

Aquí un ejemplo:

.. code-block:: lua

  A = newclass("A")

  A:virtual("whoami") -- whoami() is an abstract method

  function A:test()
    print(self:whoami())
  end

  B = newclass("B", A)

  function B:whoami() -- define whoami() here
    return "B"
  end

  myB = B()
  myB:test() -- will print "B"

  myA = A()  -- no error here! 
  myA:test() -- but will raise an error here


Atributos privados
++++++++++++++++++

Por defecto, las subclases heredan todos los métodos y todos los atributos definidos por su(s) clase(s) padre. Esto puede llevar a algunas confusiones cuando definimos atributos que comparten el mismo nombre en diferentes niveles en la jerarquía:

.. code-block:: lua

  A = newclass("A")

  function A:init()
    self.x = 42  -- define an attribute here for internal purposes
  end

  function A:doSomething()
    self.x = 0   -- change attribute value
    -- do something here...
  end


  B = A:subclass("B")

  function B:init(x)
    self.super:init()   -- call the superclass's constructor
    self.x = x          -- B defines an 'x' attribute. Problem: 'x' is actually already defined by A!
  end

  function B:doYourJob()
    self.x = 5
    self.doSomething()
    print(self.x)       -- prints "0": 'x' has been modified by A because A defined it first
  end

Es posible definir atributos privados en una clase dependiendo del orden en que esos atributos son inicializados. 
Nótese que “privado” no es el mejor término para definirlo aquí (porque éste no es un mecanismo de protección real); yo preferiría hablar de atributo “compartido” y “no compartido” entre las clases y sus subclases.

Usted también notará que esta distinción está hecha por la misma subclase (y no por la superclase), la cual puede decidir (en su constructor) qué atributos de la superclase pueden ser eventualmente heredados desde la superclase o sobrescritos privadamente. 
Por ley usted casi siempre definirá los atributos de la clase antes de llamar el constructor de su superclase.

Vamos a ver éste ejemplo con un pequeño cambio en ``B:init()``:

.. code-block:: lua

  A = newclass("A")
  function A:init()
    self.x = 42  -- define an attribute here for internal purposes
  end

  function A:doSomething()
    self.x = 0   -- change attribute value
    -- do something here...
  end

  B = A:subclass("B")

  function B:init(x)
    self.x = x          -- B defines a private 'x' attribute
    self.super:init()   -- call the superclass's constructor
  end

  function B:doYourJob()
    self.x = 5
    self.doSomething()
    print(self.x)       -- prints "5": 'x' has not been modified by A
    print(self.super.x) -- prints "0": this is the 'x' attribute that was used by A
  end

Como usted puede ver los diferentes behaviors de los atributos ``x`` y ``y`` vienen en el orden de inicialización en el constructor. 
La primera clase que define un atributo va a obtener la posesión de ese atributo, even si algunas superclases declaran un atributo con el mismo nombre “después” en el proceso de inicialización. 
Yo personalmente sugiero inicializar todos los atributos “no compartidos” al inicio del constructor, luego llamar el constructor de la superclase, then eventually use some of the superclass' methods. Por el contrario si usted quiere acceder a un atributo definido por una superclase no establezca este valor antes de que el constructor de la superclase has done it.


Castings
++++++++

Los Castings son muy útiles si usted necesita acceder a un método (no virtual) desde un método localizado más arriba en la jerarquía de clases. Esto puede hacerse con los métodos ``cast()`` y ``trycast()`` de todas las clases. Aquí un simple ejemplo:

.. code-block:: lua

  A = newclass("A")
  function A:foo()
    print(self.x)         -- prints "nil"! There is no field 'x' at A's level
    selfB = B:cast(self)  -- explicit casting into a B
    print(selfB.x)        -- prints "5"
  end
  B = newclass("B",A)
  function B:init(x) 
      self.x = x
  end

  myB = B(5)
  myB:foo()
  C:cast(x) 

Intenta buscar el sub-objeto o super-objeto en ``x`` correspondiente a la ``clase C``, Buscando arriba y abajo en la jerarquía. Intuitivamente nosotros vamos a obtener ``myB.super == A:cast(myB)`` y ``myB == B:cast(myB.super)``.

Por supuesto que esto funciona con mas de dos niveles de herencia. Si el casting falla ocurrirá un error.

``C:trycast(x)`` hace exactamente lo mismo excepto que ésto simplemente retorna ``nil`` cuando el casting es imposible en vez de ocurrir un error.
