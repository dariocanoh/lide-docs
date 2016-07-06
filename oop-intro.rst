Class reference
===============


A tutorial mode, this paper will try to explain what OOP in Lide programming and adaptations made in 
the base language (Lua) so that the programmer can design and implement their own classes or even
modify aspects of Lide framework.

Within the world of LUA are different implementations/adaptations of OOP, some are shaped and other 
projects are simple scripts that help us interact with classes, subclasses, methods and properties 
within the programming language.

For various reasons we decided to take a small but highly customizable and scalable library that 
suits our needs as a project, such implementation was called `yaci.lua <http://lua-users.org/wiki/YetAnotherClassImplementation>`_ 
(for `Julien Patte <https://github.com/jpatte>`_) we include it within the core and made some minor 
modifications to be adequate to what we wanted.


Making a class
**************

Basically there are two ways to define a new class:

Calling th function ``newclass()`` or using the method ``BaseObject:subclass()``

When you are creating a class must specify a name for it, this is not absolutely necessary, but can 
be helpful at the time of debug their applications. **If you do not specify the class name will be
called "Unnamed".**

When you use ``Object:subclass()``, the new class will be directly a subclass of :ref:`Object <ClassObject>` 
on the other hand ``newClass()`` accepts a second argument, which will be another superclass for your 
object if you do not specify a superclass, the :ref:`Object class <ClassObject>` will be chosen.

.. note::

  This means that all classes are subclasses of :ref:`Object<ClassObject>`.


An example can illustrate better:

.. code-block:: lua

 -- 'Human' is a subclass of 'BaseObject'
 Human = newclass("Human")
 -- 'Engineer' is a subclass of 'Human'
 Engineer = newclass("Engineer", Human)
 -- 'Student' is another subclass of 'Human'
 Student = Human:subclass("Student")

Defining our class
******************

Constructor
+++++++++++

Naturally our classes can define a constructor, or not ...
How to define our builders is as follows:

.. code-block:: lua

  function Human:Human(name, year)
       self.name = name
       self.year   = year
  end

  function Engineer:Engineer(name, year, title)
      self.super:init(name, year)   --> Note that this calls the superclass constructor
      self.title = title
  end


.. important::

  Subclasses can call the constructor of its superclasses through the field super ``self.super:init()``.
  Note that ``Object:init()`` there however, it is recommended never to use it.

Methods
+++++++

Methods can be defined in a very simple way:

