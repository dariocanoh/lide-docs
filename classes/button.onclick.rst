.. /////// 2016/02/07 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/button.onclick.rst
.. //  Reference to onClick event of Button class.
.. //   (c) 2015 Hernan Dario Cano | lide license

.. _Button.onClick:

Button.onClick
^^^^^^^^^^^^^^ 

	When the user clicks on this button.


----------------------------------------------------------------------------------------------------

Prototype
+++++++++
      
===========  =======================================================================================
 function_    onClickHandler ( object_ event )
===========  =======================================================================================

----------------------------------------------------------------------------------------------------

Example
+++++++

This example prints the name of the button when the user click.

.. code-block:: lua
   :linenos:
   :emphasize-lines: 1,5

    local function onClickHandler ( this )
       print ( 'the click is on the button "'.. this:getSender():getName() ..'"' )
    end

    myButton.onEnter : setHandler(onEnterHandler)

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst