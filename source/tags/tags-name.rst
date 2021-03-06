@name
=============================

.. rst:directive:: @name

   :Syntax: ``@name <namePath>``
   :Overview:

      The @name tag forces JSDoc to associate the remainder of the JSDoc
      comment with the given name, ignoring all surrounding code. This tag is
      best used in “virtual comments” for symbols that are not readily visible
      in the code, such as methods that are generated at runtime.

      When you use the @name tag, you must provide additional tags that tell
      JSDoc what kind of symbol you are documenting; whether the symbol is a
      member of another symbol; and so on. If you do not provide this
      information, the symbol will not be documented correctly.

      .. warning::
         By using the @name tag, you are telling JSDoc to *ignore
         the surrounding code* and treat your documentation comment in isolation.
         In many cases, it is best to use the [@alias
         tag]\ :rst:dir:`alias` instead, which changes a symbol’s
         name in the documentation but preserves other information about the symbol.

   :Examples:

      The following example shows how to use the @name tag to document a
      function that JSDoc would not normally recognize.

      .. code-block:: js
         :caption: Using the @name tag

         /**
          * @name highlightSearchTerm
          * @function
          * @global
          * @param {string} term - The search term to highlight.
          */
         eval("window.highlightSearchTerm = function(term) {};")
