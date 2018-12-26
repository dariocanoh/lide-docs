Welcome
=======

Lide is an object-oriented, high-level framework for implementing
desktop applications. Lide is based on wxWidgets so programs are 
crossplatform and operates good with GTK+ on GNU/Linux and Native
controls on Microsoft Windows.

Lide Framework supports inheritance, libraries and user-defined 
classes among other features.

With Lide you can create packages for lua libraries, manage packages, 
load packages and set private repositories to ensure apps stability.

Lide was influenced by npm, Python and JavaScript and is designed 
to target Windows and GNU/Linux operating systems.


Framework Documentation
=======================

If you are new to the concept of object oriented programming on Lua we
recommend you start with _an example desktop app_  written in Lide. 

When you are ready for more detail, we recommend you read the 
_“Lide by Example”_ and _“Lide in Depth”_ sections to learn the core 
concepts of the framework.

For further reading, try _the basics of lua_ and details of the 
_wxlua binding_.

.. hint::
  You can use _lide shell_ to execute lua scripts and can be your lua
  interpreter by default.

Contents
========

:ref:`Keyword Index <genindex>`

.. toctree::
   :maxdepth: 2

   introduction-to-smart-contracts.rst
   installing-solidity.rst
   solidity-by-example.rst
   solidity-in-depth.rst
   security-considerations.rst
   resources.rst
   using-the-compiler.rst
   metadata.rst
   abi-spec.rst
   yul.rst
   style-guide.rst
   common-patterns.rst
   bugs.rst
   contributing.rst
   frequently-asked-questions.rst
   lll.rst

Installation
============

* Make sure you have the lua5.1 interpreter and manager luarocks5.1 
packages installed on your machine.

============  ======================================================================================
 Platform      Installation
============  ======================================================================================
 Windows   	   Download `shell-installer_v0.2.exe <https://github.com/lidesdk/shell/releases/download/0.2/shell-installer-0.2.exe>`_.
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