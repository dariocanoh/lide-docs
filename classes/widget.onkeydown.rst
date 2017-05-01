.. /////// 2016/02/07 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/widget.onkeydown.rst
.. //  Widget's event onKeyDown reference
.. //   (c) 2016 Hernan Dario Cano | GNU GENERAL PUBLIC LICENSE

Widget.onKeyDown
^^^^^^^^^^^^^^^^

   When any key has been pressed. 

   If this event is handled and not skipped, Widget.onKeyChar_ will not be 
   generated at all for this key press (but Widget.onKeyUp_ will be).

----------------------------------------------------------------------------------------------------

Prototype
+++++++++

===========  =======================================================================================
 function_    onKeyHandler ( object_ event, number_ nKeyCode )
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