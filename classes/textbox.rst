.. /////// 2016/03/20 - Dario Cano [thdkano@gmail.com]
.. // classes/widgets/controls/textbox.rst
.. //  Class Textbox reference
.. //   (c) 2016 Dario Cano | lide license

.. _ClassTextbox:

Textbox
=======

This class currently simply presents a simpler to use interface for the TextCtrl -- it can be thought 
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
 Widget:getWidth	   				:ref:`Widget class <ClassWidget>`    	 Returns object's width.
 Widget:setWidth	   				:ref:`Widget class <ClassWidget>`    	 Sets the object width.
 Widget:getHeight	   				:ref:`Widget class <ClassWidget>`    	 Returns object's height.
 Widget:setHeight	   				:ref:`Widget class <ClassWidget>`    	 Sets the object height.
 Widget:getwxObj	   				:ref:`Widget class <ClassWidget>`    	 Returns the wxWidgets object.
 TextCtrl:saveFile					:ref:`TextCtrl class <ClassTextCtrl>`    Saves the contents of the control in a text file.
 TextCtrl:loadFile					:ref:`TextCtrl class <ClassTextCtrl>`	 Loads and displays the named file, if it exists.
 TextCtrl:replace					:ref:`TextCtrl class <ClassTextCtrl>`	 Replaces the text at the given position.
 TextCtrl:remove					:ref:`TextCtrl class <ClassTextCtrl>`	 Removes the text starting at the given position.
 TextCtrl:positionToXY				:ref:`TextCtrl class <ClassTextCtrl>`	 Converts given position to a zero-based column, line number pair.
 TextCtrl:xyToPosition				:ref:`TextCtrl class <ClassTextCtrl>`	 Converts the given zero based column and line number to a position.
 TextCtrl:getSelection				:ref:`TextCtrl class <ClassTextCtrl>`	 Gets the current selection span.
 TextCtrl:getStringSelection		:ref:`TextCtrl class <ClassTextCtrl>`	 Gets the text currently selected in the control.
 TextCtrl:getLineLength				:ref:`TextCtrl class <ClassTextCtrl>`	 Gets the length of the specified line.
 TextCtrl:getLineText				:ref:`TextCtrl class <ClassTextCtrl>`	 Returns the contents of a given line in the text control.
 TextCtrl:getNumberOfLines			:ref:`TextCtrl class <ClassTextCtrl>`	 Returns the number of lines in the text control buffer.
 TextCtrl:isEditable				:ref:`TextCtrl class <ClassTextCtrl>`	 Returns true if the controls contents may be edited by user.
 TextCtrl:isModified				:ref:`TextCtrl class <ClassTextCtrl>`	 Returns true if the text has been modified by user
 TextCtrl:isMultiline				:ref:`TextCtrl class <ClassTextCtrl>`	 Returns true if this is a multi line edit control and false otherwise.
 TextCtrl:setMaxLength				:ref:`TextCtrl class <ClassTextCtrl>`	 This function sets the maximum number of characters the user can enter into the control.
 TextCtrl:setSelection				:ref:`TextCtrl class <ClassTextCtrl>`	 Selects the text starting at the first position up to (but not including) the character at the last position.
 TextCtrl:setEditable				:ref:`TextCtrl class <ClassTextCtrl>`	 Makes the text item editable or read-only, overriding the TC_READONLY flag.
 TextCtrl:canCut					:ref:`TextCtrl class <ClassTextCtrl>`    Returns true if the selection can be cut to the clipboard.
 TextCtrl:canCopy					:ref:`TextCtrl class <ClassTextCtrl>`    Returns true if the selection can be copied to the clipboard.
 TextCtrl:canPaste					:ref:`TextCtrl class <ClassTextCtrl>`	 Returns true if the contents of the clipboard can be pasted into the text control.
 TextCtrl:canUndo					:ref:`TextCtrl class <ClassTextCtrl>`	 Returns true if there is an undo facility available and the last operation can be undone.
 TextCtrl:canRedo					:ref:`TextCtrl class <ClassTextCtrl>` 	 Returns true if there is a redo facility available and the last operation can be redone.
 TextCtrl:cutToClipboard			:ref:`TextCtrl class <ClassTextCtrl>`	 Copies to the clipboard the text from 'nFrom' to 'nTo' and removes the selection.
 TextCtrl:copyToClipboard			:ref:`TextCtrl class <ClassTextCtrl>`	 Copies to the clipboard the text between 'nFrom' to 'nTo'.
 TextCtrl:pasteFromClipboard		:ref:`TextCtrl class <ClassTextCtrl>`	 Pastes text from the clipboard to the text item. 
 TextCtrl:undo						:ref:`TextCtrl class <ClassTextCtrl>`	 If there is an undo facility and the last operation can be undone, undoes the last operation.
 TextCtrl:redo						:ref:`TextCtrl class <ClassTextCtrl>`	 If there is a redo facility and the last operation can be redone, redoes the last operation.
 TextCtrl:appendText				:ref:`TextCtrl class <ClassTextCtrl>`    Appends the text to the end of the text control.
 TextCtrl:clear						:ref:`TextCtrl class <ClassTextCtrl>`	 Clears the text in the control.
 TextCtrl:markDirty					:ref:`TextCtrl class <ClassTextCtrl>`    Mark text as modified (dirty).
 TextCtrl:discardEdits				:ref:`TextCtrl class <ClassTextCtrl>`	 Resets the internal modified flag as if the current changes had been saved.
 TextCtrl:getInsertionPoint			:ref:`TextCtrl class <ClassTextCtrl>`	 Returns the insertion point.
 TextCtrl:getLastPosition			:ref:`TextCtrl class <ClassTextCtrl>`	 Returns the zero based index of the last position in the text control.
 TextCtrl:getRange					:ref:`TextCtrl class <ClassTextCtrl>`	 Returns the string containing the text starting in the positions from and up to to in the control.
 TextCtrl:setInsertionPoint			:ref:`TextCtrl class <ClassTextCtrl>`	 Sets the insertion point at the given position.
 TextCtrl:setInsertionPointEnd		:ref:`TextCtrl class <ClassTextCtrl>`	 Sets the insertion point at the end of the text control.
 TextCtrl:writeText					:ref:`TextCtrl class <ClassTextCtrl>`	 Writes the text into the text control at the current insertion position.
 TextCtrl:showPosition				:ref:`TextCtrl class <ClassTextCtrl>`	 Makes the line containing the given position visible.

=================================  =======================================  ================================================================================================================


Events
******

The following events are emitted by this class:

.. toctree::
    :hidden:
    
	classes/widget.onenter
    classes/widget.onleave
    classes/controls/Textbox.onclick

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../types.rst