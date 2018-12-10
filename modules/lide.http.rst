.. /////// Created 2017/11/12 - Hernan Dario Cano [dcanohdev@gmail.com]
.. // docs/modules/lide.http.rst 0.2.1 Released 
.. //  lide.http reference 0.2.1 2018/12/10 3:33
.. //   (c) 2017 Hernan Dario Cano | Lide License

lide.http
=========

``[lide.http] ^0.2.1``

The library lide.http allows us to do http / https (post, get, put, 
head, delete, etc ...) from lua.


installation
^^^^^^^^^^^^

To install this library use ``lide install``.

``$ lide install lide.http``



dependencies
^^^^^^^^^^^^

The following dependencies are necessary to be able to run the library:

- socket 2.0.2
- ssl_  0.4
- ltn12_ 1.0.3
- cjson_ 2.1.0
- xml_ 1.1.2
- md5_ 1.1.2
- base64_ 5.1.0
- luacurl_ 1.1.0



lua API
^^^^^^^

Basic usage functions.

----------------------------------------------------------------------


http.download
^^^^^^^^^^^^^

   Download the given "url" to "dest" path to the system.

======  ==============================================================
 nil_    http.download ( string_ Url, string_ DestPath, func_ downldCallback ( number_ Downlded, number_ DownldTotal, number_ Percent )  )
======  ==============================================================

----------------------------------------------------------------------


http.test_connection
^^^^^^^^^^^^^^^^^^^^

   Test HTTP or HTTPS connection.

======  ==============================================================
 nil_    http.test_connection ( string_ Url )
======  ==============================================================


----------------------------------------------------------------------

http requests
-------------

The second argument of a request is a table that can be used to make 
more advanced requests. Any request can be made with either a second 
argument or as a table.

.. code-block:: lua

  table requestData = {
    table data,
    table headers,
    table proxy,
    number timeout,
    table auth,   --> result of requests.HTTPDigestAuth
    string cookies,
    bool allow_redirects = true,
  }


http.get
^^^^^^^^

  The GET method requests a representation of a specific resource.
  Requests that use the GET method should only retrieve data.

========  ============================================================
 table_     http.get ( string Url, table requestData )
========  ===========================================================

http.head
^^^^^^^^^

  The HEAD method requests an identical response to that of a GET 
  request, but without the body of the response.

========  ============================================================
 table_     http.head ( string Url, table requestData )
========  ============================================================

http.post
^^^^^^^^^

  The POST method is used to send an entity to a specific resource, 
  often causing a change in state or side effects on the server.

========  ============================================================
 table_     http.post ( string Url, table requestData )
========  ============================================================

http.put
^^^^^^^^

  The PUT mode replaces all current representations of the 
  destination resource with the payload of the request.

========  ============================================================
 table_     http.put ( string Url, table requestData )
========  ============================================================

http.delete
^^^^^^^^^^^

  The DELETE method deletes a specific resource.

========  ============================================================
 table_     http.delete ( string Url, table requestData )
========  ============================================================

http.connect
^^^^^^^^^^^^

  The CONNECT method establishes a tunnel to the server identified 
  by the resource.

========  ============================================================
 table_     http.connect ( string Url, table requestData )
========  ============================================================

http.options
^^^^^^^^^^^^

  The OPTIONS method is used to describe the communication options 
  for the destination resource.

========  ============================================================
 table_     http.options ( string Url, table requestData )
========  ============================================================

http.trace
^^^^^^^^^^

  The TRACE method performs a message loopback test along the route 
  to the destination resource.

========  ============================================================
 table_     http.trace ( string Url, table requestData )
========  ============================================================

http.patch
^^^^^^^^^^

  The PATCH method is used to apply partial modifications to a resource.

========  ============================================================
 table_     http.patch ( string Url, table requestData )
========  ============================================================

.. _dcanoh:  http://github.com/lidesdk/repos/dcanoh.rst>`.
.. _ssl:     https://github.com/lidesdk/repos/blob/master/stable/ssl/readme.rst
.. _ltn12:   https://github.com/lidesdk/repos/blob/master/stable/ltn12/readme.rst
.. _cjson:   https://github.com/lidesdk/repos/blob/master/stable/cjson/readme.rst
.. _xml:     https://github.com/lidesdk/repos/blob/master/stable/xml/readme.rst
.. _md5:     https://github.com/lidesdk/repos/blob/master/stable/md5/readme.rst
.. _base64:  https://github.com/lidesdk/base64/readme.rst
.. _luacurl: https://github.com/lidesdk/repos/blob/master/stable/luacurl/readme.rst
.. _socket:  https://github.com/lidesdk/readme

.. // Required values for html docs visualization
.. include:: ../directives.rst