.. /////// 2018/11/22 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/classes/widgets/controls/tree.rst
.. //  Class Tree reference
.. //   (c) 2018 Hernan Dario Cano

.. _ClassTree:

Tree
====

   Tree is derived from Control_ class.

   ``[lide.widgets] ^1.1`` ``lide.widgets.controls.tree 1.0``


A tree control presents information as a hierarchy, with items that 
may be expanded to show further items.


The general look of a control at runtime is demonstrated in the following picture:

.. image:: ../images/class_tree.png
   :alt: Lide Class Tree
   :align: center

.. note::
  
  Items in a tree control are referenced by wxTreeItemId handles, which
  may be tested for validity by calling wxTreeItemId:IsOk().

----------------------------------------------------------------------


Constructor
***********

Control class has a single constructor:


.. code-block:: lua

 Tree:new { 
    object Parent, string Name,
    number PosX, number PosY,
 }


Arguments
^^^^^^^^^

These arguments are received by class constructor.

============  ========================================================
  Argument     Description
============  ========================================================
 Name          The control name
 Parent        The control parent
 PosX          Position related to X
 PosY          Position related to Y
 Flags         Possible style modificators for Tree control:
              
              =====================================  ============  =========================================================================================================================================================================================================================
                 constant                                value      description
              =====================================  ============  =========================================================================================================================================================================================================================
                ``TR_SINGLE``                            ``0``      For convenience to document that only one item may be selected at a time. Selecting another item causes the current selection, if any, to be deselected. This is the default.
                ``TR_NO_LINES``                          ``4``      Use this style to hide vertical level connectors.
                ``TR_MULTIPLE``                          ``32``     Use this style to allow a range of items to be selected. If a second range is selected, the current range, if any, is deselected.
                ``TR_EXTENDED``                          ``64``     **
                ``TR_HIDE_ROOT``                         ``2048``   Use this style to suppress the display of the root node, effectively causing the first-level nodes to appear as a series of root nodes.
                ``TR_ROW_LINES``                         ``1024``   Use this style to draw a contrasting border between displayed rows.
                ``TR_NO_BUTTONS``                        ``0``      For convenience to document that no buttons are to be drawn.
                ``TR_HAS_BUTTONS``                       ``1``      For convenience to document that no buttons are to be drawn.
                ``TR_EDIT_LABELS``                       ``512``    Use this style if you wish the user to be able to edit labels in the tree control.
                ``TR_TWIST_BUTTONS``                     ``16``     **
                ``TR_LINES_AT_ROOT``                     ``8``      Use this style to show lines between root nodes. Only applicable if ``TR_HIDE_ROOT`` is set and ``TR_NO_LINES`` is not set.
                ``TR_DEFAULT_STYLE``                     ``9``      The set of flags that are closest to the defaults for the native control for a particular toolkit.
                ``TR_FULL_ROW_HIGHLIGHT``              ``8192``     Use this style to have the background colour and the selection highlight extend over the entire horizontal row of the tree control window. (This flag is ignored under Windows unless you specify TR_NO_LINES as well.)
                ``TR_HAS_VARIABLE_ROW_HEIGHT``           ``128``    Use this style to cause row heights to be just big enough to fit the content. If not set, all rows use the largest row height. The default is that this flag is unset. Generic only.
              =====================================  ============  =========================================================================================================================================================================================================================
============  ========================================================

----------------------------------------------------------------------


Events
******

The following events are emitted by this class:

============================  ========================================
  Event name                    Description
============================  ========================================
 Tree.onSelectCell             When the selected date was changed.
============================  ========================================

----------------------------------------------------------------------


Inherited Methods
*****************

These methods are inherited from its super classes:

=====================  ===============================================
  Class Method          Description
=====================  ===============================================
 Object:getName_	       Returns control's name.
 Object:setName_	       Sets the control name.
 Widget:getParent_	     Returns control's parent.
 Widget:setParent_	     Sets the control parent.
 Widget:getPosX_	       Returns control's position related to X.
 Widget:setPosX_	       Sets the control position related to X.
 Widget:getPosY_	       Returns control's position related to Y.
 Widget:setPosY_	       Sets the control position related to Y.
 Widget:getEnabled_      Returns true if is enabled.
 Widget:setEnabled_      Set control enabled or disabled.
 Widget:getVisible_      Returns the control visibility.
 Widget:setVisible_      Returns the control visibility.
 Widget:getBind_         Returns a reference to the C++ control.
=====================  ===============================================

----------------------------------------------------------------------


Class Methods
*************

These methods are defined by this class.


----------------------------------------------------------------------


Tree:addRoot
^^^^^^^^^^^^
   
  Adds the root node to the tree, returning the new item. 

=========  ===========================================================
 nil_       Tree:addRoot( string_ Text, string_ Image )
=========  ===========================================================

----------------------------------------------------------------------


Tree:addItem
^^^^^^^^^^^^
   
  Appends an item to the end of the branch identified by parent, 
  return a new item id. 

=========  ===================================================================================================
 nil_       Tree:addItem( string_ Text, number_ ItemID, object_ ParentItem, string_ Image, number_ selImage )
=========  ===================================================================================================

----------------------------------------------------------------------


Tree:insertItem
^^^^^^^^^^^^^^^
   
  Inserts an item after a given one (previous). 

=========  ==============================================================================================================================
 nil_       Tree:insertItem( string_ Text, number_ ItemID, string_ ParentItem, string_ PreviousItemID, string_ Image, string_ selImage )
=========  ==============================================================================================================================

----------------------------------------------------------------------


Tree:startEditItemText
^^^^^^^^^^^^^^^^^^^^^^
   
  Starts editing the label of the given item.

  This function generates a EVT_TREE_BEGIN_LABEL_EDIT event which can 
  be vetoed so that no text control will appear for in-place editing.

  If the user changed the label (i.e. s/he does not press ESC or leave
  the text control without changes, a EVT_TREE_END_LABEL_EDIT event 
  will be sent which can be vetoed as well.

=========  ===========================================================
 nil_       Tree:startEditItemText( number_ nItemID )
=========  ===========================================================

----------------------------------------------------------------------


Tree:endEditItemText
^^^^^^^^^^^^^^^^^^^^^^
   
  Ends label editing.

  *Note:*

  This function is currently supported under Windows only.

=========  ===========================================================
 nil_       Tree:editItemText( number_ nItemID, bool_ bDiscardChanges = false )
=========  ===========================================================

----------------------------------------------------------------------


Tree:collapse
^^^^^^^^^^^^^
   
  Collapses the given item. 

========  ============================================================
 nil_       Tree:collapse( number_ nItemID )
========  ============================================================

----------------------------------------------------------------------



Tree:collapseAll
^^^^^^^^^^^^^^^^
   
  Collapses the root item. 

========  ============================================================
 nil_       Tree:collapseAll( )
========  ============================================================

----------------------------------------------------------------------



Tree:collapseAllChildren
^^^^^^^^^^^^^^^^^^^^^^^^
   
  Collapses this item and all of its children, recursively. 

========  ============================================================
 nil_       Tree:collapseAllChildren()
========  ============================================================

----------------------------------------------------------------------



Tree:collapseAndReset
^^^^^^^^^^^^^^^^^^^^^
   
  Collapses the given item and removes all children. 

========  ============================================================
 nil_       Tree:collapseAndReset ( ItemID )
========  ============================================================

----------------------------------------------------------------------



Tree:delete
^^^^^^^^^^^
   
  Deletes the specified item. 

=========  ===========================================================
 nil_       Tree:delete( number_ nItemID )
=========  ===========================================================

----------------------------------------------------------------------



Tree:deleteAllItems
^^^^^^^^^^^^^^^^^^^
   
  Deletes all items in the control. xx

=========  ===========================================================
 nil_       Tree:deleteAllItems( )
=========  ===========================================================

----------------------------------------------------------------------



Tree:deleteChildren
^^^^^^^^^^^^^^^^^^^
   
  Deletes all children of the given item (but not the item itself). 

=========  ===========================================================
 string_    Tree:deleteChildren ( number_ nItemID )
=========  ===========================================================

----------------------------------------------------------------------


Tree:expand
^^^^^^^^^^^
   
  Expands the given item. 

=========  ===========================================================
 string_    Tree:expand( number_ nItemID )
=========  ===========================================================

----------------------------------------------------------------------


Tree:expandAll
^^^^^^^^^^^^^^
   
  Expands all items in the tree. 

=========  ===========================================================
 nil_       Tree:expandAll( )
=========  ===========================================================

----------------------------------------------------------------------


Tree:expandAllChildren
^^^^^^^^^^^^^^^^^^^^^^
   
  Expands the given item and all its children recursively. 

=========  ===========================================================
 nil_       Tree:expandAllChildren( number_ nItemID )
=========  ===========================================================

----------------------------------------------------------------------


Tree:ensureVisible
^^^^^^^^^^^^^^^^^^
   
  Scrolls and/or expands items to ensure that the given item is visible. 


=========  ===========================================================
 nil_       Tree:ensureVisible ( nItemID )
=========  ===========================================================

----------------------------------------------------------------------


Tree:getChildrenCount
^^^^^^^^^^^^^^^^^^^^^
   
  Returns the number of items in the branch. 

=========  =====================================================================
 number_    Tree:getChildrenCount( number_ nItemID, bool_ bRecursively = true )
=========  =====================================================================

----------------------------------------------------------------------


Tree:getCount
^^^^^^^^^^^^^
   
  Returns the number of items in the control. 

=========  ===========================================================
 nil_       Tree:getCount( )
=========  ===========================================================

----------------------------------------------------------------------


Tree:getIndent
^^^^^^^^^^^^^^
   
  Returns the current tree control indentation. 

=========  ===========================================================
 nil_       Tree:getIndent( )
=========  ===========================================================


----------------------------------------------------------------------


Tree:getItemText
^^^^^^^^^^^^^^^^
   
  Returns the item label. 

=========  ===========================================================
 nil_       Tree:getItemText( number_ nItemID )
=========  ===========================================================

----------------------------------------------------------------------


Tree:getSelection
^^^^^^^^^^^^^^^^^
   
  Returns the selection, or an invalid item if there is no selection. 

================== ===================================================
 number_, string_       Tree:getSelection( )
================== ===================================================

----------------------------------------------------------------------


Tree:isBold
^^^^^^^^^^^
   
  Returns true if the given item is in bold state. 

=========  =========================================================================================
 nil_       Tree:isBold( number_ nItemID )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Tree:isExpanded
^^^^^^^^^^^^^^^
   
  Returns true if the item is expanded (only makes sense if it has children). 

=========  =========================================================================================
 nil_       Tree:isExpanded( number_ nItemID )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Tree:isSelected
^^^^^^^^^^^^^^^
   
  Returns true if the item is selected. 

=========  =========================================================================================
 nil_       Tree:isSelected( number_ nItemID )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Tree:isVisible
^^^^^^^^^^^^^^

  Returns true if the item is visible on the screen.

=========  =========================================================================================
 nil_       Tree:isVisible( number_ nItemID )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Tree:itemHasChildren
^^^^^^^^^^^^^^^^^^^^
   
  Returns true if the item has children. 

=========  =========================================================================================
 nil_       Tree:itemHasChildren( number_ nItem )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Tree:isEmpty
^^^^^^^^^^^^
   
  Returns true if the control is empty (i.e. has no items, even no root one).

=========  =========================================================================================
 bool_      Tree:isEmpty( )
=========  =========================================================================================

----------------------------------------------------------------------------------------------------


Tree:scrollTo
^^^^^^^^^^^^^
   
  Scrolls the specified item into view.

=========  =========================================================================================
 nil_       Tree:scrollTo( number_ nItemID )
=========  =========================================================================================

----------------------------------------------------------------------


Tree:selectItem
^^^^^^^^^^^^^^^

  Selects the given item.

  In multiple selection controls, can be also used to deselect a 
  currently selected item if the value of select is false.
  
=========  ===========================================================
 nil_       Tree:selectItem( nItemID, bool bSelect )
=========  ===========================================================

----------------------------------------------------------------------


Tree:setIndent
^^^^^^^^^^^^^^

  Sets the indentation for the tree control.
  
=========  ===========================================================
 nil_       Tree:setIndent( nIndentValue )
=========  ===========================================================

----------------------------------------------------------------------


Tree:setItemBold
^^^^^^^^^^^^^^^^

  Makes item appear in bold font if bold parameter is true or resets 
  it to the normal state.
 
=========  ===========================================================
 nil_       Tree:setItemBold( number_ nItemID, bool_ bBold )
=========  ===========================================================

----------------------------------------------------------------------


Tree:setItemDropHighlight
^^^^^^^^^^^^^^^^^^^^^^^^^

  Gives the item the visual feedback for Drag'n'Drop actions, which 
  is useful if something is dragged from the outside onto the tree 
  control (as opposed to a DnD operation within the tree control, 
  which already is implemented internally).
  
=========  ================================================================
 nil_       Tree:setItemDropHighlight( number_ nItemID, bool_ bHighlight )
=========  ================================================================

----------------------------------------------------------------------


Tree:setItemText
^^^^^^^^^^^^^^^^

  Sets the item label.
 
=========  ===========================================================
 nil_       Tree:setItemText( number_ nItemID, string_ sItemText )
=========  ===========================================================

----------------------------------------------------------------------


Tree:sortChildren
^^^^^^^^^^^^^^^^^

  Sorts the children of the given item using OnCompareItems().

  You should override that method to change the sort order (the default 
  is ascending case-sensitive alphabetical order).
  
=========  ===========================================================
 nil_       Tree:sortChildren( number_ nItemID )
=========  ===========================================================

----------------------------------------------------------------------


Tree:toggle
^^^^^^^^^^^

  Toggles the given item between collapsed and expanded states.
  
=========  ===========================================================
 nil_       Tree:toggle( number_ nItemID )
=========  ===========================================================

----------------------------------------------------------------------


Tree:toggleItemSelection
^^^^^^^^^^^^^^^^^^^^^^^^

  Toggles the given item between selected and unselected states.

  For multiselection controls only.
  
=========  ===========================================================
 nil_       Tree:toggle( number_ nItemID )
=========  ===========================================================

----------------------------------------------------------------------


Tree:unselect
^^^^^^^^^^^^^

  Removes the selection from the currently selected item (if any).
  
=========  ===========================================================
 nil_       Tree:unselect( )
=========  ===========================================================

----------------------------------------------------------------------


Tree:unselectAll
^^^^^^^^^^^^^^^^

  This function either behaves the same as unselect() if the control 
  doesn't have TR_MULTIPLE style, or removes the selection from all 
  items if it does have this style.
  
=========  ===========================================================
 nil_       Tree:unselectAll( )
=========  ===========================================================

----------------------------------------------------------------------


Tree:unselectItem
^^^^^^^^^^^^^^^^^

  Unselects the given item.

  This works in multiselection controls only.
  
=========  ===========================================================
 nil_       Tree:unselectItem( number_ nItemID )
=========  ===========================================================

----------------------------------------------------------------------


.. // Required values for html docs visualization
.. include:: ../directives.rst