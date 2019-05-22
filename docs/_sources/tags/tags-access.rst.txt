@access
=============================

.. rst:directive:: @access

   :Syntax: ``@access <package|private|protected|public>``
   :Overview:

      The :rst:dir:`@access` tag specifies the access level of a member. You can use
      the :rst:dir:`@access` tag as a synonym for other tags:

      -  ``@access package`` is the same as :rst:dir:`@package`.
         This option is available in JSDoc 3.5.0 and later.
      -  ``@access private`` is the same as :rst:dir:`@private`.
      -  ``@access protected`` is the same as :rst:dir:`@protected`.
      -  ``@access public`` is the same as :rst:dir:`@public`.

      Private members are not shown in the generated output unless JSDoc is
      run with the ``-p/--private`` command-line option. In JSDoc 3.3.0 and
      later, you can also use the ``-a/--access`` :ref:`command-line` to change this behavior.

      Note that a doclet’s *access level* is different from its *scope*. For
      example, if ``Parent`` has an inner variable named ``child`` that is
      documented as :rst:dir:`@public`, the ``child`` variable will still be treated
      as an inner variable with the namepath ``Parent~child``. In other words,
      the ``child`` variable will have an inner scope, even though the
      variable is public. To change a doclet’s scope, use the
      :rst:dir:`@instance`,
      :rst:dir:`@static`, and
      :rst:dir:`@global` tags.

   :Examples:

      .. code-block:: js
         :caption: Using @access as a synonym for other tags

         /** @constructor */
         function Thingy() {

             /** @access private */
             var foo = 0;

             /** @access protected */
             this._bar = 1;

             /** @access package */
             this.baz = 2;

             /** @access public */
             this.pez = 3;

         }

         // same as...

         /** @constructor */
         function OtherThingy() {

             /** @private */
             var foo = 0;

             /** @protected */
             this._bar = 1;

             /** @package */
             this.baz = 2;

             /** @public */
             this.pez = 3;

         }
