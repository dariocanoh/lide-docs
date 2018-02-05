lide.widgets
============

  These classes are loaded with ``lide.widgets`` into this module we 
  will find the necessary functions to build GUI Applications
  implemented in Lua.

  We can access this calling directly ``lide.widgets.?classname`` where 
  *?classname* is the class you searching.

  .. code-block:: lua

    lide = require 'lide.widgets.init'
    
    Form = lide.widgets.form
    Font = lide.widgets.font
    Button lide.widgets.button


.. toctree::
	:maxdepth: 1
	:caption: GUI Classes

	../classes/font
	../classes/color

	../classes/object
	../classes/event
	../classes/menu

	../classes/widget
	../classes/window
	../classes/form
	../classes/dialog
	
	../classes/panel
	../classes/toolbar
	
	../classes/control

	../classes/button
	../classes/label
	../classes/image
	../classes/listbox
	../classes/combobox
	../classes/progress
	../classes/calendar


.. toctree::
	:maxdepth: 1
	:caption: GUI Events

	../classes/widget.onenter
	../classes/widget.onleave
	../classes/widget.onkeydown
	../classes/widget.onkeyup
	../classes/button.onclick
	