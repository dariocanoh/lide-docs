.. /////// 2017/04/13 - Dario Cano (Dario Cano [dcanohdev@gmail.com])
.. // classes/widgets/controls/toolbar.rst
.. //  Class Toolbar reference
.. //   (c) 2017 Dario Cano | lide license

.. _ClassToolbar:

Toolbar
=======

A toolbar is a bar of buttons and/or other controls usually placed below the menu bar in a Window_.

----------------------------------------------------------------------------------------------------


Constructor
***********

Toolbar class has a complex constructor:


.. code-block:: lua

 object Toolbar:new {
      *number ID, string Name, object Parent,
      *number Flags = TB_HORZ_TEXT
 }


Constructor flags
^^^^^^^^^^^^^^^^^

These are the flags received by class constructor.

====================  ===========  ======================================================================================
  Flag                 Value         Description
====================  ===========  ======================================================================================
 ``TB_FLAT``            ``32``       "flat" buttons (Win32/GTK only)
 ``TB_HORIZONTAL``      ``4``        lay out the toolbar horizontally
 ``TB_VERTICAL``        ``8``        lay out the toolbar vertically
 ``TB_TEXT``            ``256``      show the text (not shown by default)
 ``TB_NOICONS``         ``128``      don't show the icons (they're shown by default)
 ``TB_NODIVIDER``       ``512``      don't show the divider between toolbar and the window (Win32 only)
 ``TB_NOALIGN``         ``1024``     no automatic alignment (Win32 only, useless)
 ``TB_HORZ_LAYOUT``     ``2048``     show the text and the icons alongside, not vertically stacked (Win32/GTK)
 ``TB_HORZ_TEXT``       ``2304``     Combination of ``TB_HORZ_LAYOUT`` and ``TB_TEXT``
====================  ===========  ======================================================================================


------------------------------------------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=====================  =============================================================================
  Class Method             Description
=====================  =============================================================================
  Object:getID_          Returns object's identifier.
  Object:setID_          Sets the object identifier.
  Object:getName_        Returns object's name.
  Object:setName_        Sets the object name.
  Widget:getParent_      Returns object's parent.
  Widget:setParent_      Sets the object parent.
  Widget:getwxObj_       Returns the wxWidgets object.
=====================  =============================================================================

----------------------------------------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.

----------------------------------------------------------------------------------------------------


Toolbar:addTool
^^^^^^^^^^^^^^^
   
   Adds a tool to the toolbar.

    *Returns a number: index of tool.*

=========  =========================================================================================
 number_    Toolbar:addTool( number_ nID, string_ sText, string_ sImage, string_ sTooltip )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Toolbar:addControl
^^^^^^^^^^^^^^^^^^
  
   Adds any control to the toolbar, typically e.g. a ComboBox_.

=========  =========================================================================================
   nil_     Toolbar:addControl( object_ objControl )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Toolbar:getToolEnabled
^^^^^^^^^^^^^^^^^^^^^^
	
   Called to determine whether a tool is enabled (responds to user input).

=========  =========================================================================================
  bool_ 	Toolbar:getToolEnabled( number_ nToolID )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Toolbar:setImageSizes
^^^^^^^^^^^^^^^^^^^^^
	
   Set size for tool's bitmap.

=========  =========================================================================================
  nil_      Toolbar:setImageSizes( number_ nWidth, number_ nHeight )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Toolbar:setRows
^^^^^^^^^^^^^^^
	
   Set number of rows.

=========  =========================================================================================
  nil_      Toolbar:setRows( number_ nRows )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Toolbar:getMaxRows
^^^^^^^^^^^^^^^^^^
	
   Get total number of rows.

=========  =========================================================================================
 number_    Toolbar:getMaxRows()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Toolbar:getMaxCols
^^^^^^^^^^^^^^^^^^
	
   Get total number of columns.

=========  =========================================================================================
 number_    Toolbar:getMaxCols()
=========  =========================================================================================


Toolbar:getToolImageFilename
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
	
   Get filename of given tool.

=========  =========================================================================================
 number_    Toolbar:getToolImageFilename( number_ nID )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst  