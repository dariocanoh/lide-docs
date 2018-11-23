.. /////// 2016/02/07 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/checkbox.onclick.rst
.. //  Reference to onClick event of checkbox class.
.. //   (c) 2016 Hernan Dario Cano | Lide Framework License

.. _checkbox.onClick:

Checkbox.onClick
^^^^^^^^^^^^^^ 

	``wxEVT_COMMAND_CHECKBOX_CLICKED``

	When the user clicks on this checkbox.


----------------------------------------------------------------------

Prototype
+++++++++
      
===========  =========================================================
 function_    onClickHandler ( object_ event, boolean_ isCheked )
===========  =========================================================

----------------------------------------------------------------------

Example
+++++++

This example prints the name of the checkbox when the user click.

.. code-block:: lua
   :linenos:

    local function onClickHandler ( this,  isChecked )
       print ( 'the click is on the checkbox "'.. this:getSender():getName() ..'"' )
    end

    mycheckbox.onEnter:setHandler(onEnterHandler)

----------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst