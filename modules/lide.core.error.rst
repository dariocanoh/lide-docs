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
 nil_ 	  lide.error.finally ( function_ finally_code )
======  ==============================================================


.. // Required values for html docs visualization
.. include:: ../directives.rst