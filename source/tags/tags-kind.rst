@kind
=============================

.. rst:directive:: @kind

   :Syntax: ``@kind <kindName>``

      where ``<kindName>`` is one of:

         -  class
         -  constant
         -  event
         -  external
         -  file
         -  function
         -  member
         -  mixin
         -  module
         -  namespace
         -  typedef

   :Overview:

      The @kind tag is used to document what *kind* of symbol is being
      documented (for example, a class or a module). The *kind* of symbol
      differs from a symbol’s *type* (for example, string or boolean).

      Usually you do not need the @kind tag, because the symbol’s kind is
      determined by other tags in the doclet. For example, using the :rst:dir:`@class`
      tag automatically implies “@kind class”, and using the :rst:dir:`@namespace` tag
      implies “@kind namespace”.

   :Examples:

      .. code-block:: js
         :caption: Using @kind

         // The following examples produce the same result:

         /**
          * A constant.
          * @kind constant
          */
         const asdf = 1;

         /**
          * A constant.
          * @constant
          */
         const asdf = 1;

      In the case of tags with conflicting kinds (for example, using both
      :rst:dir:`@module`, which sets the kind to “module”, and “@kind constant” which
      sets the kind to “constant”), the last tag determines the kind.

      .. code-block:: js
         :caption: Conflicting @kind statements

         /**
          * This will show up as a constant
          * @module myModule
          * @kind constant
          */

         /**
          * This will show up as a module.
          * @kind constant
          * @module myModule
          */
