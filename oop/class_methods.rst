Class Methods
=============

These methods allow you to interact directly with classes and make useful changes to constructors and 
methods of classes and instances.


Class:enum
**********

===========  =======================================================================================
 table_       Class : enum ( table_ tblEnum )
===========  =======================================================================================

``enum`` method allows you to add classes constant values, **returns a read-only table** that
It contains the values provided for the enum.


.. code-block:: lua

	ClassConstants = Class:enum {
		CONST_1 = 100,
		CONST_2 = 200,
	}

	print( Class.CONST_1 )          -->> 100
	print( ClassConstants.CONST_1 ) -->> 100


.. include:: ../directives.rst