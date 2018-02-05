.. /////// 2015/06/15 - Dario Cano [thdkano@gmail.com]
.. // docs/directives.rst
.. //  ...
.. //   (c) 2015 Dario Cano | lide license

.. _Event:    ../classes/event.html
.. _EventREF: ../classes/event_reference.html

.. _void:     ../types.html # nil-type
.. _nil:      ../types.html # nil-type
.. _object:   ../types.html # object-type
.. _function: ../types.html # function-type
.. _string:   ../types.html # string-type
.. _userdata: ../types.html # userdata-type
.. _table:    ../types.html # table-type
.. _number:   ../types.html # number-type
.. _bool:     ../types.html # boolean-type


.. // _Object:   ../classes/object.html
.. _Font:  	  ../classes/font.html
.. _Widget:   ../classes/widget.html
.. _Control:  ../classes/control.html
.. _TextCtrl: ../classes/textctrl.html


.. // Common GUI 

.. // window_class_directives.rst:

.. _Window: ../classes/window.html
.. _Window.onShow:   ../classes/window.onshow.html
.. _Window.onClose:  ../classes/window.onclose.html

.. //////////////////////////////

.. _Button:   ../classes/button.html
.. _Label:    ..classes/label.html
.. _Image:    ..classes/image.html
.. _Listbox:  ..classes/listbox.html
.. _Combobox: ..classes/combobox.html
.. _Progress: ..classes/progress.html
.. _Calendar: ..classes/calendar.html

.. // Define events:

.. _Widget.onEnter:    ../classes/widget.onenter.html
.. _Widget.onLeave:    ../classes/widget.onleave.html
.. _Widget.onKeyDown:  ../classes/widget.onkeydown.html

.. _Button.onClick:	 ../classes/button.onclick.html


.. // Define virtual methods:

.. _Object:getID: ../classes/object.html # object-getid
.. _Object:setID: ../classes/object.html # object-setid
.. _Object:getName: ../classes/object.html # object-getname
.. _Object:setName: ../classes/object.html # object-setname

.. // class widget:

.. _Widget:getParent:    ../classes/widget.html # widget-getparent  
.. _Widget:setParent:    ../classes/widget.html # widget-setparent
.. _Widget:getPosX:      ../classes/widget.html # widget-getposx
.. _Widget:setPosX:      ../classes/widget.html # widget-setposx
.. _Widget:getPosY:      ../classes/widget.html # widget-getposy
.. _Widget:setPosY:      ../classes/widget.html # widget-setposy
.. _Widget:getWidth:     ../classes/widget.html # widget-getwidth
.. _Widget:setWidth:     ../classes/widget.html # widget-setwidth
.. _Widget:getHeight:    ../classes/widget.html # widget-getheight
.. _Widget:setHeight:    ../classes/widget.html # widget-setheight  
.. _Widget:getwxObj:     ../classes/widget.html # widget-getwxobj
.. _Widget:getEnabled:   ../classes/widget.html # widget-getenabled
.. _Widget:setEnabled:   ../classes/widget.html # widget-setenabled   
.. _Widget:getVisible:   ../classes/widget.html # widget-getvisible   
.. _Widget:setVisible:   ../classes/widget.html # widget-setvisible      

.. _Control:getText: ../classes/control.html # control-gettext
.. _Control:setText: ../classes/control.html # control-settext
.. _Control:getFont: ../classes/control.html # control-getfont
.. _Control:setFont: ../classes/control.html # control-setfont

.. _TextCtrl:saveFile:				../classes/textctrl.html # textctrl-savefile
.. _TextCtrl:loadFile:				../classes/textctrl.html # textctrl-loadfile
.. _TextCtrl:replace:				../classes/textctrl.html # textctrl-replace
.. _TextCtrl:remove:				../classes/textctrl.html # textctrl-remove
.. _TextCtrl:positionToXY:				../classes/textctrl.html # textctrl-positiontoxy
.. _TextCtrl:xyToPosition:				../classes/textctrl.html # textctrl-xytoposition
.. _TextCtrl:getSelection:				../classes/textctrl.html # textctrl-getselection
.. _TextCtrl:getStringSelection:				../classes/textctrl.html # textctrl-getstringselection
.. _TextCtrl:getLineLength:				../classes/textctrl.html # textctrl-getlinelength
.. _TextCtrl:getLineText:				../classes/textctrl.html # textctrl-getlinetext
.. _TextCtrl:getNumberOfLines:				../classes/textctrl.html # textctrl-getnumberoflines
.. _TextCtrl:isEditable:				../classes/textctrl.html # textctrl-iseditable
.. _TextCtrl:isModified:				../classes/textctrl.html # textctrl-ismodified
.. _TextCtrl:isMultiline:				../classes/textctrl.html # textctrl-ismultiline
.. _TextCtrl:setMaxLength:				../classes/textctrl.html # textctrl-setmaxlength
.. _TextCtrl:setSelection:				../classes/textctrl.html # textctrl-setselection
.. _TextCtrl:setEditable:				../classes/textctrl.html # textctrl-seteditable
.. _TextCtrl:canCut:				../classes/textctrl.html # textctrl-cancut
.. _TextCtrl:canCopy:				../classes/textctrl.html # textctrl-cancopy
.. _TextCtrl:canPaste:				../classes/textctrl.html # textctrl-canpaste
.. _TextCtrl:canUndo:				../classes/textctrl.html # textctrl-canundo
.. _TextCtrl:canRedo:				../classes/textctrl.html # textctrl-canredo
.. _TextCtrl:cutToClipboard:				../classes/textctrl.html # textctrl-cuttoclipboard
.. _TextCtrl:copyToClipboard:				../classes/textctrl.html # textctrl-copytoclipboard
.. _TextCtrl:pasteFromClipboard:				../classes/textctrl.html # textctrl-pastefromclipboard
.. _TextCtrl:undo:				../classes/textctrl.html # textctrl-undo
.. _TextCtrl:redo:				../classes/textctrl.html # textctrl-redo
.. _TextCtrl:appendText:				../classes/textctrl.html # textctrl-appendtext
.. _TextCtrl:clear:				../classes/textctrl.html # textctrl-clear
.. _TextCtrl:markDirty:				../classes/textctrl.html # textctrl-markdirty
.. _TextCtrl:discardEdits:				../classes/textctrl.html # textctrl-discardedits
.. _TextCtrl:getInsertionPoint:				../classes/textctrl.html # textctrl-getinsertionpoint
.. _TextCtrl:getLastPosition:				../classes/textctrl.html # textctrl-getlastposition
.. _TextCtrl:getRange:				../classes/textctrl.html # textctrl-getrange
.. _TextCtrl:setInsertionPoint:				../classes/textctrl.html # textctrl-setinsertionpoint
.. _TextCtrl:setInsertionPointEnd:				../classes/textctrl.html # textctrl-setinsertionpointend
.. _TextCtrl:writeText:				../classes/textctrl.html # textctrl-writetext
.. _TextCtrl:showPosition:				../classes/textctrl.html # textctrl-showposition