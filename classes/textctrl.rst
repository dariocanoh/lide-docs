.. /////// 2016/02/25 - Dario Cano [thdkano@gmail.com]
.. // classes/widgets/controls/TextCtrl.rst
.. //  Class TextCtrl reference
.. //   (c) 2016 Dario Cano | lide license

.. _ClassTextCtrl:

TextCtrl
========

A text box allows text to be displayed and edited. It may be single line or multi-line.

----------------------------------------------------------------------------------------------------


Constructor
***********

TextCtrl class has a complex constructor:


.. code-block:: lua

 object TextCtrl:new {
 		number ID, string Name,
 		object Parent, Text = 'My TextCtrl'
 	}

----------------------------------------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=====================  ==================================  =========================================
  Class Method           Defined in                  		  Description
=====================  ==================================  =========================================
 Object:getID		   :ref:`Object class <ClassObject>`    Returns object's identifier.
 Object:setID		   :ref:`Object class <ClassObject>`    Sets the object identifier.
 Object:getName		   :ref:`Object class <ClassObject>`    Returns object's name.
 Object:setName		   :ref:`Object class <ClassObject>`    Sets the object name.
 Widget:getParent	   :ref:`Widget class <ClassWidget>`    Returns object's parent.
 Widget:setParent	   :ref:`Widget class <ClassWidget>`    Sets the object parent.
 Widget:getPosX	   	   :ref:`Widget class <ClassWidget>`    Returns object's position related to X.
 Widget:setPosX	   	   :ref:`Widget class <ClassWidget>`    Sets the object position related to X.
 Widget:getPosY	   	   :ref:`Widget class <ClassWidget>`    Returns object's position related to Y.
 Widget:setPosY	   	   :ref:`Widget class <ClassWidget>`    Sets the object position related to Y.
 Widget:getWidth	   :ref:`Widget class <ClassWidget>`    Returns object's width.
 Widget:setWidth	   :ref:`Widget class <ClassWidget>`    Sets the object width.
 Widget:getHeight	   :ref:`Widget class <ClassWidget>`    Returns object's height.
 Widget:setHeight	   :ref:`Widget class <ClassWidget>`    Sets the object height.
 Widget:getwxObj	   :ref:`Widget class <ClassWidget>`    Returns the wxWidgets object.
=====================  ==================================  =========================================

----------------------------------------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


TextCtrl:loadFile
^^^^^^^^^^^^^^^^^
   
   Loads and displays the named file, if it exists.

========  ==========================================================================================
 bool_     TextCtrl:loadFile ( string_ sFilename )
========  ==========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:saveFile
^^^^^^^^^^^^^^^^^
	
   Saves the contents of the control in a text file.

=======  ===========================================================================================
 bool_ 	  TextCtrl:saveFile( string_ sFilename )
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:replace
^^^^^^^^^^^^^^^^
	
   Replaces the text starting at the first position up to (but not including) the character at the 
   last position with the given text.

======  ============================================================================================
 nil_ 	 TextCtrl:replace( number_ nFrom, number_ nTo, string_ sText )
======  ============================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:remove
^^^^^^^^^^^^^^^
	
   Removes the text starting at the first given position up to (but not including) the character at 
   the last position.

======  ============================================================================================
 nil_ 	 TextCtrl:remove( number_ nFrom, number_ nTo )
======  ============================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:positionToXY
^^^^^^^^^^^^^^^^^^^^^
	
	Converts given position to a zero-based column, line number pair. true on success, false on 
	failure. 

	*Returns: bool_ bSucces, number_ PosX, number_ PosY*


======  ============================================================================================
 nil_ 	 TextCtrl:positionToXY( number_ nPos )
======  ============================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:xyToPosition
^^^^^^^^^^^^^^^^^^^^^
	
	Converts the given zero based column and line number to a position.

	*Returns: number_: The position value, or -1 if nX or nY was invalid. *


=========  =========================================================================================
 number_ 	TextCtrl:xyToPosition( number_ nPosX, number_ nX, number_ nY )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:getSelection
^^^^^^^^^^^^^^^^^^^^^
	
	Gets the current selection span.

	If the returned values are equal, there was no selection. Please note that the indices returned 
	may be used with the other TextCtrl methods but don't necessarily represent the correct indices 
	into the string returned by getValue() for multiline controls under Windows (at least,) you 
	should use getStringSelection() to get the selected text.

	*Returns: number_ nFrom: The returned first position, number_ nTo: The returned last position.*


==================  ================================================================================
 number_, number_ 	 TextCtrl:getSelection()
==================  ================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:getStringSelection
^^^^^^^^^^^^^^^^^^^^^^^^^^^
	
	 Gets the text currently selected in the control. If there is no selection, the returned string 
	 is empty.

=========  =========================================================================================
 string_ 	TextCtrl:getStringSelection()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:getLineLength
^^^^^^^^^^^^^^^^^^^^^^
	
	 Gets the length of the specified line, not including any trailing newline character(s). 

	 *Returns: The length of the line, or -1 if nLineNumber was invalid.*

=========  =========================================================================================
 string_ 	TextCtrl:getLineLength( number_ nLineNumber )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:getLineText
^^^^^^^^^^^^^^^^^^^^
	
	Returns the contents of a given line in the text control, not including any trailing newline 
	character(s).
	
	*Returns: The contents of the line.*

=========  =========================================================================================
 string_ 	TextCtrl:getLineText( number_ nLineNumber )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:getNumberOfLines
^^^^^^^^^^^^^^^^^^^^^^^^^
	
	Returns the number of lines in the text control buffer.

	*Remarks

	Note that even empty text controls have one line (where the insertion point is), so GetNumberOfLines() 
	never returns 0.

	Also note that you may wish to avoid using functions that work with line numbers if you are 
	working with controls that contain large amounts of text as this function has O(N) complexity 
	for N being the number of lines.*

=========  =========================================================================================
 number_ 	TextCtrl:getNumberOfLines()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:isEditable
^^^^^^^^^^^^^^^^^^^
	
	Returns true if the controls contents may be edited by user (note that it always can be changed 
	by the program), i.e. if the control hasn't been put in read-only mode by a previous call to 
	setEditable.

=======  ===========================================================================================
 bool_ 	  TextCtrl:isEditable()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:isModified
^^^^^^^^^^^^^^^^^^^
	
	Returns true if the text has been modified by user. Note that calling setValue doesn't make the 
	control modified.

	*See also: 	MarkDirty()*
	
=======  ===========================================================================================
 bool_ 	  TextCtrl:isModified()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:isMultiline
^^^^^^^^^^^^^^^^^^^^
	
	Returns true if this is a multi line edit control and false otherwise.
	
=======  ===========================================================================================
 bool_ 	  TextCtrl:isMultiline()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:isSingleline
^^^^^^^^^^^^^^^^^^^^^
	
	Returns true if this is a single line edit control and false otherwise.

=======  ===========================================================================================
 bool_ 	  TextCtrl:isSingleline()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:setMaxLength
^^^^^^^^^^^^^^^^^^^^^
	
	This function sets the maximum number of characters the user can enter into the control. In other 
	words, it allows to limit the text value length to len not counting the terminating NUL character.

	If len is 0, the previously set max length limit, if any, is discarded and the user may enter as 
	much text as the underlying native text control widget supports (typically at least 32Kb).

	If the user tries to enter more characters into the text control when it already is filled up to
	the maximal length, a wxEVT_COMMAND_TEXT_MAXLEN event is sent to notify the program about it 
	(giving it the possibility to show an explanatory message, for example) and the extra input is 
	discarded.

	*Note that under GTK+, this function may only be used with single line text controls.*

======  ============================================================================================
 nil_ 	 TextCtrl:setMaxLength( number_ nMaxLength )
======  ============================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:setSelection
^^^^^^^^^^^^^^^^^^^^^
	
	Selects the text starting at the first position up to (but not including) the character at the 
	last position. If both parameters are equal to -1 all text in the control is selected.

======  ============================================================================================
 nil_ 	 TextCtrl:setSelection( number_ nFrom, number_ nTo )
======  ============================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:setEditable
^^^^^^^^^^^^^^^^^^^^
	
	Makes the text item editable or read-only, overriding the TC_READONLY flag.

======  ============================================================================================
 nil_ 	 TextCtrl:setEditable( bool_ bEditable )
======  ============================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:setEditable
^^^^^^^^^^^^^^^^^^^^
	
	Makes the text item editable or read-only, overriding the TC_READONLY flag.

======  ============================================================================================
 nil_ 	 TextCtrl:setEditable( bool_ bEditable )
======  ============================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:canCut
^^^^^^^^^^^^^^^
	
	Returns true if the selection can be cut to the clipboard.

=======  ===========================================================================================
 bool_ 	  TextCtrl:canCut()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:canCopy
^^^^^^^^^^^^^^^^
	
	Returns true if the selection can be copied to the clipboard.

=======  ===========================================================================================
 bool_ 	  TextCtrl:canCopy()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:canPaste
^^^^^^^^^^^^^^^^^
	
	Returns true if the contents of the clipboard can be pasted into the text control. On some platforms 
	(Motif, GTK) this is an approximation and returns true if the control is editable, false otherwise.

=======  ===========================================================================================
 bool_ 	  TextCtrl:canPaste()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:canUndo
^^^^^^^^^^^^^^^^
	
	Returns true if there is an undo facility available and the last operation can be undone.

=======  ===========================================================================================
 bool_ 	  TextCtrl:canUndo()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:canRedo
^^^^^^^^^^^^^^^^
	
	Returns true if there is a redo facility available and the last operation can be redone.

=======  ===========================================================================================
 bool_ 	  TextCtrl:canRedo()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:cutToClipboard
^^^^^^^^^^^^^^^^^^^^^^^
	
	Copies to the clipboard the text from 'nFrom' to 'nTo' and removes the selection.

=======  ===========================================================================================
 void_ 	  TextCtrl:cutToClipboard()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:copyToClipboard
^^^^^^^^^^^^^^^^^^^^^^^^
	
	Copies to the clipboard the text between 'nFrom' to 'nTo'.

=======  ===========================================================================================
 void_ 	  TextCtrl:copyToClipboard()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:pasteFromClipboard
^^^^^^^^^^^^^^^^^^^^^^^^^^^
	
	Pastes text from the clipboard to the text item. 

=======  ===========================================================================================
 void_ 	  TextCtrl:pasteFromClipboard()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:undo
^^^^^^^^^^^^^
	
	If there is an undo facility and the last operation can be undone, undoes the last operation.

	Does nothing if there is no undo facility.

=======  ===========================================================================================
 void_ 	  TextCtrl:undo()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:redo
^^^^^^^^^^^^^
	
	If there is a redo facility and the last operation can be redone, redoes the last operation.

	Does nothing if there is no redo facility. 

=======  ===========================================================================================
 void_ 	  TextCtrl:redo()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:appendText
^^^^^^^^^^^^^^^^^^^
	
	Appends the text to the end of the text control. 

    After the text is appended, the insertion point will be at the end of the text control. 
    If this behaviour is not desired, the programmer should use getInsertionPoint() and 
    setInsertionPoint().

=======  ===========================================================================================
 void_ 	  TextCtrl:appendText( string_ sText )
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:clear
^^^^^^^^^^^^^^
	
	Clears the text in the control.

	Note that this function will generate a wxEVT_TEXT event, i.e. its effect is identical to 
	calling wxObj:SetValue("").

=======  ===========================================================================================
 void_ 	  TextCtrl:appendText( string_ sText )
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:discardEdits
^^^^^^^^^^^^^^^^^^^^^
	
	Resets the internal modified flag as if the current changes had been saved.

=======  ===========================================================================================
 void_ 	  TextCtrl:discardEdits()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:markDirty
^^^^^^^^^^^^^^^^^^
	
	Mark text as modified (dirty).

=======  ===========================================================================================
 void_ 	  TextCtrl:markDirty()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:getInsertionPoint
^^^^^^^^^^^^^^^^^^^^^^^^^^
	
	Returns the insertion point. This is defined as the zero based index of the character position 
	to the right of the insertion point. For example, if the insertion point is at the end of the 
	text control, it is equal to both GetValue().Length() and GetLastPosition().

=========  =========================================================================================
 number_ 	TextCtrl:getInsertionPoint()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:getLastPosition
^^^^^^^^^^^^^^^^^^^^^^^^
	
	Returns the zero based index of the last position in the text control, which is equal to the 
	number of characters in the control.

=========  =========================================================================================
 number_ 	TextCtrl:getLastPosition()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:getRange
^^^^^^^^^^^^^^^^^
	
	Returns the string containing the text starting in the positions from and up to to in the control. 
	The positions must have been returned by another TextCtrl method.

	Please note that the positions in a multiline wxTextCtrl do not correspond to the indices in the 
	string returned by GetValue because of the different new line representations (CR or CR LF) and 
	so this method should be used to obtain the correct results instead of extracting parts of the 
	entire value. It may also be more efficient, especially if the control contains a lot of data.

=======  ===========================================================================================
 void_ 	  TextCtrl:getRange( nFrom, nTo )
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:setInsertionPoint
^^^^^^^^^^^^^^^^^^^^^^^^^^	
	
	Sets the insertion point at the given position.

=======  ===========================================================================================
 void_ 	  TextCtrl:setInsertionPoint()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:setInsertionPointEnd
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
	
	Sets the insertion point at the end of the text control. This is equivalent to 
	setInsertionPoint(getLastPosition()).

=======  ===========================================================================================
 void_ 	  TextCtrl:setInsertionPointEnd()
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:writeText
^^^^^^^^^^^^^^^^^^
	
	Writes the text into the text control at the current insertion position.
	
	*Remarks:

	Newlines in the text string are the only control characters allowed, and they will cause appropriate 
	line breaks. See wxTextCtrl::appendText for more convenient ways of writing to the window.
   
    After the write operation, the insertion point will be at the end of the inserted text, so 
	subsequent write operations will be appended. To append text after the user may have interacted 
	with the control, call wxTextCtrl::SetInsertionPointEnd before writing.*

=======  ===========================================================================================
 void_ 	  TextCtrl:writeText( string_ sText )
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


TextCtrl:showPosition
^^^^^^^^^^^^^^^^^^^^^
	
	Makes the line containing the given position visible.

=======  ===========================================================================================
 void_ 	  TextCtrl:showPosition( nPos )
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


Events
******

The following events are emitted by this class:

.. toctree::
    :hidden:
    
	classes/widget.onenter
    classes/widget.onleave
    
----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../types.rst