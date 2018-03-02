Encapsulation and access modifiers
==================================

Encapsulation is one of the key features in object-oriented programming.
In Lide we will have at our disposal the three basic modifiers: ``private``, ``protected``
and ``public``. We can access these modifiers only from within the class constructor.

Surely those who are familiar with any programming language you will be
known these modifiers, for those who do not, it is a good opportunity to have a first shot
Contact with fundamental concepts in object-oriented programming.

public Modifier
***************

This switch is the most permissive of the three, since it indicates that the method, or property, is accessible from any other part of our application.
This is the default modifier applied if not specify otherwise.

private Modifier
****************

This switch sets the most restrictive level, since the properties or methods that declare
as private will only be accessible from within the class.

protected Modifier
******************

hese modifiers do not change the form of access or behavior, only control
from where you can use the class members:

**public:** from anywhere.
**private:** from the methods of the class.
**protected:** from the methods of the class and from the methods of the derived classes.

A code explanation of how works Lide encapsulation:

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

In this way we will have a new class called "Window" with different attributes that are accessible
from different places, for example:

If we create an instance of this class will be possible for us to access the field "OnShow" that
It corresponds to an object in the "Event" class from the instance itself, ie outside the class,
Here's an example:

.. code-block:: lua 

	form1 = Window:new {
	   Flags = WIN_STYLE_DEFALUT,
	   PosX  = 10, PosY = 30,
	   Width = 300, Height = 500,
	}
	print( form1 .onClick )         ---> prints [event: onClick]
	print( form1 .Flags )           ---> prints nil

In this example we can see that when trying to access the public field "onClick" from outside the
class system gives us the required value, but if we try to do the same with a value
Private as "Flags" or protected we will not have the same result and can not access the value.

The correct way to do this is by defining methods that allow us to work with these values and
for this we have the famous getters / setters.

In the following example we will define a method that allows us to access the field "Flags" class:

.. code-block:: lua 

	function Window:getFlags()
	   return self.Flags
	end
	...
  	print( form1 .Flags )           ---> prints nil
  	print( form1:getFlags() )        --> prints WIN_STYLE_DEFALUT
	...

 
Being a private field we can only access this by calling the Window :: getFlags method from a
direct instance of the class "Window" itself is that if we try to access this value from
a subclass of "Window" the result will be zero.

If you really want to share a field between a class and its subclasses you must use the modifier
"Protected". So then the value will be accessible from within the class and its subclasses, this type of
we modifier would be useful for example for fields that have to do with the size and position
since the window can be values that are needed in other subclasses of "Window" as a "Dialog"

.. code-block:: lua 

	...
	 class 'Dialog' : subclassof 'Window'
	-- definimos el método que obtendrá el valor para la clase:
	function Dialog:getWidth()
	   return self.Width  -- funciona. Width es protected.
	end
	...

This way when we create an instance of the "Dialog" class we will be able to access the field "Width" as defined in the superclass using the "getWidth" method.

.. code-block:: lua 

	myDLG = Dialog:new {
	   Flags = WIN_STYLE_DEFALUT,
	   PosX  = 10, PosY = 30,
	   Width = 300, Height = 500,
	}

	print( myDLG .onClick )         ---> prints [event: onClick]
	print( myDLG :getWidth() )      ---> prints 300

In this way we can control access to different areas of our classes, the idea is
make a correct abstraction and that each of the instances work only with the values that are useful for themselves.