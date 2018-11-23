.. /////// 2018/02/27 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/classes/item.rst
.. //  Class Item reference
.. //   (c) 2017 Hernan Dario Cano | GNU GENERAL PUBLIC LICENSE

.. _ClassItem:

Item
====

   Item is derived from :ref:`Object class<ClassObject>`.

   ``[lide.base] ^1.0`` ``lide.classes.item 1.0``


An item represents object with numerous values can be accessed with 
getters and setters.
 
----------------------------------------------------------------------


Constructor
***********

Item class has one constructor:

.. code-block:: lua

 object Item:new { 
 	Key1 = Value1,
 	Key2 = Value2,
 }


----------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=================  ===================================================
  Class Method       Description
=================  ===================================================
 Object:getName_    Returns item's name.
 Object:setName_    Sets the item's name.
=================  ===================================================

----------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


Item:get
^^^^^^^^

   Gets the the value from given key.

=========  ===========================================================
	*       Item:get ( string_ sKey )
=========  ===========================================================

----------------------------------------------------------------------


Item:set
^^^^^^^^
   
   Sets the value of the given key.

===========  =========================================================
 nil          Item:set( string_ sKey, * anyData )
===========  =========================================================

----------------------------------------------------------------------


Item:add
^^^^^^^^
   
   Adds a new value to item's values list.

===========  =========================================================
 boolean_      Item:add( string_ sKey, * anyData )
===========  =========================================================

-----------------------------------------------------------------------




.. // Required values for html docs visualization
.. include:: ../directives.rst