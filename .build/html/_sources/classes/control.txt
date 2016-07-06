.. /////// 14/06/2015 - Dario Cano [thdkano@gmail.com]
.. // classes/control.rst
.. //  Class Control reference
.. //   (c) 2015 Dario Cano | lide license

.. _ClassControl:

Control
=======
.. note::

  Control is derived from :ref:`Widget class<ClassWidget>`.

This class is an abstract base class for objects called controls. The purpose is to define properties 
and methods shared for derivated classes. 

----------------------------------------------------------------------------------------------------


Constructor
***********

Control class has a single constructor:


.. code-block:: lua

 Control:new ( string sControlName, object oParent, number nPosX, number nPosY, number nWidth, number nHeight, number nID )


Arguments
^^^^^^^^^

These arguments are received by class constructor.

============  ======================================================================================
  Argument     Description
============  ======================================================================================
 sControlName  The control name
 oParent       The control parent
 nPosX         Position related to X
 nPosY         Position related to Y
 nWidth        Width of the control
 nHeight       Height of the control
 nID           The object identificator 
============  ======================================================================================


----------------------------------------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=====================  =============================================================================
  Class Method          Description
=====================  =============================================================================
 Object:getID_		       Returns control's identifier.
 Object:setID_		       Sets the control identifier.
 Object:getName_	       Returns control's name.
 Object:setName_	       Sets the control name.
 Widget:getParent_	     Returns control's parent.
 Widget:setParent_	     Sets the control parent.
 Widget:getPosX_	       Returns control's position related to X.
 Widget:setPosX_	       Sets the control position related to X.
 Widget:getPosY_	       Returns control's position related to Y.
 Widget:setPosY_	       Sets the control position related to Y.
 Widget:getWidth_	       Returns control's width.
 Widget:setWidth_	       Sets the control width.
 Widget:getHeight_	     Returns control's height.
 Widget:setHeight_	     Sets the control height.
 Widget:getwxObj_	       Returns a reference to the C++ control.
 Widget:getEnabled_      Returns true if is enabled.
 Widget:setEnabled_      Set control enabled or disabled.
 Widget:getVisible_      Returns the control visibility.
 Widget:setVisible_      Returns the control visibility.
=====================  =============================================================================

----------------------------------------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


Control:getText
^^^^^^^^^^^^^^^
   
   Returns the control text.

=========  =========================================================================================
 string_    Control:getText( bool_ bMnemonics )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Control:setText
^^^^^^^^^^^^^^^
	
   Set control's text.

======  ============================================================================================
 nil_ 	 Control:setText( string_ sNewText )
======  ============================================================================================

----------------------------------------------------------------------------------------------------


Control:getFont
^^^^^^^^^^^^^^^
	
   Returns the control's font.

=======  ===========================================================================================
 Font_    Control:getFont( )
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


Control:setFont
^^^^^^^^^^^^^^^
	
   Set control's font.

======  ============================================================================================
 nil_ 	 Control:setFont( string_ sFontFamily, number_ nFontSize, string_ sFontFlags )
======  ============================================================================================

----------------------------------------------------------------------------------------------------


.. // Required values for html docs visualization
.. include:: ../directives.rst