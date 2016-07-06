Bienvenido
==========

Lide Framework es una librería que le permite crear interfaces gráficas multiplataforma desde el lenguaje Lua. 
Lide utiliza wxWidgets para construir los controles y las ventanas, ésto asegura la integración de sus aplicaciones con GTK+ en Linux y controles realmente nativos en Windows.


Instalación
============

* Asegurese de tener instalado el interprete de lua5.1 y el gestor de paquetes luarocks5.1 en su máquina.

============  ======================================================================================
 Plataforma     Instalación
============  ======================================================================================
 Windows   	   Descargue `LuaForWindows_v5.1.4-33.exe <http://files.luaforge.net/releases/luaforwindows/luaforwindows/5.1.4-33/LuaForWindows_v5.1.4-33.exe>`_ y `luarocks-2.3.0-win32.zip <http://keplerproject.github.io/luarocks/releases/luarocks-2.3.0-win32.zip>`_.
 Ubuntu        ``$ sudo apt-get install lua5.1 luarocks libwxgtk2.8``
 Archlinux	   ``# pacman -S lua5.1 luarocks5.1 wxgtk2.8``
============  ======================================================================================


* Instalar la última versión de Lide desde LuaRocks:

.. code-block:: bash

	$ luarocks install https://raw.githubusercontent.com/thedary/lide-sdk/master/lide-0.0-0.rockspec


Cómo usarlo
===========

* Cree un archivo ``main.lua`` donde inicie la aplicación.

.. code-block:: lua
	:linenos:

	local Form = lide.classes.widgets.form
	local MessageBox = lide.core.base.messagebox

	form1 = Form:new { Name = 'form1',
		Title = 'Window Caption'
	};

	button1 = Button:new { Name = 'button1', Parent = form1,
		PosX = 10, PosY = 30,
		Text = 'Click me!',
	};

	button1.onClick : setHandler ( function ( ... )
		MessageBox 'Hello world!'
	end );

	form1:show(true)

Con el anterior código estamos creando un nuevo formulario y poniendo un botón dentro de él 
en la posición (10, 30), al hacer click dentro del botón se mostrará un mensaje "Hola mundo".

* Ejecute el archivo ``main.lua`` con el siguiente comando:

.. code-block:: bash
	
	$ lua5.1 -l lide.init main.lua

Esto es lo único que usted necesita para empezar a crear aplicaciones, **cabe resaltar que
éstas instrucciones funcionan** de igual manera para Windows o GNU/Linux.