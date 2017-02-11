Lide commandline plugins
************************

Usted puede crear sus propios plugins utilizando la api de lide, los plugins de lide integrados en el core
son: install, update, remove, search que se encargan de instalar, actualizar, eliminar y buscar packages en nuestra distribución de lide.

Lo unico que tenemos que hacer para que lide pueda cargar nuestros plugins es colocarlos en la carpeta 
"modules" que tenemos en la carpeta raiz de lide.

.. code-block:: rst
 
 C:\lide\modules\
                \install.lua
                \search.lua
                \update.lua
                \remove.lua
                \nuestro_modulo.lua

Podemos usar las tablas framework y repository para ayudarnos a interactuar con la instalacion de lide en 
especifico y hacer cosas como ejecutar scripts o instalar, actualizar o remover modulos en la aplicación.

