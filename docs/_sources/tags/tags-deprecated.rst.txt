@deprecated
=============================

.. rst:dir:: @deprecated

   :Syntax: ``@deprecated [<some text>]``
   :Overview: The @deprecated tag marks a symbol in your code as being deprecated.
   :Examples:

      You can use the @deprecated tag by itself, or include some text that
      describes more about the deprecation.

      .. code-block:: js
         :caption: Document that the old function has been deprecated since version 2.0

         /**
          * @deprecated since version 2.0
          */
         function old() {
         }
