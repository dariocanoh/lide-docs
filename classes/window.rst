.. /////// 14/06/2015 - Dario Cano [thdkano@gmail.com]
.. // classes/widgets/window.rst
.. //  Class Window reference
.. //   (c) 2015 Dario Cano | lide license

.. _ClassWindow:

Window
======
.. note::
  
  Window is derived from  :ref:`Widget class <ClassWidget>`.

  A Window is an object whose size and position can (usually) be changed by the user. It usually has 
  thick borders and a title bar, and can optionally contain a menu bar, toolbar and status bar. 
  A Window contains any control or other windows sometimes.

----------------------------------------------------------------------------------------------------

Constructor
***********

Window class has a complex constructor:

::

  Window:new {
     number ID, string Name, 
     
     number PosX  , number PosY,
     number Width , number Height,

     string Title,
  }


Arguments
^^^^^^^^^

These arguments are received by class constructor.

============  ======================================================================================
  Argument     Description
============  ======================================================================================
 ID            The object identificator 
 Name          The object's name
 PosX          Position related to X
 PosY          Position related to Y
 Width         Width of the widget
 Height        Height of the widget
 Title         The caption of the window.
============  ======================================================================================

----------------------------------------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=====================  =================================================================================
  Class Method            Description
=====================  =================================================================================
 Object:getID_           Returns widget's identifier.
 Object:setID_           Sets the widget identifier.
 Object:getName_         Returns widget's name.
 Object:setName_         Sets the widget name.
 Widget:getParent_       Returns control's parent.
 Widget:setParent_       Sets the control parent.
 Widget:getPosX_         Returns control's position related to X.
 Widget:setPosX_         Sets the control position related to X.
 Widget:getPosY_         Returns control's position related to Y.
 Widget:setPosY_         Sets the control position related to Y.
 Widget:getWidth_        Returns control's width.
 Widget:setWidth_        Sets the control width.
 Widget:getHeight_       Returns control's height.
 Widget:setHeight_       Sets the control height.
 Widget:getwxObj_        Returns a reference to the C++ control.
 Widget:getEnabled_      Returns true if is enabled.
 Widget:setEnabled_      Set control enabled or disabled.
 Widget:getVisible_      Returns the control visibility.
 Widget:setVisible_      Returns the control visibility.
=====================  =================================================================================

----------------------------------------------------------------------------------------------------

Class Methods
*************

These methods are defined by this class.

----------------------------------------------------------------------------------------------------

Window:centre
^^^^^^^^^^^^^

  Centers the window on the display.

======  ============================================================================================
 nil_    Window:centre( )
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------

Window:show
^^^^^^^^^^^

	Shows the Window. Returns true if the window has been shown or hidden or false if nothing was done 
  because it already was in the requested state.

=======  ===========================================================================================
 bool_ 	  Window:show( bool_ bShow = true )
=======  ===========================================================================================
 
----------------------------------------------------------------------------------------------------

Window:getMinSize
^^^^^^^^^^^^^^^^^

  Gets the minimum size of the window.

   *Returns two numbers: Width, Height*

==================  ================================================================================
 number_, number_    Window:getMinSize( )
==================  ================================================================================
 
----------------------------------------------------------------------------------------------------

Window:setMinSize
^^^^^^^^^^^^^^^^^

  Sets the minimum size of the window, to indicate to the sizer layout mechanism that this is the 
  minimum required size. 

======  ============================================================================================
 nil_    Window:setMinSize( number_ Width, number_ Height )
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------

Window:getMaxSize
^^^^^^^^^^^^^^^^^

  Gets the maximum size of the window.

   *Returns two numbers: Width, Height*

==================  ================================================================================
 number_, number_    Window:getMaxSize( )
==================  ================================================================================

----------------------------------------------------------------------------------------------------

Window:setMaxSize
^^^^^^^^^^^^^^^^^

  Sets the maximum size of the window, to indicate to the sizer layout mechanism that this is the 
  maximum possible size.

======  ============================================================================================
 nil_    Window:setMaxSize( number_ Width, number_ Height )
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------

Window:maximize
^^^^^^^^^^^^^^^

  Maximize or restore the Window.

======  ============================================================================================
 nil_    Window:maximize( bool_ Maximize )
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------

Window:isMaximized
^^^^^^^^^^^^^^^^^

  Returns true if the window is maximized.

=======  ===========================================================================================
 bool_    Window:isMaximized( )
=======  ===========================================================================================
 
----------------------------------------------------------------------------------------------------

Window:iconize
^^^^^^^^^^^^^^

  Iconizes (Minimize) or restore the Window.

======  ============================================================================================
 nil_    Window:iconize( bool_ Iconize )
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------

Window:isIconized
^^^^^^^^^^^^^^^^^

  Returns true if the window is iconized.

=======  ===========================================================================================
 bool_    Window:isIconized( )
=======  ===========================================================================================
 
----------------------------------------------------------------------------------------------------

Window:getTitle
^^^^^^^^^^^^^^^

  Gets a string containing the window caption.

=========  =========================================================================================
 string_    Window:getTitle( )
=========  =========================================================================================
 
----------------------------------------------------------------------------------------------------

Window:setTitle
^^^^^^^^^^^^^^^

  Sets the window caption.

======  ============================================================================================
 nil_    Window:setTitle( string Title )
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------

Window:setMenubar
^^^^^^^^^^^^^^^^^

  Tells the window to show the given menu objects at menu bar.

  If the frame is destroyed, the menu bar and its menus will be destroyed also, so do not delete the 
  menu bar explicitly (except by resetting the frame's menu bar to another frame or NULL).

  Under Windows, a size event is generated, so be sure to initialize data members properly before 
  calling SetMenuBar.

  Note that on some platforms, it is not possible to call this function twice for the same frame 
  object.

======  ============================================================================================
 nil_    Window:setMenubar( table_ tMenus )
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------

Window:createStatusbar
^^^^^^^^^^^^^^^^^^^^^^

  Creates a status bar at the bottom of the frame. "nFields" are the number of fields to create. 
  Specify a value greater than 1 to create a multi-field status bar.

  Statusbar Styles:
  
    SB_NORMAL = (Default) The field appears sunken with a standard 3D border.
    SB_FLAT   = No border is painted around the field so that it appears flat.
    SB_RAISED = A raised 3D border is painted around the field.

======  ============================================================================================
 nil_    Window:createStatusBar( number_ nFields , number_ nStyle = SB_NORMAL )
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------

Window:setStatusWidths
^^^^^^^^^^^^^^^^^^^^^^

  Sets the widths of the fields in the status bar. You must be send many widths as fields exists.
  
======  ============================================================================================
 nil_    Window:createStatusBar( number_ ... )
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------

Window:setStatusText
^^^^^^^^^^^^^^^^^^^^

  Sets the status bar text and redraws the status bar.
  
======  ============================================================================================
 nil_    Window:setStatusText( string_ sText, number_ nField )
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------

Window:setStatusBarPane
^^^^^^^^^^^^^^^^^^^^^^^

  Set the status bar pane used to display menu and toolbar help. Use -1 for disable help text.
  
======  ============================================================================================
 nil_    Window:setStatusBarPane( number_ nField )
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------


Events
******

The following events are emitted by this class:

==============================  ====================================================================
  Event name                      Description
==============================  ====================================================================
 :ref:`Window_onShow`            When the window is shown.
==============================  ====================================================================

----------------------------------------------------------------------------------------------------

Example
*******

In this example we create a new window ...

.. code-block:: lua
   :linenos:
   :emphasize-lines:3,5
    
    myWnd = Window:new {
    	ID = 100, Name = "MyWindow",
    	
    	-- PosX = 30, PosY = 70, Width , Height, >> Here we don't send the size, for using default sizes

    	Title  = "YOUR NEW WINDOW",
    }

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst