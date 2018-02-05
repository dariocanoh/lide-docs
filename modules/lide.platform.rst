.. /////// 2017/08/07 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/modules/lide.platform.rst
.. //  Platform library reference
.. //   (c) 2017 Hernan Dario Cano - All rights reserved

.. _lide.platform:

lide.platform
============= 

   The platform library allows us to interact with basic aspects of the Operating System as the 
   architecture, version and the name of operating system that is being used. It is useful to identify 
   the current operating system in order to improve the convergence of our applications.

----------------------------------------------------------------------------------------------------

platform.get_osname
+++++++++++++++++++
      
	Gets the name of current Operating System.

=========  =========================================================================================
 string_    platform.get_osname()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------

platform.get_osarch
+++++++++++++++++++
      
	Gets the architecture of current Operating System.

=========  =========================================================================================
 string_    platform.get_osarch()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------

platform.get_osversion
++++++++++++++++++++++
      
	Gets the version of current Operating System.

=========  =========================================================================================
 string_    platform.get_osversion()
=========  =========================================================================================

----------------------------------------------------------------------------------------------------

.. // Required values for html docs visualization
.. include:: ../directives.rst