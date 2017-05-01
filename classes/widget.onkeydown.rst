.. /////// 2016/02/07 - Dario Cano [thdkano@gmail.com]
.. // classes/widget.onleave.rst
.. //  Widget's event onLeave reference
.. //   (c) 2016 Dario Cano | lide license

Widget.onKeyDown
^^^^^^^^^^^^^^^^

   When any key has been pressed. If this event is handled and not skipped, onKeyChar will not be 
   generated at all for this key press (but onKeyUp will be).

----------------------------------------------------------------------------------------------------

Prototype
+++++++++

===========  =======================================================================================
 function_    onKeyHandler ( object_ event, nKeyCode )
===========  =======================================================================================      

See :ref:`Event reference<EventREF>` for more info of Event prototying and referencing

----------------------------------------------------------------------------------------------------

Example
+++++++

This example prints the name of the widget when the mouse is out of it.

.. code-block:: lua
   :linenos:
   :emphasize-lines: 1,5

    local function onKeyHandler ( this, nKeyCode )
       print ( 'key pressed: ' .. nKeyCode )
    end4

    myForm.onKeyDown:setHandler(onKeyHandler)

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst