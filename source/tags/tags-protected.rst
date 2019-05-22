@protected
=============================

.. rst:directive:: @protected

   :Syntax: ``@protected [{typeExpression}]``
   :Overview:

      With the JSDoc tag dictionary (enabled by default): @protected With the `Closure Compiler <https://github.com/google/closure-compiler/wiki/Annotating-JavaScript-for-the-Closure-Compiler#jsdoc-tags>`_
      tag dictionary:

      The :rst:dir:`@protected` tag marks a symbol as protected. Typically, this tag
      indicates that a symbol is only available, or should only be used,
      within the current module.

      By default, symbols marked with the :rst:dir:`@protected` tag will appear in
      your documentation. In JSDoc 3.3.0 and later, you can use the
      ``-a/--access`` :ref:`command-line` to
      change this behavior.

      The :rst:dir:`@protected` tag is equivalent to ``@access protected``.

   :Examples:

      In the following example, the instance member ``Thingy#_bar`` appears in
      the generated documentation, but with an annotation indicating that it
      is protected:

      .. code-block:: js
         :caption: Using the @protected tag

         /** @constructor */
         function Thingy() {
             /** @protected */
             this._bar = 1;
         }
