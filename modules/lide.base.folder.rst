.. /////// 2018/02/08 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/modules/lide.base.folder.rst
.. //  lide.folder reference
.. //   (c) 2018 Hernan Dario Cano | Lide License

.. _lide_folder:

lide.folder
===========
  
  ``[lide.base] ^1.0``

  This module is loaded with ``lide.base`` it's part of framework into
  the ``lide.folder`` module we will find the necessary functions to 
  manage folders with Lua.

  .. code-block:: lua
   
   local folder = lide.folder
   folder.copy('C:\\folder', 'D:\\folderdest');

----------------------------------------------------------------------

folder.create
^^^^^^^^^^^^^
   
  Create one or more directories specified by the Directory argument.

======  ==============================================================
 nil_    folder.create ( string_ sDirectory or table_ tDirectories )
======  ==============================================================

----------------------------------------------------------------------

folder.exists
^^^^^^^^^^^^^
  
  Determine if the given file exists.|

=======  ==============================================================
 bool_    folder.exists ( string_ sFolderPath )
=======  ==============================================================

----------------------------------------------------------------------

folder.list
^^^^^^^^^^^
	
  List directory contents.

========  ==============================================================
 table_ 	 folder.list ( string_ sFolderPath )
========  ==============================================================

----------------------------------------------------------------------

folder.remove
^^^^^^^^^^^^^
  
  Remove current folder.

======  ==============================================================
 nil_     file.exists ( string_ sFolderPath )
======  ==============================================================

----------------------------------------------------------------------

folder.remove_tree
^^^^^^^^^^^^^^^^^^
  
  Remove folder and all contents

======  ==============================================================
 nil_     file.remove_tree ( string_ sFolderPath )
======  ==============================================================


.. // Required values for html docs visualization
.. include:: ../directives.rst