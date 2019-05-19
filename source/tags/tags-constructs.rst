Overview
--------

When using an object literal to define a class (for example with the
``@lends`` tag) the ``@constructs`` tag allows you to document that a
particular function will be used to construct instances of that class.

Syntax
------

``@constructs [<name>]``

Examples
--------

{% example “Using the @constructs tag with @lends” %}

.. code:: js

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

{% endexample %}

{% example “Without @lends you must provide the name of the class” %}

.. code:: js

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

{% endexample %}
