.. /////// 2016/11/24 - Dario Cano [thdkano@gmail.com]
.. // docs/classes/Menu.rst
.. //  Class Menu reference
.. //   (c) 2016 Dario Cano | lide license

.. _ClassMenu:

Menu
====
.. note::

  Menu is derived from :ref:`Object class<ClassObject>`.

A menu is a popup (or pull down) list of items, one of which may be selected before the menu goes 
away (clicking elsewhere dismisses the menu).

Menus may be used to construct either menu bars or popup menus.

----------------------------------------------------------------------------------------------------


Constructor
***********

Menu class has a single constructor:


.. code-block:: c++

  object Menu:new {
      number ID, string Name, 
      
      number Style, number Text,
  }


Arguments
^^^^^^^^^

These arguments are received by class constructor.

============  ======================================================================================
  Argument     Description
============  ======================================================================================
 Name          The Menu name
 Text          The Menu text
 Style         Menu Style
 ID            Menu's identificator 
============  ======================================================================================

----------------------------------------------------------------------------------------------------


Events
******

The following events are emitted by this class:

=========================  =========================================================================
  Event name                Description
=========================  =========================================================================
 Menu.onEnter_            When the mouse moves onto this Menu.
 Menu.onLeave_            When the mouse moves out to this Menu.
=========================  =========================================================================

----------------------------------------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=================  =================================================================================
  Class Method       Description
=================  =================================================================================
 Object:getID_      Returns Menu's identifier.
 Object:setID_      Sets the Menu identifier.
 Object:getName_    Returns Menu's name.
 Object:setName_    Sets the Menu name.
=================  =================================================================================

----------------------------------------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.

----------------------------------------------------------------------------------------------------


Menu:getText
^^^^^^^^^^^^
  
   Returns the menu text.

=========  =========================================================================================
 object_    Menu:getText()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Menu:addSeparator
^^^^^^^^^^^^^^^^^
	
   Adds a separator to the end of the menu.

=========  =========================================================================================
 number_ 	  Menu:addSeparator()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Menu:addItem
^^^^^^^^^^^^

   Adds a menu item.

==========  ========================================================================================
 bool_       Menu:addItem( string_ sText, number_ nID, string_ sHelpStr, string_ sShortcut)
==========  ========================================================================================

----------------------------------------------------------------------------------------------------


Menu:setEnabled
^^^^^^^^^^^^^^^

   Enables or disables (greys out) a menu item.

=========  =========================================================================================
 number_    Menu:setEnabled( number_ nID, bool_ bEnable )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


.. // Required values for html docs visualization
.. include:: ../directives.rst