.. code-block:: lua 

  function Human:Greet()
      print(“Hello World”)
  end
  function Engineer:Read( book )
      print("Reading: ”..book)
  end

Lua events (meta-methods)
++++++++++++++++++++++++++


Do not confuse these events with the *class Event* These events correspond to interactions between
objects in the programming language, some of these may be: ``__tostring``, ``__add``, ``__eq``.

For more information on methods and meta-meta-tables in Lua see the language reference.

Usted también puede definir eventos para las instancias de la clase, exactamente de la misma manera que define los métodos:

.. code-block:: lua
  
  function Human:__tostring ()
      return “a Human called: ” .. self.nombre .. “, have “ .. self.edad .. “ years old.”
  end

  function Engineer:__tostring()
      return “A Engineer of “.. self.titulo .. “ called: ” .. self.nombre .. “, have “ .. self.edad .. “ years old.”
  end

Any event can be used, except and ``__newindex`` ``__index`` which are necessary for the operation 
of the library.

You can use this feature to define operators as ``__add``, ``__eq``, etc. ``__tostring`` is a really
useful event class :ref:`Object <ClassObject>` implements a standard version it simply returns "xxx" 
where 'xxx' is the name of the class of that instance.

Instantiation
+++++++++++++


Every class has the ``new()`` method, used for instantiation. All the arguments we pass to this 
method are passed to the constructor:

.. code-block:: lua

  Anthony = Human:new (“Anthony”, 33)
  Camila  = Engineer:new (“Camila”, 21, “Electrónica”)

The result is the same as if you "called" classes directly:

.. code-block:: lua

  Julieth = Human (“Julieth”, 13)
  Jefferson = Engineer (“Jefferson”, 23, “Sistemas”)


Classes methods
+++++++++++++++

As ``subclass()`` and ``new()``, classes have some other methods:

* ``inherits()`` It can be used to check if a class inherits from another class:
  For example: ``Ingeniero:inherits(Humano)`` returns ``true``, and ``Estudiante:inherits(Ingeniero)`` returns ``false``. (Generally used for internal purposes)

* ``name()`` Returns the name of the class (you specified when you created it).

* ``super()`` Returns the superclass.

* ``made()`` It is used to check if an instance implements this class or not.
  For example, ``Human:made(Anthony)`` returns ``true`` While ``Student:made(Jefferson)`` returns ``false``.

* ``virtual()`` It is used to explicitly declare abstract and virtual methods, see below.

* ``cast()`` & ``trycast()`` they are used for casting. See below for details.


Running
*******

Intance's methods
+++++++++++++++++

All instances allow access to variables defined in the constructor of your class (and its superclasses). 
They also have a ``class()`` method that returns the class, and ``super`` field that is used to access 
the superclass if you overwrote the method, see:

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

Superclass members are created (and initialized) when the ``self.super:init()`` is called. You generally 
must call this method at the beginning of the constructor to initialize. Note that b is an instance 
of ``B``, ``b.super`` is simply an instance of ``A`` (then beware, here ``super`` is dynamic, not static).


Static variables
++++++++++++++++

Every time you define a new method for a class, it is recorded in a table ``static``; in this way we 
will not mix the methods of classes with class services. This table is accessible via the ``static`` 
field. This generally allows access to static variables in classes, for example:


.. code-block:: lua

  A = newclass("A")
  function A:init(a) self.a = a end
  A.test = 5   -- a static variable in A

  a = A(3)
  prints(a.a)           -- prints 3
  prints(a.test)        -- prints 5
  prints(A.test)        -- prints nil (!)
  prints(A.static.test) -- prints 5


Virtual Methods
+++++++++++++++

The class methods are not virtual by default, which means implicitly that they are not overwritten 
by potential implementations of subclasses. To declare a method as virtual you have to declare explicitly 
using the ``virtual()`` in its class. The call to ``virtual()`` should be written out of any method, 
and before the method definition:

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

With this it is also possible to declare some methods as abstract (b.p. purely virtual methods); you 
just call ``A:virtual()`` with the method name without defining it.

An error will occur if you try to call without defining it before in the hierarchy.

Example here:

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


Private attributes
++++++++++++++++++

By default, subclasses inherit all methods and all the attributes defined by their (s) type (s) father. 
This can lead to some confusion when defining attributes that share the same name at different levels 
in the hierarchy:

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

You can define private attributes in a class depending on the order in which these attributes are initialized.

Note that "private" is not the best term to describe it here (because this is not a real protection 
mechanism); I prefer to speak of attribute "shared" and "shared" between classes and subclasses.

You will also notice that this distinction is made by the same subclass (and not by the superclass),
which can decide (in its constructor) which attributes of the superclass can be possibly inherited from 
the superclass or overwritten privately.

By law, you almost always define the attributes of the class before calling the constructor of its superclass.

Let's see this example with a small change in ``B:init()``:

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


As you can see the different behaviors of the attributes ``X`` and ``Y`` come in the order of 
initialization in the constructor.

The first class that defines an attribute will obtain possession of that attribute, even if some 
superclasses declare an attribute with the same name "after" in the initialization process.

I personally suggest initialize all attributes "unshared" the beginning of the constructor, then call 
the superclass constructor, then a Eventually use some of the superclass' methods. On the contrary 
if you want to access an attribute defined by a superclass does not set this value before the 
superclass constructor has done it.


Castings
++++++++

The Castings are very useful if you need access to a (non-virtual) method from a localized higher in
the class hierarchy method. This can be done with the ``cast()`` and ``trycast()`` of all kinds.

Here's a simple example:

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

Try searching for the sub-object or super-object ``x`` corresponding to the ``class C``, Looking up 
and down the hierarchy. Intuitively we will get ``myB.super == A:cast(MYB)`` and ``myb == B:cast(myB.super)``.

Of course this works with more than two levels of inheritance. If the casting fails an error occurs.

``C:trycast(x)`` does exactly the same except that this simply returns ``nil`` when the casting is 
impossible rather than an error occurs.
