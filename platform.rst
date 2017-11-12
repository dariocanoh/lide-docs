.. /////// 2017/11/12 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/platform.rst
.. //  lide.platform reference
.. //   (c) 2016-2017 Hernan Dario Cano | Lide License

.. _lide_platform:

lide.platform
=============
  
  ``[lide.core] ^0.01``

  Into the ``lide.platform`` module we will find the necessary functions to interact with
  the operating system of the machine and its fundamental aspects.

  .. code-block:: lua
   
   print('os platform: ' .. lide.platform.getOS())
   print('os version : ' .. lide.platform.getOSVersion())
   print('os arch    : ' .. lide.platform.getArch())

----------------------------------------------------------------------------------------------------


platform.getArch
^^^^^^^^^^^^^^^^
   
   Gets the operating system architecture that is currently running.

    **Returns:** A string that can be ``x86`` or ``x64``


==========  ========================================================================================
 string_     lide.platform.getArch()
==========  ========================================================================================

----------------------------------------------------------------------------------------------------


platform.getOS
^^^^^^^^^^^^^^
  
   Gets the operating system that is currently running.

   **Retorna:** Un string que puede ser ``windows`` o ``linux``.


=========  =========================================================================================
 string_    lide.platform.getOS()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


platform.getOSVersion
^^^^^^^^^^^^^^^^^^^^^
	
   Get the version of the operating system that we are currently running.

=========  =========================================================================================
 string_ 	  lide.platform.getOSVersion()
=========  =========================================================================================



.. // Required values for html docs visualization
.. include:: ./directives.rst