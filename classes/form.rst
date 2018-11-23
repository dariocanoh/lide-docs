.. /////// 2016/03/01 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/widgets/Form.rst
.. //  Class Form reference
.. //   (c) 2016 Hernan Dario Cano | GNU GENERAL PUBLIC LICENSE

.. _ClassForm:

Form
====
 
  Form is derived from  Window_ class.

  ``[lide.base] ^1.0`` ``lide.classes.file 1.0``


  A form is a window or screen that contains numerous controls, or 
  fields to enter data. 

----------------------------------------------------------------------

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

============  ========================================================
 Argument      Description
============  ========================================================
 Name          The form's name
 PosX          Position related to X on Screen or Parent object
 PosY          Position related to X on Screen or Parent object
 Width         Width of the form
 Height        Height of the form
============  ========================================================

----------------------------------------------------------------------

Events
******

The following events are emitted by this class:

============================  ========================================
  Event name                    Description
============================  ========================================
 Form.onShow_                   When the form is shown.
 Form.onClose_                  When the form is closed.
============================  ========================================

----------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.

=====================  ===============================================
  Class Method            Description
=====================  ===============================================
 Object:getID_           Returns widget's identifier.
 Object:setID_           Sets the widget identifier.
 Object:getName_         Returns widget's name.
 Object:setName_         Sets the widget name.
 Widget:getParent_       Returns control's parent.
 Widget:setParent_       Sets the control parent.
 Widget:getPosX_         Returns control's position related to X.
 Widget:setPosX_         Sets the control position related to X.
 Widget:getPosY_         Returns control's position related to Y.
 Widget:setPosY_         Sets the control position related to Y.
 Widget:getWidth_        Returns control's width.
 Widget:setWidth_        Sets the control width.
 Widget:getHeight_       Returns control's height.
 Widget:setHeight_       Sets the control height.
 Widget:getBind_         Returns a reference to the C++ control.
 Widget:getEnabled_      Returns true if is enabled.
 Widget:setEnabled_      Set control enabled or disabled.
 Widget:getVisible_      Returns the control visibility.
 Widget:setVisible_      Returns the control visibility.
 Window:show_            Shows the Window.
 Window:centre_          Centers the window on the display.
=====================  ===============================================

----------------------------------------------------------------------

Form:getFocusedObject
^^^^^^^^^^^^^^^^^^^^^

  Returns focused object.

=========  ===========================================================
 object_    Form:getFocusedObject()
=========  ===========================================================
 
----------------------------------------------------------------------

Form:setFocusedObject
^^^^^^^^^^^^^^^^^^^^^

  Sets the focused object.

=========  ===========================================================
 nil_       Form:setFocusedObject( Widget_ oDefault )
=========  ===========================================================
 
----------------------------------------------------------------------


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

----------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst
.. _Form.onShow:  Window.onShow_
.. _Form.onClose:  Window.onClose_