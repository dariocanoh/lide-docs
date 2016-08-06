.. /////// 2016/01/10 - Dario Cano [thdkano@gmail.com]
.. // classes/widgets/panel.rst
.. //  Class Panel reference
.. //   (c) 2015 Dario Cano | lide license

.. _ClassPanel:

Panel
=====

A panel is a widget on which controls are placed. It is usually placed within a Form. It contains 
minimal extra functionality over and above its parent class Window; its main purpose is to be 
similar in appearance and functionality to a Dialog, but with the flexibility of having any window 
as a parent.

----------------------------------------------------------------------------------------------------


Constructor
***********

Panel class has a complex constructor:


.. code-block:: lua

 object Panel:new {
 		number ID, string Name,
 		object Parent, 
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
 Widget:getwxObj	   :ref:`Widget class <ClassWidget>`    Returns a reference to the C++ object.
 Widget:getEnabled     :ref:`Widget class <ClassWidget>`    Returns true if is enabled.
 Widget:setEnabled     :ref:`Widget class <ClassWidget>`    Set widget enabled or disabled.
 Widget:getVisible     :ref:`Widget class <ClassWidget>`    Returns the widget visibility.
 Widget:setVisible     :ref:`Widget class <ClassWidget>`    Returns the widget visibility.
=====================  ==================================  =========================================

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
.. include:: ../directives.rst