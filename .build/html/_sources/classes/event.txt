.. /////// 2015/01/08 - Dario Cano [thdkano@gmail.com]
.. // docs/classes/event.rst
.. //  Class Event reference
.. //   (c) 2015 Dario Cano | lide license

.. _ClassEvent:

Event
=====
.. note::

  Event is derived from :ref:`Object class<ClassObject>`.

An event is a structure holding information about an event passed to a callback or member function. 
Event is used to be a multipurpose event object, and is an abstract base class for other event classes.

----------------------------------------------------------------------------------------------------


Constructor
***********

Event class has a single constructor:


.. code-block:: c++

 object Event:new ( string sEventName, object oEventSender, function fDefEventHandler )


Arguments
^^^^^^^^^

These arguments are received by class constructor.

============  ======================================================================================
  Argument     Description
============  ======================================================================================
 sEvtName      The event name
 oEvtSender    The object associated to the event (usually is a derived of "Widget_")
 fEvtHandler   The event handler function (that is called when you call `Event:call`).
============  ======================================================================================

----------------------------------------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=================  =================================================================================
  Class Method       Description
=================  =================================================================================
 Object:getID_	    Returns event's identifier.
 Object:setID_	    Sets the event identifier.
 Object:getName_    Returns event's name.
 Object:setName_    Sets the event name.
=================  =================================================================================

----------------------------------------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


Event:getSender
^^^^^^^^^^^^^^^
   
   Gets the object associated to the event.

=========  =========================================================================================
 object_    Event:getSender()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Event:setSender
^^^^^^^^^^^^^^^
	
   Sets the object associated to the event.

=======  ============================================================================================
 bool_ 	  Event:setSender ( object oEvtSender )
=======  ============================================================================================

----------------------------------------------------------------------------------------------------


Event:getHandler
^^^^^^^^^^^^^^^^^
   
   Returns the event handler function (that is called when you call `Event:call`).

===========  =======================================================================================
 function_    Event:getHandler()
===========  =======================================================================================

----------------------------------------------------------------------------------------------------


Event:setHandler
^^^^^^^^^^^^^^^^
  
   Sets the event handler function.

=======  ===========================================================================================
 bool_    Event:setSender ( object oEvtSender )
=======  ===========================================================================================

----------------------------------------------------------------------------------------------------


Event:call
^^^^^^^^^^
  
   Calls the event handler and pass it all the args.

    *Returns one value: Returns first value what event handler sents.*

=====  =============================================================================================
 ...    Event:call ( ... )
=====  =============================================================================================

-----------------------------------------------------------------------------------------------------



.. // Required values for html docs visualization
.. include:: ../directives.rst