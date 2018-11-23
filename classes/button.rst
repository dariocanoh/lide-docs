.. /////// 2016/02/25 - Dario Cano [thdkano@gmail.com]
.. // classes/widgets/controls/button.rst
.. //  Class Button reference
.. //   (c) 2016 Dario Cano | lide license

.. _ClassButton:

Button
======

  Button is derived from Control_ class.

  ``[lide.widgets] ^1.0`` ``lide.widgets.controls.button 1.0``

A Button is a control that contains a text string, and is one of the most common elements of a GUI.

----------------------------------------------------------------------


Constructor
***********

Button class has a complex constructor:


.. code-block:: lua

 object Button:new {
 		number ID, string Name,
 		object Parent, Text = 'My Button'
 	}

----------------------------------------------------------------------

Events
******

The following events are emitted by this class:

=========================  ===========================================
  Event name                Description
=========================  ===========================================
 Widget.onEnter_             When the mouse moves onto this widget.
 Widget.onLeave_             When the mouse moves out to this widget.
 Button.onClick_             When the user clicks on this button.
=========================  ===========================================

----------------------------------------------------------------------

Inherited Methods
*****************

These methods are inherited from its super classes:

=========================  ===========================================
  Class Method              Description
=========================  ===========================================
  Object:getID_             Returns object's identifier.
  Object:setID_             Sets the object identifier.
  Object:getName_           Returns object's name.
  Object:setName_           Sets the object name.
  Widget:getParent_         Returns object's parent.
  Widget:setParent_         Sets the object parent.
  Widget:getPosX_           Returns object's position related to X.
  Widget:setPosX_           Sets the object position related to X.
  Widget:getPosY_           Returns object's position related to Y.
  Widget:setPosY_           Sets the object position related to Y.
  Widget:getWidth_          Returns object's width.
  Widget:setWidth_          Sets the object width.
  Widget:getHeight_         Returns object's height.
  Widget:setHeight_         Sets the object height.
  Widget:getBind_           Returns the wxWidgets object.
=========================  ===========================================


Button:getText
^^^^^^^^^^^^^^
   
   Returns the button's text, as it was passed to ``setText()``

   Note that the returned string may contains mnemonics 
   ("&" characters) if they were passed to the ``setText()`` function; 
   use ``getText(false)`` if they are undesired.

   Also note that the returned string is always the string which was 
   passed to ``setText()``.

   Reimplemented from wxWindow.

=========================  ===========================================
 string_    Control:getText( bool_ bMnemonics = true )
=========================  ===========================================

----------------------------------------------------------------------


Button:setText
^^^^^^^^^^^^^^
  
   Sets the control's label.

   All "&" characters in the label are special and indicate that the 
   following character is a mnemonic for this control and can be used 
   to activate it from the keyboard (typically by using Alt key in 
   combination with it). To insert a literal ampersand character, you 
   need to double it, i.e. use "&&". If this behaviour is undesirable, 
   use ``setText(text, false)`` instead.

=========================  ===========================================
 bool_    Control:setText( string_ sNewText, bMnemonics = true )
=========================  ===========================================

----------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst