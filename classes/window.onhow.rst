.. /////// 07/02/2016 - Dario Cano [thdkano@gmail.com]
.. // classes/widgets/Window.onShow.rst
.. //  Reference to onShow event of Window class.
.. //   (c) 2015 Dario Cano | lide license

.. _Window_onShow:

Window.onShow
^^^^^^^^^^^^^^ 

An event being sent when the window is shown or hidden. Notice that the event is not triggered when 
the application is iconized (minimized) or restored under Windows.


----------------------------------------------------------------------------------------------------

Prototype
+++++++++
      
============ =======================================================================================
 function_    onShowHandler ( object_ event, bool_ IsShown )
============ =======================================================================================

----------------------------------------------------------------------------------------------------

Example
+++++++

This example prints the name of the Window when it's shown.

.. code-block:: lua
   :linenos:
   :emphasize-lines: 1,5

    local function onShowHandler ( this )
       print ( 'the Window is "'.. this:getSender():getName() ..'"' )
    end

    myWindow.onEnter : setHandler(onEnterHandler)

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst