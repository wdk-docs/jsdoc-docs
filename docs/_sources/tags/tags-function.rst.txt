@function
=============================

.. rst:directive:: @function

   :Syntax: ``@function [<FunctionName>]``
   :Overview: This marks an object as being a function, even though it may not appear
      to be one to the parser. It sets the doclet’s
      :rst:dir:`@kind` to ‘function’.

   :Examples:

      .. code-block:: js
         :caption: Using @function to mark a function.

         /** @function */
         var paginate = paginateFactory(pages);

      Without the @function tag, the ``paginate`` object would be documented
      as a generic object (a :rst:dir:`@member`),
      because it isn’t possible to tell from examining the line of code what
      type of value ``paginate`` will hold when it is run.

      .. code-block:: js
         :caption: Using @function with a name.

         /** @function myFunction */

         // the above is the same as:
         /** @function
          * @name myFunction */
