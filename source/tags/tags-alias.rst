@alias
=============================

.. rst:directive:: @alias

   :Syntax: ``@alias <aliasNamepath>``
   :Overview:

      The :rst:dir:`@alias` tag causes JSDoc to treat all references to a member as if
      the member had a different name. This tag is especially useful if you
      define a class within an inner function; in this case, you can use the
      :rst:dir:`@alias` tag to tell JSDoc how the class is exposed in your app.

      While the :rst:dir:`@alias` tag may sound similar to the :rst:dir:`@name` tag, these tags
      behave very differently. The :rst:dir:`@name` tag tells JSDoc to ignore any code
      associated with the comment. For example, when JSDoc processes the
      following code, it ignores the fact that the comment for ``bar`` is
      attached to a function:

      .. code-block:: js

         /**
          * Bar function.
          * @name bar
          */
         function foo() {}

      The :rst:dir:`@alias` tag tells JSDoc to pretend that Member A is actually named
      Member B. For example, when JSDoc processes the following code, it
      recognizes that ``foo`` is a function, then renames ``foo`` to ``bar``
      in the documentation:

      .. code-block:: js

         /**
          * Bar function.
          * @alias bar
          */
         function foo() {}

   :Examples:

      Suppose you are using a class framework that expects you to pass in a
      constructor function when you define a class. You can use the :rst:dir:`@alias` tag
      to tell JSDoc how the class will be exposed in your app.

      In the following example, the :rst:dir:`@alias` tag tells JSDoc to treat the
      anonymous function as if it were the constructor for the class
      “trackr.CookieManager”. Within the function, JSDoc interprets the
      ``this`` keyword relative to trackr.CookieManager, so the “value” method
      has the namepath “trackr.CookieManager#value”.

      .. code-block:: js
         :caption: Using :rst:dir:`@alias` with an anonymous constructor function

         Klass('trackr.CookieManager',

             /**
              * @class
              * @alias trackr.CookieManager
              * @param {Object} kv
              */
             function(kv) {
                 /** The value. */
                 this.value = kv;
             }

         );

      You can also use the :rst:dir:`@alias` tag with members that are created within an
      immediately invoked function expression (IIFE). The :rst:dir:`@alias` tag tells
      JSDoc that these members are exposed outside of the IIFE’s scope.

      .. code-block:: js
         :caption: Using :rst:dir:`@alias` for static members of a namespace

         /** @namespace */
         var Apple = {};

         (function(ns) {
             /**
              * @namespace
              * @alias Apple.Core
              */
             var core = {};

             /** Documented as Apple.Core.seed */
             core.seed = function() {};

             ns.Core = core;
         })(Apple);

      For members that are defined within an object literal,
      you can use the :rst:dir:`@alias` tag as an alternative to the [@lends]\ :rst:dir:`lends` tag.

      .. code-block:: js
         :caption: Using @alias for an object literal

         // Documenting objectA with @alias

         var objectA = (function() {

             /**
              * Documented as objectA
              * @alias objectA
              * @namespace
              */
             var x = {
                 /**
                  * Documented as objectA.myProperty
                  * @member
                  */
                 myProperty: 'foo'
             };

             return x;
         })();

         // Documenting objectB with @lends

         /**
          * Documented as objectB
          * @namespace
          */
         var objectB = (function() {

             /** @lends objectB */
             var x = {
                 /**
                  * Documented as objectB.myProperty
                  * @member
                  */
                 myProperty: 'bar'
             };

             return x;
         })();
