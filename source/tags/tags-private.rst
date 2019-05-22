@private
=============================

.. rst:directive:: @private

   :Syntax: ``@private [{typeExpression}]``
   :Overview:

      With the JSDoc tag dictionary (enabled by default):

      :rst:dir:`@private` With the `Closure Compiler <https://github.com/google/closure-compiler/wiki/Annotating-JavaScript-for-the-Closure-Compiler#jsdoc-tags>`_
      tag dictionary:

      The :rst:dir:`@private` tag marks a symbol as private, or not meant for general
      use. Private members are not shown in the generated output unless JSDoc
      is run with the ``-p/--private`` command-line option. In JSDoc 3.3.0 and
      later, you can also use the ``-a/--access`` `command-line`_ to change this behavior.

      The :rst:dir:`@private` tag is not inherited by child members. For example, if
      the :rst:dir:`@private` tag is added to a namespace, members of the namespace
      can still appear in the generated output; because the namespace is
      private, the members’ namepath will not include the namespace.

      The :rst:dir:`@private` tag is equivalent to ``@access private``.

   :Examples:

      In the following example, ``Documents`` and ``Documents.Newspaper``
      appear in the generated documentation, but not ``Documents.Diary``.

      .. code-block:: js
         :caption: Using the @private tag

         /** @namespace */
         var Documents = {
             /**
              * An ordinary newspaper.
              */
             Newspaper: 1,
             /**
              * My diary.
              * @private
              */
             Diary: 2
         };
