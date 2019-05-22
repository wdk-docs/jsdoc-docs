@description (synonyms: @desc)
================================

.. rst:directive:: @description

   :Synonyms: :rst:dir:`@desc`
   :Syntax: ``@description <some description>``
   :Overview:

      The @description tag allows you to provide a general description of the
      symbol you are documenting. The description may include HTML markup. It
      may also include Markdown formatting if the :ref:`plugins-markdown` is enabled.

   :Examples:

      If you describe a symbol at the very beginning of a JSDoc comment,
      before using any block tags, you may omit the @description tag.

      .. code-block:: js
         :caption: Describing a symbol without the @description tag

         /**
          * Add two numbers.
          * @param {number} a
          * @param {number} b
          * @returns {number}
          */
         function add(a, b) {
             return a + b;
         }

      By using the @description tag, you can place the description anywhere in
      the JSDoc comment.

      .. code-block:: js
         :caption: Describing a symbol with the @description tag

         /**
          * @param {number} a
          * @param {number} b
          * @returns {number}
          * @description Add two numbers.
          */
         function add(a, b) {
             return a + b;
         }

      If there’s both a description at the beginning of a JSDoc comment and a
      description provided with the @description tag, the description
      specified with the @description will override the description at the
      beginning of the comment.

.. rst:directive:: @desc

   :Synonyms: :rst:dir:`@description`
