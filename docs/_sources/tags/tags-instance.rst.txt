@instance
=============================

.. rst:directive:: @instance

   :Syntax: ``@instance``
   :Overview:

      Using the @instance tag will mark a symbol as an instance member of its
      parent symbol. This means it can be referred to by “Parent#Child”.

      Using @instance will override a doclet’s default scope (unless it is in
      the global scope, in which case it will remain global).

   :Examples:

      The following example is a longhand way of writing “@function
      MyNamespace#myFunction”:

      .. code-block:: js
         :caption: Using @instance to make a virtual doclet an instance member

         /** @namespace MyNamespace */
         /**
          * myFunction is now MyNamespace#myFunction.
          * @function myFunction
          * @memberof MyNamespace
          * @instance
          */

      More usefully, you can use the @instance tag to override the scope that
      JSDoc infers. For example, you can indicate that a static member is used
      as an instance member:

      .. code-block:: js
         :caption: Using @instance to identify an instance member

         /** @namespace */
         var BaseObject = {
             /**
              * foo is now BaseObject#foo rather than BaseObject.foo.
              * @instance
              */
             foo: null
         };

         /** Generates BaseObject instances. */
         function fooFactory(fooValue) {
             var props = { foo: fooValue };
             return Object.create(BaseObject, props);
         }
