.. /////// 2016/02/25 - Dario Cano [thdkano@gmail.com]
.. // classes/widgets/controls/button.rst
.. //  Class Button reference
.. //   (c) 2016 Dario Cano | lide license

.. _ClassButton:

Button
======
.. note::

  Button is derived from Control_ class.

A Button is a control that contains a text string, and is one of the most common elements of a GUI.

----------------------------------------------------------------------------------------------------


Constructor
***********

Button class has a complex constructor:


.. code-block:: lua

 object Button:new {
 		number ID, string Name,
 		object Parent, Text = 'My Button'
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
 Button.onClick_             When the user clicks on this button.
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
  Control:getText_       Returns the button text.
  Control:setText_       Sets the button text.
=====================  =============================================================================

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst