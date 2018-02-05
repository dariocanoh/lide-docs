.. /////// 2017/11/12 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/modules/lide.class.rst
.. //  lide.class reference
.. //   (c) 2017 Hernan Dario Cano | Lide License

lide.class
==========

  This function allow us to make a class using another Lua class as 
  base or make clear class.

  .. code-block:: lua
   
   --- load only lide core and assign class variable
   local class = require 'lide.core.init' . class 

   newClass = class 'newClass' : subclassof ( baseClass )
     
   function newClass:newClass ( fields )
   	... -- do constructor
   end

OOP Lua model resources:

- `See Class reference <../oop-intro.html>`_.
- `See Encapsulation and modifiers <../access_modifiers.html>`_.


Lua Class Methods
*****************

These methods allow you to interact directly with classes and make 
useful changes to constructors and methods of classes and instances.

----------------------------------------------------------------------


Class:enum
^^^^^^^^^^

``enum`` method allows you to add classes constant values, **returns a 
read-only table** that contains the values provided for the enum.

======== =============================================================
 table_   Class : enum ( table_ tblEnum )
======== =============================================================

.. code-block:: lua

	ClassConstants = Class:enum {
		CONST_1 = 100,
		CONST_2 = 200,
	}

	print( Class.CONST_1 )          -->> 100
	print( ClassConstants.CONST_1 ) -->> 100

----------------------------------------------------------------------



.. include:: ../directives.rst