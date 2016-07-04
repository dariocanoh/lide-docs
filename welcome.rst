Welcome
=======

Lide Framework es una librería que le permite crear interfaces gráficas multiplataforma desde el lenguaje Lua. Lide utiliza wxWidgets para construir los controles y las ventanas, ésto asegura la integración de sus aplicaciones con GTK+ en Linux y controles realmente nativos en Windows.


Installation
============

* Asegurese de tener instalado el interprete de lua5.1 en su máquina.
* Instalarla última versión desde luarocks:

.. code-block:: bash

	# luarocks-5.1 install http://lol.com/lide.rockspec´


Basic Usage
===========

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