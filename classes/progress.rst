.. /////// 2016/02/25 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/widgets/controls/progress.rst
.. //  Class Progress reference
.. //   (c) 2016 Dario Cano | lide license

.. _ClassProgress:

Progress
========

.. note::

  Progress is derived from Control_ class.

 A Progress is a horizontal or vertical bar which shows a quantity (often time).

Progressbar supports two working modes: determinate and indeterminate progress.

The first is the usual working mode (see ``setCurrentPos`` and ``setMaxValue``) while the second can 
be used when the program is doing some processing but you don't know how much progress is being done. 
In this case, you can periodically call the Pulse function to make the progressbar switch to 
indeterminate mode (graphically it's usually a set of blocks which move or bounce in the bar control).

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
   
   This method helps to set the current position of the progress bar. This function makes the 
   progressbar switch to determinate mode, if it's not already.
   
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
  
    Returns true if the progressbar is vertical and false otherwise.

===========  =======================================================================================
 boolean_      Progress:isVertical()
===========  =======================================================================================

----------------------------------------------------------------------------------------------------


Progress:setMaxValue
^^^^^^^^^^^^^^^^^^^^
  
  Sets the range (maximum value) of the progressbar. This function makes the progressbar switch to 
  determinate mode, if it's not already.

===========  =======================================================================================
 nil_          Progress:setMaxValue( number_ nMaxValue )
===========  =======================================================================================

----------------------------------------------------------------------------------------------------


Progress:pulse
^^^^^^^^^^^^^^
  
  Switch the progressbar to indeterminate mode (if required) and makes the progressbar move a bit 
  to indicate the user that some progress has been made.

  *Note that after calling this function the value returned by ``getCurrentPos`` is undefined and 
  thus you need to explicitely call ``setCurrentPos`` if you want to restore the determinate mode.*

===========  =======================================================================================
 nil_          Progress:pulse( )
===========  =======================================================================================

----------------------------------------------------------------------------------------------------


Progress:getMaxValue
^^^^^^^^^^^^^^^^^^^^
  
  Returns the maximum position of the progressbar.

==========  ========================================================================================
 number_      Progress:getMaxValue( )
==========  ========================================================================================

----------------------------------------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst