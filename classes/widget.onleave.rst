.. /////// 2016/02/07 - Dario Cano [thdkano@gmail.com]
.. // classes/widget.onleave.rst
.. //  Widget's event onLeave reference
.. //   (c) 2016 Dario Cano | lide license

.. _Widget.onLeave:

Widget.onLeave
^^^^^^^^^^^^^^ 

   This event will be performed when the mouse moves out to this widget ("leaves" the widget's territory).


----------------------------------------------------------------------------------------------------

Prototype
+++++++++

===========  =======================================================================================
 function_    onLeaveHandler ( object_ event )
===========  =======================================================================================      

----------------------------------------------------------------------------------------------------

Example
+++++++

This example prints the name of the widget when the mouse is out of it.

.. code-block:: lua
   :linenos:
   :emphasize-lines: 1,5

    local function onLeaveHandler ( this )
       print ( 'the cursor is out of the widget "'.. this:getSender():getName() ..'"' )
    end4

    myForm.onLeaveHandler:setHandler(onLeaveHandler)

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst