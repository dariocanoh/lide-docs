.. /////// 2018/02/04 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/widgets/controls/label.rst
.. //  Class Label reference
.. //   (c) 2018 Hernan Dario Cano | lide license

.. _ClassLabel:

Label
======
.. note::

  Label is derived from Control_ class.

A static text control displays one or more lines of read-only text.

Label supports the three classic text alignments, label ellipsization i.e. replacing parts of the 
text with the ellipsis ("...") if the label doesn't fit into the provided space and also formatting 
markup with Label:SetLabelMarkup()

----------------------------------------------------------------------------------------------------


Constructor
***********

Label class has a complex constructor:


.. code-block:: lua

 object Label:new {
 		number ID, string Name,
 		object Parent, Text = 'My Label'
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

=====================  =============================================================================
  Class Method             Description
=====================  =============================================================================
  Object:getID_          Returns object's identifier.
  Object:setID_          Sets the object identifier.
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


Label:getText
^^^^^^^^^^^^^^
   
   Returns the Label's text, as it was passed to ``setText()``

   Note that the returned string may contains mnemonics ("&" characters) if they were passed to the 
   ``setText()`` function; use ``getText(false)`` if they are undesired.

   Also note that the returned string is always the string which was passed to ``setText()``.

   Reimplemented from wxWindow.

=========  =========================================================================================
 string_    Label:getText( bool_ bMnemonics = true )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Label:setText
^^^^^^^^^^^^^^
  
   Sets the control's label.

   All "&" characters in the label are special and indicate that the following character is a 
   mnemonic for this control and can be used to activate it from the keyboard (typically by using 
   Alt key in combination with it). To insert a literal ampersand character, you need to double it, 
   i.e. use "&&". If this behaviour is undesirable, use ``setText(text, false)`` instead.

=======  ===========================================================================================
 bool_    Label:setText( string_ sNewText, bMnemonics = true )
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst