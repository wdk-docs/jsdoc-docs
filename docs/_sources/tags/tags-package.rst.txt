@package
=============================

.. rst:directive:: @package

   :Syntax:

      With the JSDoc tag dictionary (enabled by default):

      :rst:dir:`@package`

       With the `Closure
       Compiler <https://github.com/google/closure-compiler/wiki/Annotating-JavaScript-for-the-Closure-Compiler#jsdoc-tags>`_
       tag dictionary:

       ``@package [{typeExpression}]``

   :Overview:

      The :rst:dir:`@package` tag marks a symbol as package-private. Typically, this
      tag indicates that a symbol is available only to code in the same
      directory as the source file for this symbol. This tag is available in
      JSDoc 3.5.0 and later.

      By default, symbols marked with the :rst:dir:`@package` tag will appear in your
      documentation. In JSDoc 3.3.0 and later, you can use the
      ``-a/--access`` `command-line option <about-commandline.html>`__ to
      change this behavior.

      The :rst:dir:`@package` tag is equivalent to ``@access package``.

   :Examples:

      In the following example, the instance member ``Thingy#_bar`` appears in
      the generated documentation, but with an annotation indicating that it
      is package-private:

      .. code-block:: js
         :caption: Using the @package tag

         /** @constructor */
         function Thingy() {
             /** @package */
             this._bar = 1;
         }
