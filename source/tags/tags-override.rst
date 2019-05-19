@override
=============================

Overview
--------

The ``@override`` tag indicates that a symbol overrides a symbol with
the same name in a parent class.

This tag is provided for compatibility with `Closure
Compiler <https://developers.google.com/closure/compiler/>`__. By
default, JSDoc automatically identifies symbols that override a parent.

If your JSDoc comment includes the ```@inheritdoc``
tag <tags-inheritdoc.html>`__, you do not need to include the
``@override`` tag. The presence of the ``@inheritdoc`` tag implies the
presence of the ``@override`` tag.

Example
-------

The following example shows how to indicate that a method overrides a
method in its parent class:

{% example “Method that overrides a parent” %}

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

   /**
    * Open the socket.
    * @override
    */
   Socket.prototype.open = function() {
       // ...
   };

{% endexample %}
