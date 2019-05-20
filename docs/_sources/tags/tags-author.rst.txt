@author
=============================

.. rst:directive:: @author

   :Syntax:

      ``@author <name> [<emailAddress>]``

   :Overview:

      The @author tag identifies the author of an item. In JSDoc 3.2 and
      later, if the author’s name is followed by an email address enclosed in
      angle brackets, the default template will convert the email address to a
      ``mailto:`` link.

   :Examples:

      .. code-block:: js
         :caption: Documenting the author of an item

         /**
          * @author Jane Smith &lt;jsmith@example.com>
          */
         function MyClass() {}
