.. /////// 2017/05/20 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/widgets/Dialog.rst
.. //  Class Dialog reference
.. //   (c) 2017 Hernan Dario Cano | GNU GENERAL PUBLIC LICENSE

.. _ClassDialog:

Dialog
====
.. note::
  
  Dialog is derived from  :ref:`Window class <ClassWindow>`.

  A Dialog is a window or screen that contains numerous controls, or fields to enter data. 

----------------------------------------------------------------------------------------------------

Constructor
***********

Dialog class has a complex constructor:

.. code-block:: lua

   Dialog:new {
      string Name, string Title,
     
      number PosX  , number PosY,
      number Width , number Height,
  }


Arguments
^^^^^^^^^

These arguments are received by class constructor.

============  ======================================================================================
  Argument     Description
============  ======================================================================================
 Name          The object's name
 PosX          Position related to X
 PosY          Position related to Y
 Width         Width of the widget
 Height        Height of the widget
 Title         The caption of the dialog.
============  ======================================================================================

----------------------------------------------------------------------------------------------------

Class Methods
*************

These methods are defined by this class.

----------------------------------------------------------------------------------------------------

Dialog:showModal
^^^^^^^^^^^^^^^^

  Show modal Dialog.

======  ============================================================================================
 nil_    Dialog:showModal()
======  ============================================================================================
 
----------------------------------------------------------------------------------------------------


Example
*******

In this example we create a new Dialog ...

.. code-block:: lua
   :linenos:
   :emphasize-lines: 2,4,7,8
    
    myWnd = Dialog:new { Name = "MyDialog",
    	Title  = "YOUR NEW Dialog",
    }

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst