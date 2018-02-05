.. /////// 2018/02/06 - Hernan Dario Cano | [dcanohdev@gmail.com]
.. // docs/classes/Timer.rst
.. //  Class Timer reference
.. //   (c) 2018 Hernan Dario Cano | lide license

.. _ClassTimer:

Timer
======

::

   lide.widgets.timer

The Timer class allows you to execute code at specified intervals.

Its precision is platform-dependent, but in general will not be better than 1ms nor worse than 1s.

Start the timer with Timer:start() after constructing it before it actually starts sending 
notifications. It can be stopped later with Timer:stop()

*Note: A timer can only be used from the main thread*

----------------------------------------------------------------------------------------------------

Constructor
***********

Timer class has a single constructor:


.. code-block:: lua

   Timer:new ( number nTimerID, function fTimerHandler )


Arguments
^^^^^^^^^

These arguments are received by class constructor.

===============  ===================================================================================
 Argument         Description
===============  ===================================================================================
 nTimerID         The Timer identificator
 fTimerHandler    The Timer name
===============  ===================================================================================

----------------------------------------------------------------------------------------------------

Class Methods
*************

These methods are defined by this class.

----------------------------------------------------------------------------------------------------

Timer:start
^^^^^^^^^^^
   
    Start or restarts the timer. If milliseconds parameter is ``-1`` (value by default), the 
    previous value is used. Returns false if the timer could not be started, true otherwise (in MS 
    Windows timers are a limited resource).

    If oneShot is false (the default), the Notify function will be called repeatedly until the 
    timer is stopped. If ``true``, it will be called only once and the timer will stop automatically. 
    To make your code more readable you may also use the following symbolic constants:

    ==============================  ===============================================
     ``TIMER_CONTINUOUS = false``    Start a normal, continuously running, timer
     ``TIMER_ONE_SHOT   = true``     Start a one shot timer
    ==============================  ===============================================
   If the timer was already running, it will be stopped by this method before restarting it.

=========  =========================================================================================
 number_ 	Timer:start( number_ nMilliseconds, bool_ bOneshot )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------

Timer:stop
^^^^^^^^^^
   
   Stops the timer.

=======  =========================================================================================
 void_ 	  Timer:stop()
=======  =========================================================================================

----------------------------------------------------------------------------------------------------

Timer:getInterval
^^^^^^^^^^^^^^^^^
   
   Returns the current interval for the timer (in milliseconds).

=========  =========================================================================================
 number_ 	Timer:getInterval()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------

Timer:isOneShot
^^^^^^^^^^^^^^^
   
   Returns ``true`` if the timer is one shot, i.e. if it will stop after firing the first notification 
   automatically.

=======  =========================================================================================
 bool_	  Timer:isOneShot()
=======  =========================================================================================

----------------------------------------------------------------------------------------------------

Timer:isRunning
^^^^^^^^^^^^^^^
   
   Returns ``true`` if the timer is running, ``false`` if it is stopped.

=======  =========================================================================================
 bool_	  Timer:isRunning()
=======  =========================================================================================

----------------------------------------------------------------------------------------------------


.. // Required values for html docs visualization
.. include:: ../directives.rst