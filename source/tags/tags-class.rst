@class
=============================

.. rst:directive:: @class

   :Syntax:

      ``@class [<type> <name>]``

   :Overview: The @class tag marks a function as being a constructor, meant to be
      called with the new keyword to return an instance.

   :Examples:

      .. code-block:: js
        :caption: A function that constructs Person instances.

        /**
            * Creates a new Person.
            * @class
            */
        function Person() {
        }

        var p = new Person();
