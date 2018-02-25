.. /////// 2018/02/22 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/widgets/controls/combobox.rst
.. //  Class Combobox reference
.. //   (c) 2018 Hernan Dario Cano | lide license

.. _ClassCombobox:

Combobox
=======
.. note::

  Combobox is derived from Control_ class.

The Combobox control is used to display data in a drop-down combo box. By default, the 
Combobox control appears in two parts: the top part is a text box that allows the user to type a 
list item. The second part is a list box that displays a list of items from which the user can 
select one.

----------------------------------------------------------------------------------------------------


Constructor
***********

Combobox class has a complex constructor:


.. code-block:: lua

 object Combobox:new {
 		object Parent, string Name,
 		table Choices = { "item 1", "item 2", "item3" }
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
 Combobox.onSelected_        When an item on the list is selected or the selection changes. 
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

----------------------------------------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


Combobox:getText
^^^^^^^^^^^^^^^^
   
   Returns the current value in the combobox text field.

=========  =========================================================================================
 string_      Combobox: getText ( )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Combobox:setText
^^^^^^^^^^^^^^^^
	
   Set the current value in the Combobox.

=======  ===========================================================================================
 nil_     Combobox: setText( string_ sText )
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


Combobox:setChoices
^^^^^^^^^^^^^^^^^^^

   Set the current choices in the Combobox.

======  ============================================================================================
 nil_ 	Combobox:setChoices ( table_ tChoices )
======  ============================================================================================

----------------------------------------------------------------------------------------------------


Combobox:getchoices
^^^^^^^^^^^^^^^^^^^
	
   Returns a table of control choices.

========  ==========================================================================================
 table_    Combobox:getChoices( )
========  ==========================================================================================

----------------------------------------------------------------------------------------------------


Combobox:setSelection
^^^^^^^^^^^^^^^^^^^^^
	
	Sets the selection to the given item *nSelect*.

	Note that this does not cause any command events to be emitted nor does it deselect any other 
	items in the controls which support multiple selections.

======  ============================================================================================
 nil_     Combobox:setSelection( number_ nSelect )
======  ============================================================================================

----------------------------------------------------------------------------------------------------


Combobox:getSelection
^^^^^^^^^^^^^^^^^^^^^
	
	Returns the index of the selected item or ``wx.wxNOT_FOUND`` if no item is selected.

	*Returns: The position of the current selection*

	.. note::
    	
   This method can be used with single selection list boxes only, you should use 
   ``Listbox:getSelections()`` for the listboxes with ``LB_MULTIPLE`` style.

=========  =========================================================================================
 number_ 	Combobox:getSelection()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Combobox:findItem
^^^^^^^^^^^^^^^^^
	
	Finds and returns a reference to a ListItem object in a Combobox control.
	
=========  =========================================================================================
 number_ 	Combobox:findItem( number_ nItem )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Combobox:clear
^^^^^^^^^^^^^^
	
	Clear all items in the Combobox.
	
======  ============================================================================================
 nil_ 	Combobox:clear( )
======  ===========================================================================================

----------------------------------------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst