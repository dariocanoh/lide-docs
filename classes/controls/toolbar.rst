.. /////// 2017/04/13 - Dario Cano (dcanoh [at] protonmail [dot] com)
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
 		number ID, string Name,
 		object Parent
 	}

----------------------------------------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=================================  =======================================  ================================================================================================================
  Class Method         			     Defined in                  		      Description
=================================  =======================================  ================================================================================================================
 Object:getID		   				:ref:`Object class <ClassObject>`    	 Returns object's identifier.
 Object:setID		   				:ref:`Object class <ClassObject>`    	 Sets the object identifier.
 Object:getName		   				:ref:`Object class <ClassObject>`    	 Returns object's name.
 Object:setName		   				:ref:`Object class <ClassObject>`    	 Sets the object name.
 Widget:getParent	   				:ref:`Widget class <ClassWidget>`    	 Returns object's parent.
 Widget:setParent	   				:ref:`Widget class <ClassWidget>`    	 Sets the object parent.
 Widget:getPosX	   	   				:ref:`Widget class <ClassWidget>`    	 Returns object's position related to X.
 Widget:setPosX	   	   				:ref:`Widget class <ClassWidget>`    	 Sets the object position related to X.
 Widget:getPosY	   	   				:ref:`Widget class <ClassWidget>`    	 Returns object's position related to Y.
 Widget:setPosY	   	   				:ref:`Widget class <ClassWidget>`    	 Sets the object position related to Y.
 Widget:getwxObj	   				:ref:`Widget class <ClassWidget>`    	 Returns wxWidget C++ Object.

=================================  =======================================  ================================================================================================================


----------------------------------------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.

----------------------------------------------------------------------------------------------------


Toolbar:addTool
^^^^^^^^^^^^^^^
   
   Adds a tool to the toolbar.

    *Returns a number*

==========  ========================================================================================
 userdata    Toolbar:addTool( number_ nID, string_ sText, string_ sImage, string_ sTooltip )
==========  ========================================================================================

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

.. Events
.. ******
.. 
.. The following events are emitted by this class:
.. 
.. .. toctree:-:
..     :hidden:
..     
.. 	classes/widget.onenter
..     classes/widget.onleave
.. 
.. ----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../types.rst