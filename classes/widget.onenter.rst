.. /////// 2016/02/07 - Dario Cano [thdkano@gmail.com]
.. // classes/widget.onenter.rst
.. //  Widget's event onEnter reference
.. //   (c) 2015 Dario Cano | lide license

.. _Widget.onEnter:
Widget.onEnter
^^^^^^^^^^^^^^ 

   This event will be performed when the mouse moves onto this widget ("enters" the widget's territory).


----------------------------------------------------------------------------------------------------

Prototype
+++++++++
      
===========  =======================================================================================
 function_    onEnterHandler ( object_ event )
===========  =======================================================================================

See :ref:`Event reference<EventREF>` for more info of Event prototying and referencing

----------------------------------------------------------------------------------------------------

Example
+++++++

This example prints the name of the widget when the mouse is on it.

.. code-block:: lua
   :linenos:
   :emphasize-lines: 1,5

    local function onEnterHandler ( this )
       print ( 'the cursor is on the widget "'.. this:getSender():getName() ..'"' )
    end

    myForm.onEnter:setHandler(onEnterHandler)

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst