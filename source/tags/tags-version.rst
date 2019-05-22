@version
=============================

.. rst:directive:: @version

   :Syntax: ``@version``
   :Overview:

      Documents the version of an item. The text following the @version tag
      will be used to denote the version of the item.

   :Examples:

      .. code-block:: js
         :caption: Using the @version tag

         /**
          * Solves equations of the form a * x = b. Returns the value
          * of x.
          * @version 1.2.3
          * @tutorial solver
          */
         function solver(a, b) {
             return b / a;
         }
