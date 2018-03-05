.. /////// 2018/03/02 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/classes/store.rst
.. //  Class Store reference
.. //   (c) 2018 Hernan Dario Cano | GNU GENERAL PUBLIC LICENSE

.. _ClassStore:

Store
====
.. note::

  Store is derived from :ref:`Object class<ClassObject>`.

An Store represents object with a list of objects of class Store_.
 
----------------------------------------------------------------------------------------------------


Constructor
***********

Store class has one constructor:

.. code-block:: lua

 object Store:new { 
 	Key1 = Value1,
 	Key2 = Value2,
 }


----------------------------------------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=================  =================================================================================
  Class Method       Description
=================  =================================================================================
 Object:getName_    Returns Store's name.
 Object:setName_    Sets the Store's name.
=================  =================================================================================

----------------------------------------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


Store:get
^^^^^^^^

   Gets the the value from given key.

=========  =========================================================================================
	*       Store:get { field = value }
=========  =========================================================================================

----------------------------------------------------------------------------------------------------

Store:add
^^^^^^^^
   
   Adds a new value to Store's values list.

===========  =======================================================================================
 nil_         Store:add( * anyData )
===========  =======================================================================================

-----------------------------------------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst