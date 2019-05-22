@inherits
=============================

.. rst:directive:: @inheritdoc

   :Syntax: ``@inheritdoc``
   :Overview:

      The :rst:dir:`@inheritdoc` tag indicates that a symbol should inherit its
      documentation from its parent class. Any other tags that you include in
      the JSDoc comment will be ignored.

      This tag is provided for compatibility with `Closure Compiler <https://developers.google.com/closure/compiler/>`_.
      By default, if you do not add a JSDoc comment to a symbol, the symbol will
      inherit documentation from its parent.

      The presence of the :rst:dir:`@inheritdoc` tag implies the presence of the
      :rst:dir:`@override`.

   :Examples:

      The following example shows how a class can indicate that it inherits
      documentation from its parent class:

      .. code-block:: js
         :caption: Class that inherits from a parent class

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

      You can get the same result by omitting the JSDoc comment from
      ``Socket#open``:

      .. code-block:: js
         :caption: Inheriting documentation without the :rst:dir:`@inheritdoc` tag

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
