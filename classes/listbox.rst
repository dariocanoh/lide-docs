.. /////// 2018/02/04 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/widgets/controls/listbox.rst
.. //  Class Listbox reference
.. //   (c) 2018 Hernan Dario Cano | lide license

.. _ClassListbox:

Listbox
=======

   Listbox is derived from Control_ class.

   ``[lide.widgets] ^1.1`` ``lide.widgets.controls.listbox 1.1``

A listbox is used to select one or more of a list of strings.

The strings are displayed in a scrolling box, with the selected 
string(s) marked in reverse video. 
A listbox can be single selection (if an item is selected, the 
previous selection is removed) or multiple selection (clicking an item 
toggles the item on or off independently of other selections).

Listbox elements are numbered from zero and while the maximal number 
of elements is unlimited, it is usually better to use a virtual 
control, not requiring to add all the items to it at once, such as 
wxDataViewCtrl or wxListCtrl with wxLC_VIRTUAL style, once more than a 
few hundreds items need to be displayed because this control is not 
optimized, neither from performance nor from user interface point of 
view, for large number of items.

Notice that currently TAB characters in list box items text are not 
handled consistently under all platforms, so they should be replaced 
by spaces to display strings properly everywhere. The listbox doesn't 
support any other control characters at all.

----------------------------------------------------------------------


Constructor
***********

Listbox class has a complex constructor:


.. code-block:: lua

 object Listbox:new {
 		object Parent, string Name,
 		table Choices = { "item 1", "item 2", "item3" }
 	}

----------------------------------------------------------------------

Events
******

The following events are emitted by this class:

=========================  =========================================================================
  Event name                Description
=========================  =========================================================================
 Widget.onEnter_             When the mouse moves onto this widget.
 Widget.onLeave_             When the mouse moves out to this widget.
 Listbox.onSelected_         When an item on the list is selected or the selection changes. 
=========================  =========================================================================

----------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=====================  ===============================================
  Class Method           Description
=====================  ===============================================
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
  Widget:getBind_        Returns the wxWidgets object.
=====================  ===============================================

----------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


Listbox:initListboxEvents
^^^^^^^^^^^^^^^^^^^^^^^^^
   
   Initialize listbox control related events. See 
   Widget:initWidgetEvents for more info.

	*Returns: true or false, string_ error_message*
	
========  ============================================================
 bool_      Listbox:initListboxEvents ( table_ tEvents )
========  ============================================================

----------------------------------------------------------------------


Listbox:insertItems
^^^^^^^^^^^^^^^^^^^
   
   Insert the given number of strings before the specified position. 

========  ============================================================
 nil_      Listbox:insertItems ( table_ tItems, number_ nPosition )
========  ============================================================

----------------------------------------------------------------------


Listbox:deselect
^^^^^^^^^^^^^^^^
	
   Deselects an item in the list box.
   
   *Returns: This applies to multiple selection listboxes onlys*

=======  =============================================================
 nil_     Listbox:deselect( number_ nItem )
=======  =============================================================

----------------------------------------------------------------------


Listbox:setChoices
^^^^^^^^^^^^^^^^^^

   Replaces the current control contents with the given items.

   Notice that calling this method is usually much faster than 
   appending them one by one if you need to add a lot of items.

======  ==============================================================
 nil_ 	 Listbox:setChoices( table_ tChoices )
======  ==============================================================

----------------------------------------------------------------------


Listbox:getChoices
^^^^^^^^^^^^^^^^^^
	
   Returns a table of control choices.

========  ============================================================
 table_    Listbox:getChoices( )
========  ============================================================

----------------------------------------------------------------------


Listbox:setSelection
^^^^^^^^^^^^^^^^^^^^
	
	Sets the selection to the given item *nSelect* or removes the 
  selection entirely if ``nSelect == wx.wxNOT_FOUND``

	Note that this does not cause any command events to be emitted nor 
  does it deselect any other items in the controls which support 
  multiple selections.

======  ==============================================================
 nil_ 	 Listbox:setSelection( number_ nSelect )
======  ==============================================================

----------------------------------------------------------------------


Listbox:getSelection
^^^^^^^^^^^^^^^^^^^^^
	
	Returns the index of the selected item or ``wx.wxNOT_FOUND`` if no 
  item is selected.

	*Returns: The position of the current selection*

	.. note::
    	
   This method can be used with single selection list boxes only, you 
   should use ``Listbox:getSelections()`` for the listboxes with 
   ``LB_MULTIPLE`` style.

=========  ===========================================================
 number_ 	  Listbox:getSelection()
=========  ===========================================================

----------------------------------------------------------------------


Listbox:isSelected
^^^^^^^^^^^^^^^^^^
	
	Determines whether an item is selected.

	*Returns: true if the given item is selected, false otherwise*

=======  =============================================================
 bool_     Listbox:isSelected( number_ nItem )
=======  =============================================================

----------------------------------------------------------------------


Listbox:getItemString
^^^^^^^^^^^^^^^^^^^^^
	
	Returns the label of the item with the given index.

	*Returns: The label of the item or an empty string if the position 
  was invalid*

=========  ===========================================================
 string_ 	  Listbox:getItemString( number_ nItem )
=========  ===========================================================

----------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst