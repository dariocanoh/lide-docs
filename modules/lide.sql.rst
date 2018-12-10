.. /////// Created 2018/12/10 3:33 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/modules/lide.sql.rst 0.2.0 Released 
.. //  lide.http reference 0.2.0 2018/12/10 3:33
.. //   (c) 2018 Hernan Dario Cano | Lide License

.. _luasql:   https://github.com/lidesdk/luasql.sqlite3
.. _fbclient: https://github.com/lidesdk/fbclient
.. _Database: #Database:new

lide.sql
========

``[lide.sql] ^0.2``

SQL Databases support for Lide framework.

**Allow us to:**

- lide.sql library allows us to execute queries in sql databases from lua.
- Get data from sql databases from lua.
- Connect trought sqlite3 and firebird.


----------------------------------------------------------------------


installation
^^^^^^^^^^^^

To install this library I recommend using the command line of lide, 
using ``lide install``.

``$ lide install lide.sql``


dependencies
------------

The following dependencies are necessary to be able to run the library:

- lide 0.1
- luasql_ 2.1.0
- fbclient_ 0.5.0


----------------------------------------------------------------------

Database:new
^^^^^^^^^^^^
	
	Create new Database object and connect using given sql driver.

	You can use "firebird" or "sqlite3" as sql database driver.

.. code-block:: lua
	
	sqldb = sql.database:new ( 'sqlite3', 'test.db' );

**SQLite3**

===========  ===========================================================
 Database_ 	  Database:new ( string sqlDriver, string sDatabase )
===========  ===========================================================

**Firebird**

===========  ===========================================================
 Database_ 	  Database:new ( string sqlDriver, string sDatabase, string_ username, string_ password )
===========  ===========================================================

Database:exec
^^^^^^^^^^^^^

	Executes the given SQL statement.

.. code-block:: lua
	
	sqldb:exec 'select * from sqlite_master'

=========  ===========================================================
 table_ 	  Database:exec ( string QueryStatement )
=========  ===========================================================

Database:create_table
^^^^^^^^^^^^^^^^^^^^^

	SQLite CREATE TABLE statement is used to create a new table in any of the given database. 
	Creating a basic table involves naming the table and defining its columns and each column's data type.

.. code-block:: lua
	
	sqldb:create_table { lua_packages = {  
	    package_checksum = "Text",
	    package_date = "Text",
	    package_description = "Text",
	    package_name = "Text",
	    package_prefix = "Text",
	    package_url = "Text",
	    package_version = "Text",
	    package_compat = "Text"
	} };

=========  ===========================================================
 nil_ 	     Database:create_table { table_name = { col1name = string col1value, col2name = string col2value } }
=========  ===========================================================

Database:insert
^^^^^^^^^^^^^^^

	Add new rows of data into a table in the database.

.. code-block:: lua

	sqldb:insert { into = 'lua_packages',
	    package_name = 'mypackage', 
	    package_description = 'Nuevo paquete',
	    package_date = '2018-10-07',
	    package_version = '1.0.0',
	};

=========  ===========================================================
 nil_    	 Database:insert { string into, col1name = string col1value, col2name = string col2value }
=========  ===========================================================

Database:update
^^^^^^^^^^^^^^^

	Used to modify the existing records in a table. 
	You must use WHERE clause with UPDATE query to update selected rows to prevent all the rows would be updated.

.. code-block:: lua

	sqldb:update { 'lua_packages', 
	    where = "package_name like 'mypackage'",
	    set = { package_description = 'Es una nueva version mucho mejor que las anteriores.' }
	}

=========  ===========================================================
 nil_    	 Database:update { string package_name, where = string WhereConditional, set = { col1name = col1value } }
=========  ===========================================================


Database:select
^^^^^^^^^^^^^^^

	Fetch the data from a SQL database table which returns data in the form of a result table. 
	These result tables are also called result sets.

.. code-block:: lua
	
	sqll:select { from = 'lua_packages', 'package_name' }

=========  ===========================================================
 nil_    	 Database:select { from = string table_name , string col1name, string col2value, ... }
=========  ===========================================================



.. // Required values for html docs visualization
.. include:: ../directives.rst