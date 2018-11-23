.. /////// 14/06/2015 - Dario Cano [dcanohdev@gmail.com]
.. // classes/control.rst
.. //  Class Control reference
.. //   (c) 2015 Dario Cano | lide license

.. _ClassControl:

Control
=======

  Control is derived from Widget_ class.
  
  ``[lide.widgets] ^1.0`` ``lide.classes.controls 1.0``


This class is an abstract base class for objects called controls. The 
purpose is to define properties and methods shared for derivated 
classes. 

----------------------------------------------------------------------


Constructor
***********

Control class has a single constructor:


.. code-block:: lua

 Control:new ( string sControlName, object oParent, number nPosX, number nPosY, number nWidth, number nHeight, number nID )


Arguments
^^^^^^^^^

These arguments are received by class constructor.

==============  ======================================================
  Argument       Description
==============  ======================================================
 sControlName    The control name
 oParent         The control parent
 nPosX           Position related to X
 nPosY           Position related to Y
 nWidth          Width of the control
 nHeight         Height of the control
 nID             The object identificator 
==============  ======================================================


----------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=====================  ===============================================
  Class Method          Description
=====================  ===============================================
 Object:getID_		       Returns control's identifier.
 Object:setID_		       Sets the control identifier.
 Object:getName_	       Returns control's name.
 Object:setName_	       Sets the control name.
 Widget:getParent_	     Returns control's parent.
 Widget:setParent_	     Sets the control parent.
 Widget:getPosX_	       Returns control's position related to X.
 Widget:setPosX_	       Sets the control position related to X.
 Widget:getPosY_	       Returns control's position related to Y.
 Widget:setPosY_	       Sets the control position related to Y.
 Widget:getWidth_	       Returns control's width.
 Widget:setWidth_	       Sets the control width.
 Widget:getHeight_	     Returns control's height.
 Widget:setHeight_	     Sets the control height.
 Widget:getBind_	       Returns a reference to the C++ control.
 Widget:getEnabled_      Returns true if is enabled.
 Widget:setEnabled_      Set control enabled or disabled.
 Widget:getVisible_      Returns the control visibility.
 Widget:setVisible_      Returns the control visibility.
=====================  ===============================================

----------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


Control:getText
^^^^^^^^^^^^^^^
   
   Returns the control text.

=========  ===========================================================
 string_    Control:getText( bool_ bMnemonics )
=========  ===========================================================

----------------------------------------------------------------------


Control:setText
^^^^^^^^^^^^^^^
	
   Set control's text.

======  ==============================================================
 nil_ 	 Control:setText( string_ sNewText )
======  ==============================================================

----------------------------------------------------------------------


Control:getFont
^^^^^^^^^^^^^^^
	
   Returns the control's font.

=======  =============================================================
 Font_    Control:getFont( )
=======  =============================================================

----------------------------------------------------------------------


Control:setFont
^^^^^^^^^^^^^^^
	
   Set control's font.

======  ============================================================================================
 nil_ 	 Control:setFont( string_ sFontFamily, number_ nFontSize, string_ sFontFlags )
======  ============================================================================================

----------------------------------------------------------------------


Control:setTextMarkup
^^^^^^^^^^^^^^^^^^^^^
  
   Sets the controls label to a string using markup.

   Simple markup supported by this function can be used to apply different fonts or colours to 
   different parts of the control label when supported. If markup is not supported by the control 
   or platform, it is simply stripped and setText() is used with the resulting string.

   For example, 

.. code-block:: lua

textlbl = Label:new {
...
textlbl:setTextMarkup("<b>&amp;Bed</b> &amp;mp; <span foreground='red'>breakfast</span> available <big>HERE</big>");

 would show the string using bold, red and big for the corresponding words under GTK but will 
 simply show the string "Bed &amp; breakfast available HERE" on the other platforms. In any case, 
 the "B" of "Bed" will be underlined to indicate that it can be used as a mnemonic for this control.

The supported tags are: 

========  =======================================================================
 Tag       Description
========  =======================================================================
 <b>       bold text
 <big>     bigger text
 <i>       italic text
 <s>       strike-through text
 <small>   smaller text
 <tt>      monospaced text
 <u>       underlined text
 <span>    generic formatter tag, see the table below for supported attributes. 
========  =======================================================================

Supported <span> attributes:

============================  ======================================================================
 Name                          Description
============================  ======================================================================
 foreground, fgcolor, color    Foreground text colour, can be a name or RGB value.
 background, bgcolor           Background text colour, can be a name or RGB value.
 font_family, face             Font face name.
 font_weight, weight           Numeric value in 0..900 range or one of "ultralight", "light", "normal" (all meaning non-bold), "bold", "ultrabold" and "heavy" (all meaning bold).
 font_style, style             Either "oblique" or "italic" (both with the same meaning) or "normal".
 size                          The font size can be specified either as "smaller" or "larger" relatively to the current font, as a CSS font size name ("xx-small", "x-small", "small", "medium", "large", "x-large" or "xx-large") or as a number giving font size in 1024th parts of a point, i.e. 10240 for a 10pt font.
============================  ======================================================================

This markup language is a strict subset of Pango markup 
(described at http://library.gnome.org/devel/pango/unstable/PangoMarkupFormat.html) and any tags and 
span attributes not documented above can't be used under non-GTK platforms.

Also note that you need to escape the following special characters: 

===================  ================
 Special character    Escape as
===================  ================
 &                    &amp; or as &&
 '                    &apos;
 "                    &quot;
 <                    &lt;
 >                    &gt; 
===================  ================

The non-escaped ampersand & characters are interpreted as mnemonics as with Control:setText

**Parameters**
  markup        String containing markup for the label. It may contain markup tags described above and newline characters but currently only wxGTK and wxOSX support multiline labels with markup, the generic implementation (also used in wxMSW) only handles single line markup labels. Notice that the string must be well-formed (e.g. all tags must be correctly closed) and won't be shown at all otherwise.

*Returns: true if the new label was set (even if markup in it was ignored) or false if we failed to parse the markup. In this case the label remains unchanged*

Currently Button_ supports markup in all major ports (Windows, Linux/GTK and wxOSX/Cocoa) while 
Label supports it in Linux/GTK and wxOSX and its generic version (which can be used under Windows if 
markup support is required). Extending support to more controls is planned in the future.

======  ==============================================================
 nil_    Control:setTextMarkup( string_ sTextMarkup )
======  ==============================================================

----------------------------------------------------------------------


.. // Required values for html docs visualization
.. include:: ../directives.rst