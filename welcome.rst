Welcome
=======


Lide Framework is a library that allows you to create multiplatform graphical interfaces from Lua language.
Lide uses wxWidgets to build controls and windows, this ensures the integration of your applications 
with GTK + on Linux and really native controls in Windows.

Installation
============

* Make sure you have the lua5.1 interpreter and manager luarocks5.1 packages installed on your machine.

============  ======================================================================================
 Platform      Installation
============  ======================================================================================
 Windows   	   Download `shell-installer_v0.2.exe < https://github.com/lidesdk/shell/releases/download/0.2/shell-installer-0.2.exe>`_.
 Ubuntu        ``$ sudo apt-get install lua5.1 luarocks libwxgtk2.8``
 Archlinux	   ``# pacman -S lua5.1 luarocks5.1 wxgtk2.8``
============  ======================================================================================


How to use it
=============

* Create a file ``main.lua`` where you start the application.

.. code-block:: lua
	:linenos:

	local Form = lide.classes.widgets.form
	local MessageBox = lide.core.base.messagebox

	form1 = Form:new { Name = 'form1';
		Title = 'Window Caption'
	};

	button1 = Button:new { Name = 'button1', Parent = form1;
		PosX = 10, PosY = 30,
		Text = 'Click me!',
	};

	button1.onClick : setHandler ( function ( ... )
		MessageBox 'Hello world!'
	end );

	form1:show(true)

With the above code we are creating a new form and putting a button inside it
at position (10, 30), clicking inside the button a message "Hello World" is displayed.

* Run the file ``main.lua`` with the following command:

.. code-block:: bash
	
	$ lide main.lua

This is all you need to start building applications, **should be noted that these instructions work** 
similarly to Windows or GNU/Linux.