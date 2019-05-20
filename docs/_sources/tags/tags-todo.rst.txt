@todo
=============================

.. rst:directive:: @todo

   :Syntax:

      ``@todo`` text describing thing to do.

   :Overview:

      The @todo tag allows you to document tasks to be completed for some part
      of your code. You can use the @todo tag more than once in a single JSDoc
      comment.

   :Examples:

      .. code-block:: js
         :caption: Using the @todo tag

         /**
          * @todo Write the documentation.
          * @todo Implement this function.
          */
         function foo() {
             // write me
         }
