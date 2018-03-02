.. /////// 2016/03/01 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/widgets/Form.rst
.. //  Class Form reference
.. //   (c) 2016 Hernan Dario Cano | GNU GENERAL PUBLIC LICENSE

.. _ClassForm:

Form
====
.. note::
  
  Form is derived from  Window_ class.

  A form is a window or screen that contains numerous controls, or fields to enter data. 

----------------------------------------------------------------------------------------------------

Constructor
***********

Form class has a complex constructor:

::

  Form:new { 
     string Name, string Title,
     
     number PosX  , number PosY,
     number Width , number Height,
  }


Arguments
^^^^^^^^^

These arguments are received by class constructor.

============  ======================================================================================
 Argument      Description
============  ======================================================================================
 Name          The form's name
 PosX          Position related to X on Screen or Parent object
 PosY          Position related to X on Screen or Parent object
 Width         Width of the form
 Height        Height of the form
============  ======================================================================================

----------------------------------------------------------------------------------------------------

Events
******

The following events are emitted by this class:

============================  =========================================================================
  Event name                    Description
============================  =========================================================================
 Form.onShow_                   When the form is shown.
 Form.onClose_                  When the form is closed.
============================  =========================================================================

----------------------------------------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.

----------------------------------------------------------------------------------------------------

Form:getFocusedObject
^^^^^^^^^^^^^^^^^^^^^

  Returns focused object.

=========  =========================================================================================
 object_    Form:getFocusedObject()
=========  =========================================================================================
 
----------------------------------------------------------------------------------------------------

Form:setFocusedObject
^^^^^^^^^^^^^^^^^^^^^

  Sets the focused object.

=========  =========================================================================================
 nil_       Form:setFocusedObject( Widget_ oDefault )
=========  =========================================================================================
 
----------------------------------------------------------------------------------------------------


Example
*******

In this example we create a new Form ...

.. code-block:: lua
   :linenos:
    
    myWnd = Form:new { Name = "MyForm",
    	
    	-- PosX = 30, PosY = 70, Width , Height, >> Here we don't send the size, for using default sizes

    	Title  = "YOUR NEW Form",
    }

    myWnd:show();

----------------------------------------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst
.. _Form.onShow:  Window.onShow_
.. _Form.onClose:  Window.onClose_