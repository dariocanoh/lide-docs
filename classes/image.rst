.. /////// 2018/02/04 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/widgets/controls/image.rst
.. //  Class Image reference
.. //   (c) 2018 Hernan Dario Cano | lide license

.. _ClassImage:

Image
======
.. note::

  Image is derived from Control_ class.

A static bitmap control displays a bitmap.

Native implementations on some platforms are only meant for display of the small icons in the dialog 
boxes.

Notice that for the best results, the size of the control should be the same as the size of the 
image displayed in it, as happens by default if it's not resized explicitly. Otherwise, behaviour 
depends on the platform: under Windows, the bitmap is drawn centred inside the control, while 
elsewhere it is drawn at the origin of the control.

----------------------------------------------------------------------------------------------------


Constructor
***********

Image class has a complex constructor:


.. code-block:: lua

 object Image:new {
 		number ID, string Name,
 		object Parent, Text = 'My Image'
 	}

------------------------------------------------------------------------------------------------------

Events
******

The following events are emitted by this class:

=========================  =========================================================================
  Event name                Description
=========================  =========================================================================
 Widget.onEnter_             When the mouse moves onto this widget.
 Widget.onLeave_             When the mouse moves out to this widget.
=========================  =========================================================================

------------------------------------------------------------------------------------------------------

Inherited Methods
*****************

These methods are inherited from its super classes:

=====================  =============================================================================
  Class Method             Description
=====================  =============================================================================
  Object:getName_        Returns object's name.
  Object:setName_        Sets the object name.
  Widget:getParent_      Returns object's parent.
  Widget:setParent_      Sets the object parent.
  Widget:getPosX_        Returns object's position related to X.
  Widget:setPosX_        Sets the object position related to X.
  Widget:getPosY_        Returns object's position related to Y.
  Widget:setPosY_        Sets the object position related to Y.
  Widget:getWidth_       Returns object's width.
  Widget:setWidth_       Sets the object width.
  Widget:getHeight_      Returns object's height.
  Widget:setHeight_      Sets the object height.
  Widget:getwxObj_       Returns the wxWidgets object.
=====================  =============================================================================


Image:getFile
^^^^^^^^^^^^^
   
   Returns the bitmap file currently used in the Image control.

=========  =========================================================================================
 string_    Image:getText( )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Image:setFile
^^^^^^^^^^^^^
  
  Sets the control's Image from file.

=======  ===========================================================================================
 void_    Image:setText( string_ sFilePath )
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


Image:getDepth
^^^^^^^^^^^^^^
  
  Gets the colour depth of the bitmap. A value of ``1`` indicates a monochrome bitmap.

=========  =========================================================================================
 number_    Image:getDepth( )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst