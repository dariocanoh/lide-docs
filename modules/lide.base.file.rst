.. /////// 2017/11/12 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/modules/lide.error.rst
.. //  lide.error reference
.. //   (c) 2017 Hernan Dario Cano | Lide License

.. _lide_file:

lide.file
==========
  
  ``[lide.base] ^1.0``

  This module is loaded with ``lide.base`` it's part of framework into
  the ``lide.file`` module we will find the necessary functions to 
  files handling implemented in Lua.

  .. code-block:: lua
   
   local file = lide.file
   file.copy('C:\\file', 'D:\\file');

----------------------------------------------------------------------


file.remove
^^^^^^^^^^^
   
  Deletes a file in the system.

======  ==============================================================
 nil_    file.remove ( string_ sFilePath )
======  ==============================================================

----------------------------------------------------------------------


file.open
^^^^^^^^^
  
  Open the given filename.

=======  ==============================================================
 File_    file.open ( string_ sFilePath )
=======  ==============================================================

----------------------------------------------------------------------


file.exists
^^^^^^^^^^^
	
  Determine if the given file exists.

==========  ==========================================================
 boolean_ 	file.exists ( string_ sFilePath )
==========  ==========================================================


.. // Required values for html docs visualization
.. include:: ../directives.rst