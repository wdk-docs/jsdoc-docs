@inherits
=============================

Overview
--------

The ``@inheritdoc`` tag indicates that a symbol should inherit its
documentation from its parent class. Any other tags that you include in
the JSDoc comment will be ignored.

This tag is provided for compatibility with `Closure
Compiler <https://developers.google.com/closure/compiler/>`__. By
default, if you do not add a JSDoc comment to a symbol, the symbol will
inherit documentation from its parent.

The presence of the ``@inheritdoc`` tag implies the presence of the
```@override`` tag <tags-override.html>`__.

Examples
--------

The following example shows how a class can indicate that it inherits
documentation from its parent class:

{% example “Class that inherits from a parent class” %}

.. code-block:: js

   /**
    * @classdesc Abstract class representing a network connection.
    * @class
    */
   function Connection() {}

   /**
    * Open the connection.
    */
   Connection.prototype.open = function() {
       // ...
   };


   /**
    * @classdesc Class representing a socket connection.
    * @class
    * @augments Connection
    */
   function Socket() {}

   /** @inheritdoc */
   Socket.prototype.open = function() {
       // ...
   };

{% endexample %}

You can get the same result by omitting the JSDoc comment from
``Socket#open``:

{% example “Inheriting documentation without the ``@inheritdoc`` tag” %}

.. code-block:: js

   /**
    * @classdesc Abstract class representing a network connection.
    * @class
    */
   function Connection() {}

   /**
    * Open the connection.
    */
   Connection.prototype.open = function() {
       // ...
   };


   /**
    * @classdesc Class representing a socket connection.
    * @class
    * @augments Connection
    */
   function Socket() {}

   Socket.prototype.open = function() {
       // ...
   };

{% endexample %}
