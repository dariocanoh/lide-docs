.. /////// Hernan Dario Cano [dcanohdev@gmail.com]
.. // classes/widgets/Window.onclose.rst
.. //  Reference to onclose event of Window class.
.. //   (c) 2018 Hernan Dario Cano | Lide Framework License

.. _Window_onClose:

Window.onclose
^^^^^^^^^^^^^^ 

An event being sent when the user has tried to close a a frame or dialog box using the window 
manager (X) or system menu (Windows). It can also be invoked by the application itself 
programmatically, for example by calling the ``Window:close`` function.

 	You should check whether the application is forcing the deletion of the window using 
 	``CloseEvent:canVeto``. If this is ``false``, you must destroy the window using ``Window:destroy``. 
 	If the return value is ``true``, it is up to you whether you respond by destroying the window.

	If you don't destroy the window, you should call ``CloseEvent:veto`` to let the calling code 
	know that you did not destroy the window. This allows the ``Window:close`` function to return 
	``true`` or ``false`` depending on whether the close instruction was honoured or not.

----------------------------------------------------------------------------------------------------

Prototype
+++++++++
      
============ =======================================================================================
 function_    onCloseHandler ( object_ event )
============ =======================================================================================

----------------------------------------------------------------------------------------------------

Example
+++++++

This example prints the name of the Window when it's shown.

.. code-block:: lua
   :linenos:
   :emphasize-lines: 1,5

    local function onShowHandler ( CloseEvent )
       print ( 'the Window is "'.. CloseEvent:getSender():getName() ..'"' )
    end

    myWindow.onEnter : setHandler(onEnterHandler)

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst