.. /////// 2015/01/08 - Dario Cano [thdkano@gmail.com]
.. // docs/classes/Exception.rst
.. //  Class Exception reference
.. //   (c) 2015 Dario Cano | lide license

.. _ClassException:

Exception
=========
.. note::

  Exception is derived from :ref:`Object class<ClassObject>`.

An Exception is a structure holding information about an Exception passed to a callback or member function. 
Exception is used to be a multipurpose Exception object, and is an abstract base class for other Exception classes.

----------------------------------------------------------------------------------------------------


Constructor
***********

Exception class has a single constructor:


.. code-block:: c++

 object Exception:new ( string sExceptionName, object oExceptionSender, function fDefExceptionHandler )


Arguments
^^^^^^^^^

These arguments are received by class constructor.

============  ======================================================================================
  Argument     Description
============  ======================================================================================
 sEvtName      The Exception name
 oEvtSender    The object associated to the Exception (usually is a derived of "Widget_")
 fEvtHandler   The Exception handler function (that is called when you call `Exception:call`).
============  ======================================================================================

----------------------------------------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=================  =================================================================================
  Class Method       Description
=================  =================================================================================
 Object:getID_	    Returns Exception's identifier.
 Object:setID_	    Sets the Exception identifier.
 Object:getName_    Returns Exception's name.
 Object:setName_    Sets the Exception name.
=================  =================================================================================

----------------------------------------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


Exception:getSender
^^^^^^^^^^^^^^^
   
   Gets the object associated to the Exception.

=========  =========================================================================================
 object_    Exception:getSender()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Exception:setSender
^^^^^^^^^^^^^^^
	
   Sets the object associated to the Exception.

=======  ============================================================================================
 bool_ 	  Exception:setSender ( object oEvtSender )
=======  ============================================================================================

----------------------------------------------------------------------------------------------------


Exception:getHandler
^^^^^^^^^^^^^^^^^
   
   Returns the Exception handler function (that is called when you call `Exception:call`).

===========  =======================================================================================
 function_    Exception:getHandler()
===========  =======================================================================================

----------------------------------------------------------------------------------------------------


Exception:setHandler
^^^^^^^^^^^^^^^^
  
   Sets the Exception handler function.

=======  ===========================================================================================
 bool_    Exception:setSender ( object oEvtSender )
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


Exception:call
^^^^^^^^^^
  
   Calls the Exception handler and pass it all the args.

    *Returns one value: Returns first value what Exception handler sents.*

=====  =============================================================================================
 ...    Exception:call ( ... )
=====  =============================================================================================

-----------------------------------------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst