.. /////// 2018/11/23 - Dario Cano [dcanohdev@gmail.com]
.. // classes/widgets/controls/Checkbox.rst
.. //  Class Checkbox reference
.. //   (c) 2018 Hernan Dario Cano | lide license

.. _ClassCheckbox:

Checkbox
======

  Checkbox is derived from Control_ class.

  ``[lide.widgets] ^1.1`` ``lide.widgets.controls.checkbox 1.0``


A Checkbox is a control that contains a text string, and is one of the 
most common elements of a GUI.

----------------------------------------------------------------------


Constructor
***********

Checkbox class has a complex constructor:


.. code-block:: lua

 object Checkbox:new {
 		number ID, string Name,
 		object Parent, Text = 'My Checkbox'
 	}

Arguments
^^^^^^^^^

These arguments are received by class constructor.

============  ========================================================
  Argument     Description
============  ========================================================
 Name          The control name
 Parent        The control parent
 PosX          Position related to X
 PosY          Position related to Y
 Flags         Possible style modificators for Checkbox control:
              
               ============================================  ============  =========================================================================================================================================================================================================================
                constant                                      value          description
               ============================================  ============  =========================================================================================================================================================================================================================
                 ``Checkbox.CHK_2STATE``                       ``0``           Create a 2-state checkbox. This is the default.
                 ``Checkbox.CHK_3STATE``                       ``4096``        Create a 3-state checkbox. Not implemented in wxOS2 and wxGTK built against GTK+ 1.2.
                 ``Checkbox.CHK_ALLOW_3RD_STATE_FOR_USER``     ``8192``        By default a user can't set a 3-state checkbox to the third state. It can only be done from code. Using this flags allows the user to set the checkbox to the third state by clicking.
                 ``Checkbox.ALIGN_RIGHT``                      ``512``         Makes the text appear on the left of the checkbox
               ============================================  ============  =========================================================================================================================================================================================================================
============  ========================================================


----------------------------------------------------------------------

Events
******

The following events are emitted by this class:

===================  =================================================
  Event name           Description
===================  =================================================
 Widget.onEnter_        When the mouse moves onto this widget.
 Widget.onLeave_        When the mouse moves out to this widget.
 Checkbox.onClick_      When the user clicks on this Checkbox.
===================  =================================================

----------------------------------------------------------------------

Inherited Methods
*****************

These methods are inherited from its super classes:

=====================  ===============================================
  Class Method             Description
=====================  ===============================================
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
  Widget:getBind_        Returns the wxWidgets object.
=====================  ===============================================


Checkbox:getValue
^^^^^^^^^^^^^^^^^
   
   Gets the state of a 2-state checkbox.

   ** Returns: **
         Returns true if it is checked, false otherwise.

=========  ===========================================================
 bool_      Checkbox:getValue(  )
=========  ===========================================================

----------------------------------------------------------------------


Checkbox:get3StateValue
^^^^^^^^^^^^^^^^^^^^^^^
  
   Gets the state of a 3-state checkbox.

   Asserts when the function is used with a 2-state checkbox.

=======  =============================================================
 bool_    Checkbox:get3StateValue( )
=======  =============================================================

----------------------------------------------------------------------


Checkbox:is3rdStateAllowedForUser
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  
   Returns whether or not the user can set the checkbox to the third 
   state.

   ** Returns: **
         true if the user can set the third state of this checkbox, 
         false if it can only be set programmatically or if it's a 
         2-state checkbox.

=======  =============================================================
 bool_    Checkbox:is3rdStateAllowedForUser( )
=======  =============================================================

----------------------------------------------------------------------


Checkbox:is3State
^^^^^^^^^^^^^^^^^
  
   Returns whether or not the checkbox is a 3-state checkbox.

   ** Returns: **
         true if this checkbox is a 3-state checkbox, false if it's a 
         2-state checkbox.

=======  =============================================================
 bool_    Checkbox:is3State( )
=======  =============================================================

----------------------------------------------------------------------


Checkbox:isChecked
^^^^^^^^^^^^^^^^^^
  
   This is just a maybe more readable synonym for GetValue(): just as 
   the latter, it returns true if the checkbox is checked and false 
   otherwise.

=======  =============================================================
 bool_    Checkbox:isChecked( )
=======  =============================================================

----------------------------------------------------------------------


Checkbox:setValue
^^^^^^^^^^^^^^^^^
  
   Sets the checkbox to the given state.

   This does not cause a Checkbox.onClick_ event to get emitted.

   ** Parameters: **
         state If true, the check is on, otherwise it is off.


=======  =============================================================
 bool_    Checkbox:setValue( bool_ bState )
=======  =============================================================

----------------------------------------------------------------------


Checkbox:set3StateValue
^^^^^^^^^^^^^^^^^^^^^^^
  
   Sets the checkbox to the given state.

   This does not cause a Checkbox.onClick_ event to get emitted.

   Asserts when the checkbox is a 2-state checkbox and setting the 
   state to ``Checkbox.CHK_UNDETERMINED``.


=======  =============================================================
 bool_    Checkbox:set3StateValue( number_ nCheckBoxState )
=======  =============================================================

----------------------------------------------------------------------


.. // Required values for html docs visualization
.. include:: ../directives.rst