.. _Types:

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

The table type implements associative arrays. An associative array is an array that can be indexed 
not only with numbers, but also with strings or any other value of the language, except nil. 
Moreover, tables have no fixed size; you can add as many elements as you want to a table dynamically. 
Tables are the main (in fact, the only) data structuring mechanism in Lua, and a powerful one. 
We use tables to represent ordinary arrays, symbol tables, sets, records, queues, and other data 
structures, in a simple, uniform, and efficient way. Lua uses tables to represent packages as well. 
When we write io.read, we mean "the read entry from the io package". For Lua, that means "index the 
table io using the string "read" as the key".

Tables in Lua are neither values nor variables; they are objects. If you are familiar with arrays 
in Java or Scheme, then you have a fair idea of what we mean. However, if your idea of an array 
comes from C or Pascal, you have to open your mind a bit. You may think of a table as a dynamically 
allocated object; your program only manipulates references (or pointers) to them. There are no hidden 
copies or creation of new tables behind the scenes. Moreover, you do not have to declare a table in Lua; 
in fact, there is no way to declare one. You create tables by means of a constructor expression, which 
in its simplest form is written as {}.


----------------------------------------------------------------------------------------------------
.. _string:

String type
***********

Strings have the usual meaning: a sequence of characters. Lua is eight-bit clean and so strings may 
contain characters with any numeric value, including embedded zeros. That means that you can store 
any binary data into a string. Strings in Lua are immutable values. You cannot change a character 
inside a string, as you may in C; instead, you create a new string with the desired modifications, 
as in the next example:

.. code-block:: lua

    a = "one string"
    b = string.gsub(a, "one", "another")  -- change string parts
    print(a)       --> one string
    print(b)       --> another string

Strings in Lua are subject to automatic memory management, like all Lua objects. That means that you 
do not have to worry about allocation and deallocation of strings; Lua handles this for you. A string 
may contain a single letter or an entire book. Lua handles long strings quite efficiently. Programs 
that manipulate strings with 100K or 1M characters are not unusual in Lua. 


----------------------------------------------------------------------------------------------------
.. _object:

Object Type
***********

An object type is a user-defined composite datatype that encapsulates a data structure along with the
functions and procedures needed to manipulate the data. The variables that form the data structure are
called attributes. The functions and procedures that characterize the behavior of the object type are
called methods. A special kind of method called the constructor creates a new instance of the object
type and fills in its attributes.


.. //_bool:     ../types/bool.html
.. //_string:   ../types/string.html
.. //_constant: ../types/constant.html