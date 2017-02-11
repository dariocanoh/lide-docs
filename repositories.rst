Lide Repositories
*****************

Dentro del repositorio de lide, están guardadas las versiones correctas de las librerias utilizadas
por el framework y otros paquetes de librerias populares soportadas por lide team.

La configuración de los repositorios del framework está guardada en el archivo lide.repos, este archivo
puede ser modificado sin problemas, añadiendo más repositorios al framework para tener diferentes fuentes 
de descarga o para crear nuestro propio repositorio.


Repositorios propios
********************

Simplemente debemos seguir una pequeña especificación para poder crear nuestro repositorio, posteriormente
modificamos el archivo lide.repos, por ejemplo si tuviera el archivo de base de datos del repositorio 
en la ruta: "http://miurl.com/mirepo.db" y suponiendo que el nombre del repositorio es mirepo.

.. code-block::

 [stable]
 url=http://github.com/lidesdk/repos/libraries.db
 
 [mirepo]
 url=http://miurl.com/mirepo.db


Base de datos
^^^^^^^^^^^^^

Necesitamos un archivo sqlite3 que se encargará de guardar la información acerca de los paquetes
que componen el repositorio, la estructura de la base de datos es ésta:

- github.com/lidesdk/repos/stable.db

================  =======================  ===============  ===================  ================
  package_name      package_description      package_url      package_version      package_date  
================  =======================  ===============  ===================  ================
 luasql            LuaSQL is a simp...      http://l         1.0.0.0              01/01/2017     
================  =======================  ===============  ===================  ================

- **package_name**: Se trata del nombre del paquete, no debe tener espacios.

- **package_description**: Una breve descripción acerca de lo que hace la librería.

- **package_url**: Ésta es la URL desde la que se puede descargar el paquete.

- **package_version**: La versión del paquete.

- **package_date**: La versión de publicación de la última versión.


Definición de Paquetes
^^^^^^^^^^^^^^^^^^^^^^

Los paquetes dentro del repositorio tambien tienen una especificación interna, para garantizar un total
control en la instalación del paquete para tener mayor seguridad.

- **Estructura de carpetas:**

Un paquete de lide es un archivo zip que contiene las librerias que se van a copiar en el sistema.
Adicionalmente también dentro del archivo zip se debe incluir un archivo .manifest que define la 
estructura del paquete, la información de la version, etc.

.. code-block::

 - base64.zip:
   | 
   ├── base64.manifest
   ├── windows
   |   └── x86
   |        └── clibs
   |              └── base64.dll
   ├── linux
   |   └── x86
   |        └── clibs
   |              └── base64.so




- **Archivo Manifest:**
Es el archivo más importante dentro del paquete ya que determina como debe instalarse el paquete, 
siguiendo con el ejemplo del paquete base64, éste seria el archivo base64.manifest:

.. code-block::

 [base64]
 author    = luiz henrique de figueiredo
 date      = 25/12/2016
 version   = 5.1
 windows   = x86:windows/x86/clibs/base64.dll
 linux     = x86:linux/x86/clibs/base64.so
 source    = http://webserver2.tecgraf.puc-rio.br/~lhf/ftp/lua/5.1/lbase64.tar.gz
 mantainer = lide team

Para determinar qué archivos deben ser copiados al sistema tenemos los parametros:

================  ====================================  =====================================================
  valor             example data                          opciones
================  ====================================  =====================================================
 windows           Para sistemas operativos Windows      ``x86`` arquitectura 32 bits | ``x64`` arquitectura 64 bits
 linux             Para sistemas operativos Linux        ``x86`` arquitectura 32 bits | ``x64`` arquitectura 64 bits
 all               Para todos los sistemas operativos    ``x86`` arquitectura 32 bits | ``x64`` arquitectura 64 bits
================  ====================================  =====================================================

**Ejemplo:** Por ejemplo si queremos agregar la libreria base64 tambien para arquitecturas x64, seria algo así:

.. code-block::

 [base64]
 author    = luiz henrique de figueiredo
 date      = 25/12/2016
 version   = 5.1
 windows   = x86:windows/x86/clibs/base64.dll  |  x64:windows/x64/clibs/base64.dll
 linux     = x86:linux/x86/clibs/base64.dll    |  x64:linux/x64/clibs/base64.dll
 ...

Si notamos se utiliza el caracter "|" como separador de archivos, adicionalmente se debe definir la
arquitectura del sistema operativo.

De ésta manera dejamos las instrucciones necesarias para que en cualquiera de las dos arquitecturas
del sistema operativo Windows sea soportada por nuestro paquete.

Los valores que pueden ser agregados al archivo manifest son:

================  ====================================
  valor             description                       
================  ====================================
 windows           Aqui se definen los archivos del paquete que se deben copiar a sistemas Windows.
 linux             Aqui se definen los archivos del paquete que se deben copiar a sistemas Linux.
 author            El nombre y/o sitio web del autor.
 date              La fecha de publicación del módulo.
 version           La versión publicada del módulo.
 source            El sitio web del código fuente de ésta versión en especifico.
 mantainer	       Nombre del mantenedor del paquete.
================  ====================================