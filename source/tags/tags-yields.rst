@yields
=============================

.. rst:directive:: @yields

   :Syntax:

      ``@yields [{type}] [description]``

   :Overview:

      The :rst:dir:`@yields` tag documents the value that is yielded by a generator
      function. This tag is available in JSDoc 3.5.0 and later.

      If you are documenting a regular function, use the `@returns
      tag <tags-returns.html>`__ instead of this tag.

   :Examples:

      .. code-block:: js
         :caption: @yields tag with a type

         /**
          * Generate the Fibonacci sequence of numbers.
          *
          * @yields {number}
          */
         function* fibonacci() {}

      .. code-block:: js
         :caption: @yields tag with a type and description

         /**
          * Generate the Fibonacci sequence of numbers.
          *
          * @yields {number} The next number in the Fibonacci sequence.
          */
         function* fibonacci() {}
