Métodos de las Clases
=====================

Estos métodos permiten interactuar con las clases directamente y hacer modificaciones utiles para
los constructores y metodos de las clases y las instancias.

Class:enum
**********

===========  =======================================================================================
 table_       Class : enum ( table_ tblEnum )
===========  =======================================================================================

El método ``enum`` permite agregar valores constantes a las clases, devuelve una tabla de **sólo lectura** que
contiene los valores proporcionados para el enum.

.. code-block:: lua

	ClassConstants = Class:enum {
		CONST_1 = 100,
		CONST_2 = 200,
	}

	print( Class.CONST_1 )          -->> 100
	print( ClassConstants.CONST_1 ) -->> 100


.. include:: ../directives.rst