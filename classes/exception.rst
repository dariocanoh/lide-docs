.. /////// 2015/01/08 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/classes/Exception.rst
.. //  Class Exception reference
.. //   (c) 2015 Hernan Dario Cano | Lide Framework License

.. _ClassException:

Exception
=========
.. note::

  Exception is derived from :ref:`Object class<ClassObject>`.

All built-in, non-system-exiting exceptions are derived from this class. All user-defined exceptions 
should also be derived from this class.

----------------------------------------------------------------------------------------------------

Constructor
***********

Exception class has a single constructor:


.. code-block:: c++

 object Exception:new ( string sExceptionName, string sDefaultErrMsg )


Arguments
^^^^^^^^^

These arguments are received by class constructor.

================  ==================================================================================
  Argument         Description
================  ==================================================================================
 sExceptionName    The Exception name
 sDefaultErrMsg    The object associated to the Exception (usually is a derived of 'Widget_')
================  ==================================================================================

----------------------------------------------------------------------------------------------------

Inherited Methods
*****************

These methods are inherited from its super classes:

=================  =================================================================================
  Class Method       Description
=================  =================================================================================
 Object:getName_    Returns Exception's name.
 Object:setName_    Sets the Exception name.
=================  =================================================================================

----------------------------------------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


Exception:isa
^^^^^^^^^^^^^
   
   It helpss to verify if the expression is of the determined type

==========  =========================================================================================
 bool_       Exception:isa( object_ Exception )
==========  =========================================================================================

-----------------------------------------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst