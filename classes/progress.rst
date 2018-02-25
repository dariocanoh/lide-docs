.. /////// 2016/02/25 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/widgets/controls/progress.rst
.. //  Class Progress reference
.. //   (c) 2016 Dario Cano | lide license

.. _ClassProgress:

Progress
========

.. note::

  Progress is derived from Control_ class.

A Progress object is a control that contains a progress bar to display the percentage of any work.

----------------------------------------------------------------------------------------------------


Constructor
***********

Progress class has a complex constructor:


.. code-block:: lua

 object Progress:new {
 		string Name, object Parent
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


Progress:setCurrentPos
^^^^^^^^^^^^^^^^^^^^^^
   
   This method helps to set the current position of the progress bar.
   
=========  =========================================================================================
 bool_       Progress:setCurrentPos ( number_ nPercent )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Progress:getCurrentPos
^^^^^^^^^^^^^^^^^^^^^^
  
   Gets the current position of progress bar.

=========  =========================================================================================
 number_    Progress:setCurrentPos( number_ nPosition )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------

Progress:isVertical
^^^^^^^^^^^^^^^^^^^



.. // Required values for html docs visualization
.. include:: ../directives.rst