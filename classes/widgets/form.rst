.. /////// 2016/03/01 - Dario Cano [thdkano@gmail.com]
.. // classes/widgets/Form.rst
.. //  Class Form reference
.. //   (c) 2016 Dario Cano | lide license

.. _ClassForm:

Form
====
.. note::
  
  Form is derived from  :ref:`Window class <ClassWindow>`.

  A form is a window or screen that contains numerous controls, or fields to enter data. 

----------------------------------------------------------------------------------------------------

Constructor
***********

Form class has a complex constructor:

::

  Form:new {
     number ID, string Name, 
     
     number PosX  , number PosY,
     number Width , number Height,
  }


Arguments
^^^^^^^^^

These arguments are received by class constructor.

============  ======================================================================================
  Argument     Description
============  ======================================================================================
 ID            The object identificator 
 Name          The object's name
 PosX          Position related to X
 PosY          Position related to Y
 Width         Width of the widget
 Height        Height of the widget
============  ======================================================================================

----------------------------------------------------------------------------------------------------

Class Methods
*************

These methods are defined by this class.

----------------------------------------------------------------------------------------------------

xxxx
^^^^^^^^^^^^^

  xxxxx

======  ============================================================================================
 nil_    xxxxxx
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------


Events
******

The following events are emitted by this class:

==============================  ====================================================================
  Event name                      Description
==============================  ====================================================================
 :ref:`Widget_onEnter`           When the mouse moves onto this widget
 :ref:`Widget_onLeave`	         When the mouse leaves the widget
 :ref:`Window_onShow`            When the Window is shown.
==============================  ====================================================================

----------------------------------------------------------------------------------------------------

Example
*******

In this example we create a new Form ...

.. code-block:: lua
   :linenos:
   :emphasize-lines: 2,4,7,8
    
    myWnd = Form:new {
    	ID = 100, Name = "MyForm",
    	
    	-- PosX = 30, PosY = 70, Width , Height, >> Here we don't send the size, for using default sizes

    	Title  = "YOUR NEW Form",
    }

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../types.rst