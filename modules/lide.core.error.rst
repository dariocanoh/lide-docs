.. /////// 2017/11/12 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/modules/lide.error.rst
.. //  lide.error reference
.. //   (c) 2017 Hernan Dario Cano | Lide License

.. _lide_error:

lide.error
==========
  
  ``[lide.core] ^0.01``

  This module is loaded with ``lide.core`` it's part of framework into
  the ``lide.error`` module we will find the necessary functions to 
  robust error handling implemented in Lua.

  .. code-block:: lua
   
   local try, catch = lide.error.try, lide.error.catch;

   try { function( )
      ...
   end,

   catch { function( err )
      print(err);
   end 
   }};

----------------------------------------------------------------------


lide.error.try
^^^^^^^^^^^^^^
   
  Within this function we will put the piece of code that could have 
  an error.

======  ==============================================================
 nil_    lide.error.try ( function_ try_code )
======  ==============================================================

----------------------------------------------------------------------


lide.error.catch
^^^^^^^^^^^^^^^^
  
  ``Optional`` Within this function we will put the code that will be 
  executed in case of error.

======  ==============================================================
 nil_    lide.error.catch ( function_ catch_code ( Exception_ exception ) )
======  ==============================================================

----------------------------------------------------------------------

lide.error.finally
^^^^^^^^^^^^^^^^^^
  
  ``Optional`` Here we should put cleaning code

======  ==============================================================
 nil_     lide.error.finally ( function_ finally_code )
======  ==============================================================

----------------------------------------------------------------------

lide.error.is_string
^^^^^^^^^^^^^^^^^^^^
  
  Check if given value is type string

======  ==============================================================
 nil_     lide.error.is_string( value )
======  ==============================================================

----------------------------------------------------------------------

lide.error.is_number
^^^^^^^^^^^^^^^^^^^^
  
  Check if given value is type number

======  ==============================================================
 nil_     lide.error.is_number( value )
======  ==============================================================

----------------------------------------------------------------------

lide.error.is_table
^^^^^^^^^^^^^^^^^^^
  
  Check if given value is type table

======  ==============================================================
 nil_     lide.error.is_table( value )
======  ==============================================================

----------------------------------------------------------------------

lide.error.is_function
^^^^^^^^^^^^^^^^^^^^^^
  
  Check if given value is type function

======  ==============================================================
 nil_     lide.error.is_function( value )
======  ==============================================================

----------------------------------------------------------------------

lide.error.is_boolean
^^^^^^^^^^^^^^^^^^^^^
  
  Check if given value is type boolean

======  ==============================================================
 nil_     lide.error.is_boolean( value )
======  ==============================================================

----------------------------------------------------------------------

lide.error.is_object
^^^^^^^^^^^^^^^^^^^^
  
  Check if given value is type object

======  ==============================================================
 nil_     lide.error.is_object( value )
======  ==============================================================

----------------------------------------------------------------------

lide.error.newException
^^^^^^^^^^^^^^^^^^^^^^^
  
  Create an exception

============  ========================================================
 Exception_     lide.error.newException ( string_ sExceptionName, string_ sDefaultErrMsg )
============  ========================================================

----------------------------------------------------------------------

lide.error.TypeError
^^^^^^^^^^^^^^^^^^^^
  
  Trhow an exception

======  ==============================================================
 nil_     lide.error.newException ( string_ sExceptionName, string_ sErrorMsg )
======  ==============================================================

----------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst