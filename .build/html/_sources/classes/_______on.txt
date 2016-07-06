.. /////// 2016/02/25 - Dario Cano [thdkano@gmail.com]
.. // classes/widgets/button.rst
.. //  Class Button reference
.. //   (c) 2016 Dario Cano | lide license

.. _ClassButton:

Button
======

A button is a control that contains a text string, and is one of the most common elements of a GUI.

----------------------------------------------------------------------------------------------------


Constructor
***********

Button class has a complex constructor:


.. code-block:: lua

 object Button:new {
 		number ID, string Name,
 		object Parent, Text = 'My Button'
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