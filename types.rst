.. _Type:

Types
=====

Objects, references, functions and classes have a property called type, which both restricts the 
operations that are permitted for those entities and provides semantic meaning to the otherwise 
generic sequences of bits. 

----------------------------------------------------------------------------------------------------
.. _nil:

Nil type
********

Nil is a type with a single value, nil, whose main property is to be different from any other value. 
As we have seen, a global variable has a nil value by default, before a first assignment, and you 
can assign nil to a global variable to delete it. 

Lua uses nil as a kind of non-value, to represent the absence of a useful value.

----------------------------------------------------------------------------------------------------

.. _bool:

Boolean type 
************

Bool type is capable of holding one of the two values: true or false. 

----------------------------------------------------------------------------------------------------

.. _number:

Number type
***********

The number type represents real (double-precision floating-point) numbers. Lua has no integer type, 
as it does not need it. There is a widespread misconception about floating-point arithmetic errors 
and some people fear that even a simple increment can go weird with floating-point numbers. 
The fact is that, when you use a double to represent an integer, there is no rounding error at all 
(unless the number is greater than 100,000,000,000,000). 
Specifically, a Lua number can represent any long integer without rounding problems. Moreover, most 
modern CPUs do floating-point arithmetic as fast as (or even faster than) integer arithmetic.

It is easy to compile Lua so that it uses another type for numbers, such as longs or single-precision 
floats. This is particularly useful for platforms without hardware support for floating point. 

We can write numeric constants with an optional decimal part, plus an optional decimal exponent. 
Examples of valid numeric constants are:
.. code-block:: lua
    4     0.4     4.57e-3     0.3e12     5e+20

----------------------------------------------------------------------------------------------------
.. _table:

Table type
**********



----------------------------------------------------------------------------------------------------

.. //_bool:     ../types/bool.html
.. //_string:   ../types/string.html
.. //_nil:      ../types/nil.html
.. //_void:     ../types/void.html
.. //_constant: ../types/constant.html