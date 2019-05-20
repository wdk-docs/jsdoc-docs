@throws
=============================

.. rst:directive:: @throws

   :Syntax:

      -  ``@throws free-form description``
      -  ``@throws {<type>}``
      -  ``@throws {<type>} free-form description``

   :Overview:

      The @throws tag allows you to document an error that a function might
      throw. You can include the @throws tag more than once in a single JSDoc
      comment.

   :Examples:

      .. code-block:: js
         :caption: Using the @throws tag with a type

         /**
          * @throws {InvalidArgumentException}
          */
         function foo(x) {}

      .. code-block:: js
         :caption: Using the @throws tag with a description

         /**
          * @throws Will throw an error if the argument is null.
          */
         function bar(x) {}

      .. code-block:: js
         :caption: Using the @throws tag with a type and description

         /**
          * @throws {DivideByZero} Argument x must be non-zero.
          */
         function baz(x) {}
