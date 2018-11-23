.. /////// 2017/04/27 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/classes/font.rst
.. //  Class Font reference
.. //   (c) 2017 Hernan Dario Cano | GNU GENERAL PUBLIC LICENSE

.. _ClassFont:

Font
====

  Font is derived from :ref:`Object class<ClassObject>`.
  
  ``[lide.widgets] ^1.1`` ``lide.classes.font 1.0``


A font is an object which determines the appearance of text, primarily 
when drawing text to a window or device context.

A font is determined by the following parameters (not all of them have 
to be specified, of course):

Specifying a family, rather than a specific typeface name, ensures a 
degree of portability across platforms because a suitable font will be 
chosen for the given font family, however it doesn't allow to choose a 
font precisely as the parameters above don't suffice, in general, to 
identify all the available fonts and this is where using the native 
font descriptions may be helpful - see below.

Under Windows, the face name can be one of the installed fonts on the 
user's system. Since the choice of fonts differs from system to 
system, either choose standard Windows fonts, or if allowing the user 
to specify a face name, store the family name with any file that might 
be transported to a different Windows machine or other platform.

.. note::

 There is currently a difference between the appearance of fonts on 
 the two platforms, if the mapping mode is anything other than 
 (`wxMM_TEXT <http://docs.wxwidgets.org/3.1.0/interface_2wx_2dc_8h.html#a5a641b839b9ac2ff94514d0596f6e20aa7cb493f78fed283bdc4d3e0797400df6>`_).
 Under X, font size is always specified in points. Under MS Windows, 
 the unit for text is points but the text is scaled according to the 
 current mapping mode. However, user scaling on a device context will 
 also scale fonts under both environments.
 
----------------------------------------------------------------------------------------------------


Constructor
***********

Font class has two constructors:

.. code-block:: lua

 object Font:new ( string FaceName, number FontSize, string FontFlags )

.. code-block:: lua

 object Font:new { 
 	string FaceName  = 'Calibri', 
 	string FontFlags = 'Bold'
 	number FontSize  = 12,
 }


==================  ======================================================================================
  Argument            Description
==================  ======================================================================================
 FaceName            The font face name
 FontSize            Font size in points.
 FontFlags           Font family, style and weight flags, values must be:

                     - ``"Bold"``
                     - ``"Underline"``
                     - ``"Italic"``

                     You can add this flags separated by comma: ``"Bold, Underline"``
==================  ======================================================================================

----------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=================  ===================================================
  Class Method       Description
=================  ===================================================
 Object:getName_    Returns font's name.
 Object:setName_    Sets the font name.
=================  ===================================================

----------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


----------------------------------------------------------------------


Font:getDescString
^^^^^^^^^^^^^^^^^^

   Gets the font description.

=========  ===========================================================
 string_    Font:getDescString()
=========  ===========================================================

----------------------------------------------------------------------


Font:getBind
^^^^^^^^^^^^
   
   Returns a reference to the C++ instance.

===========  =========================================================
 userdata_    Font:getBind()
===========  =========================================================

----------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst