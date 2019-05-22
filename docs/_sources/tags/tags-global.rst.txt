@global
=============================

.. rst:directive:: @global

   :Syntax: ``@global``
   :Overview:

         The @global tag specifies that a symbol should appear in the
         documentation as a *global* symbol. JSDoc ignores the symbol’s actual
         scope within the source file. This tag is especially useful for symbols
         that are defined locally, then assigned to a global symbol.

   :Examples:

      Use the @global tag to specify that a symbol should be documented as global.

      .. code-block:: js
         :caption: Document an inner variable as a global

         (function() {
             /** @global */
             var foo = 'hello foo';

             this.foo = foo;
         }).apply(window);
