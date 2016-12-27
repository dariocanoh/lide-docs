.. /////// 2016/12/25 - Hernán Darío Cano [thdkano@gmail.com]
.. // docs/classes/widget.rst
.. //  lide.platform reference
.. //   (c) 2016 Hernán Darío Cano | lide license

.. _lide_platform:

lide.platform
=============

  En el módulo platform del framework encontraremos las funciones necesarias para interactuar con
  el sistema operativo de la maquina y sus aspectos fundamentales.

  .. code-block:: lua
   
   print('os platform: ' .. lide.platform.getOS())
   print('os version : ' .. lide.platform.getOSVersion())
   print('os arch    : ' .. lide.platform.getArch())

----------------------------------------------------------------------------------------------------


platform.getArch
^^^^^^^^^^^^^^^^
   
   Obtiene la arquitectura del sistema operativo que se esta ejecutando actualmente.

    **Retorna:** Un string que puede ser ``x86`` o ``x64``.


==========  ========================================================================================
 string_     platform.getArch()
==========  ========================================================================================

----------------------------------------------------------------------------------------------------


platform.getOS
^^^^^^^^^^^^^^
  
   Obtiene el sistema operativo que se está ejecutando actualmente.

   **Retorna:** Un string que puede ser ``Windows`` o ``Linux``.


=========  =========================================================================================
 string_    platform.getOS()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


platform.getOSVersion
^^^^^^^^^^^^^^^^^^^^^
	
   Obtiene la version del sistema operativo que estamos ejectuando actualmente.


=========  =========================================================================================
 string_ 	  platform.getOSVersion()
=========  =========================================================================================



.. // Required values for html docs visualization
.. include:: ./directives.rst