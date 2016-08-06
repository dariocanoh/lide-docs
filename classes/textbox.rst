.. /////// 2016/03/20 - Dario Cano [thdkano@gmail.com]
.. // classes/widgets/controls/textbox.rst
.. //  Class Textbox reference
.. //   (c) 2016 Dario Cano | lide license

.. _ClassTextbox:

Textbox
=======
.. note::

  Textbox is derived from TextCtrl_ class.

This class currently simply presents a simpler to use interface for the TextCtrl_ -- it can be thought 
of as a façade for that complicated class. Using it is preferable to using TextCtrl directly whenever 
possible because in the future some ports might implement Textbox but not the full set of TextCtrl
features.

Other than different interface, this class is identical to TextCtrl. In particular, it uses the same 
events, same window styles and so on.

----------------------------------------------------------------------------------------------------


Constructor
***********

Textbox class has a complex constructor:


.. code-block:: lua

 object Textbox:new {
 		number ID, string Name,
 		object Parent, Text = 'My Textbox'
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

==================================  ================================================================
  Class Method             			 Description
==================================  ================================================================
  Object:getID_          			 Returns object's identifier.
  Object:setID_          			 Sets the object identifier.
  Object:getName_        			 Returns object's name.
  Object:setName_        			 Sets the object name.
  Widget:getParent_      			 Returns object's parent.
  Widget:setParent_      			 Sets the object parent.
  Widget:getPosX_        			 Returns object's position related to X.
  Widget:setPosX_        			 Sets the object position related to X.
  Widget:getPosY_        			 Returns object's position related to Y.
  Widget:setPosY_        			 Sets the object position related to Y.
  Widget:getWidth_       			 Returns object's width.
  Widget:setWidth_       			 Sets the object width.
  Widget:getHeight_      			 Returns object's height.
  Widget:setHeight_      			 Sets the object height.
  Widget:getwxObj_       			 Returns the wxWidgets object.
  Control:getText_       			 Returns the button text.
  Control:setText_       			 Sets the button text.
  TextCtrl:saveFile_				 Saves the contents of the control in a text file.
  TextCtrl:loadFile_				 Loads and displays the named file, if it exists.
  TextCtrl:replace_				     Replaces the text at the given position.
  TextCtrl:remove_				     Removes the text starting at the given position.
  TextCtrl:positionToXY_			 Converts given position to a zero-based column, line number pair.
  TextCtrl:xyToPosition_			 Converts the given zero based column and line number to a position.
  TextCtrl:getSelection_			 Gets the current selection span.
  TextCtrl:getStringSelection_	     Gets the text currently selected in the control.
  TextCtrl:getLineLength_			 Gets the length of the specified line.
  TextCtrl:getLineText_			     Returns the contents of a given line in the text control.
  TextCtrl:getNumberOfLines_		 Returns the number of lines in the text control buffer.
  TextCtrl:isEditable_			     Returns true if the controls contents may be edited by user.
  TextCtrl:isModified_			     Returns true if the text has been modified by user
  TextCtrl:isMultiline_			     Returns true if this is a multi line edit control and false otherwise.
  TextCtrl:setMaxLength_			 This function sets the maximum number of characters the user can enter into the control.
  TextCtrl:setSelection_			 Selects the text starting at the first position up to (but not including) the character at the last position.
  TextCtrl:setEditable_			     Makes the text item editable or read-only, overriding the TC_READONLY flag.
  TextCtrl:canCut_				     Returns true if the selection can be cut to the clipboard.
  TextCtrl:canCopy_				     Returns true if the selection can be copied to the clipboard.
  TextCtrl:canPaste_				 Returns true if the contents of the clipboard can be pasted into the text control.
  TextCtrl:canUndo_				     Returns true if there is an undo facility available and the last operation can be undone.
  TextCtrl:canRedo_				     Returns true if there is a redo facility available and the last operation can be redone.
  TextCtrl:cutToClipboard_		     Copies to the clipboard the text from 'nFrom' to 'nTo' and removes the selection.
  TextCtrl:copyToClipboard_		     Copies to the clipboard the text between 'nFrom' to 'nTo'.
  TextCtrl:pasteFromClipboard_	     Pastes text from the clipboard to the text item. 
  TextCtrl:undo_					 If there is an undo facility and the last operation can be undone, undoes the last operation.
  TextCtrl:redo_					 If there is a redo facility and the last operation can be redone, redoes the last operation.
  TextCtrl:appendText_			     Appends the text to the end of the text control.
  TextCtrl:clear_					 Clears the text in the control.
  TextCtrl:markDirty_				 Mark text as modified (dirty).
  TextCtrl:discardEdits_			 Resets the internal modified flag as if the current changes had been saved.
  TextCtrl:getInsertionPoint_		 Returns the insertion point.
  TextCtrl:getLastPosition_		     Returns the zero based index of the last position in the text control.
  TextCtrl:getRange_				 Returns the string containing the text starting in the positions from and up to to in the control.
  TextCtrl:setInsertionPoint_		 Sets the insertion point at the given position.
  TextCtrl:setInsertionPointEnd_	 Sets the insertion point at the end of the text control.
  TextCtrl:writeText_				 Writes the text into the text control at the current insertion position.
  TextCtrl:showPosition_			 Makes the line containing the given position visible.
==================================  ================================================================

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst