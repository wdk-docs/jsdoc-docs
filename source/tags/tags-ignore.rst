@ignore
=============================

.. rst:directive:: @ignore

   :Syntax: ``@ignore``
   :Overview:

      The :rst:dir:`@ignore` tag indicates that a symbol in your code should never
      appear in the documentation. This tag takes precedence over all others.

      For most JSDoc templates, including the default template, the
      :rst:dir:`@ignore` tag has the following effects:

      -  If you use the :rst:dir:`@ignore` tag with the :rst:dir:`@class` or :rst:dir:`@module`
         tag, the entire class or module will be omitted from the
         documentation.
      -  If you use the :rst:dir:`@ignore` tag with the :rst:dir:`@namespace` tag, you must
         also add the :rst:dir:`@ignore` tag to any child classes and namespaces.
         Otherwise, your documentation will show the child classes and
         namespaces, but with incomplete names.

   :Examples:

      In the following example, ``Jacket`` and ``Jacket#color`` will not
      appear in the documentation.

      .. code-block:: js
         :caption: Class with :rst:dir:`@ignore` tag

         /**
          * @class
          * @ignore
          */
         function Jacket() {
             /** The jacket's color. */
             this.color = null;
         }

      In the following example, the ``Clothes`` namespace contains a
      ``Jacket`` class. The :rst:dir:`@ignore` tag must be added to both ``Clothes``
      and ``Clothes.Jacket``. ``Clothes``, ``Clothes.Jacket``, and
      ``Clothes.Jacket#color`` will not appear in the documentation.

      .. code-block:: js
         :caption: Namespace with child class

         /**
          * @namespace
          * @ignore
          */
         var Clothes = {
             /**
              * @class
              * @ignore
              */
             Jacket: function() {
                 /** The jacket's color. */
                 this.color = null;
             }
         };
