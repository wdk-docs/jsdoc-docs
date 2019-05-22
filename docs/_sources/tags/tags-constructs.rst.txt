@constructs
=============================

.. rst:directive:: @constructs

   :Syntax: ``@constructs [<name>]``
   :Overview:

      When using an object literal to define a class (for example with the
      :rst:dir:`@lends` tag) the :rst:dir:`@constructs` tag allows you to document that a
      particular function will be used to construct instances of that class.

   :Examples:

      .. code-block:: js
         :caption: Using the @constructs tag with @lends

         var Person = makeClass(
             /** @lends Person.prototype */
             {
                 /** @constructs */
                 initialize: function(name) {
                     this.name = name;
                 },
                 /** Describe me. */
                 say: function(message) {
                     return this.name + " says: " + message;
                 }
             }
         );

      .. code-block:: js
         :caption: Without @lends you must provide the name of the class

         makeClass('Menu',
             /**
              * @constructs Menu
              * @param items
              */
             function (items) { },
             {
                 /** @memberof Menu# */
                 show: function(){
                 }
             }
         );
