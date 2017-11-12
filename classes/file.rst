.. /////// 2017/04/27 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/classes/font.rst
.. //  Class Font reference
.. //   (c) 2017 Hernan Dario Cano | GNU GENERAL PUBLIC LICENSE

.. _ClassFile:

File
====

An abstract representation of file and directory pathnames. 
User interfaces and operating systems use system-dependent pathname strings to name files and 
directories. This class presents an abstract, system-independent view of hierarchical pathnames. 
An abstract pathname has two components: 
An optional system-dependent prefix string, such as a disk-drive specifier, "/" for the UNIX root 
directory, or "\\\\" for a Microsoft Windows UNC pathname, and a sequence of zero or more string names. 
The first name in an abstract pathname may be a directory name or, in the case of Microsoft Windows 
UNC pathnames, a hostname.
 
----------------------------------------------------------------------------------------------------


Constructor
***********

File class constructors:

.. code-block:: lua

 object Font:new ( string filePath )


==================  ======================================================================================
  Argument            Description
==================  ======================================================================================
 filePath            Creates a new File instance that represents actually string filePath.
==================  ======================================================================================

----------------------------------------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=================  =================================================================================
  Class Method       Description
=================  =================================================================================
 Object:getName_    Returns font's name.
 Object:setName_    Sets the font name.
=================  =================================================================================

----------------------------------------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


----------------------------------------------------------------------------------------------------


Font:getDescString
^^^^^^^^^^^^^^^^^^

   Gets the font description.

=========  =========================================================================================
 string_    Font:getDescString()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Font:getBind
^^^^^^^^^^^^
   
   Returns a reference to the C++ instance.

===========  =======================================================================================
 function_    Font:getBind()
===========  =======================================================================================

-----------------------------------------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst