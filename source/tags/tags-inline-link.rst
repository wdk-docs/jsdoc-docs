@link (synonyms: {@linkcode}, {@linkplain})
================================================

.. rst:directive:: @link

   :Synonyms: :rst:dir:`@linkcode`, :rst:dir:`@linkplain`
   :Syntax:

      .. code-block:: sh

         {@link namepathOrURL}
         [link text]{@link namepathOrURL}
         {@link namepathOrURL|link text}
         {@link namepathOrURL link text (after the first space)}

   :Overview:

      The :rst:dir:`@link` inline tag creates a link to the namepath or URL that
      you specify. When you use the :rst:dir:`@link` tag, you can also provide link
      text, using one of several different formats. If you don’t provide any
      link text, JSDoc uses the namepath or URL as the link text.

      If you need to link to a tutorial, use the :rst:dir:`@tutorial`  instead of the ``@link`` tag.

   :Link formatting:

      By default, :rst:dir:`@link` generates standard HTML anchor tags. However,
      you may prefer to render certain links in a monospace font, or to
      specify the format of individual links. You can use the following
      synonyms for the :rst:dir:`@link` tag to control the formatting of links:

      -  :rst:dir:`@linkcode`: Forces the link’s text to use a monospace font.
      -  :rst:dir:`@linkplain`: Forces the link’s text to appear as normal text,
         without a monospace font.

      You can also set one of the following options in JSDoc’s configuration
      file; see `Configuring JSDoc <about-configuring-jsdoc.html>`__ for more
      details:

      -  ``templates.cleverLinks``: When set to ``true``, links to URLs use
         normal text, and links to code use a monospace font.
      -  ``templates.monospaceLinks``: When set to ``true``, all links use a
         monospace font, except for links created with the :rst:dir:`@linkplain`
         tag.

      .. attention::
         Although the default JSDoc template renders all of these tags
         correctly, other templates may not recognize the :rst:dir:`@linkcode` and
         :rst:dir:`@linkplain` tags. In addition, other templates may ignore the
         configuration options for link rendering.

   :Examples:

      The following example shows all of the ways to provide link text for the
      :rst:dir:`@link` tag:

      .. code-block:: js
         :caption: Providing link text

         /**
          * See {@link MyClass} and [MyClass's foo property]{@link MyClass#foo}.
          * Also, check out {@link http://www.google.com|Google} and
          * {@link https://github.com GitHub}.
          */
         function myFunction() {}

      By default, the example above produces output similar to the following:

         :caption: Output for {@link} tags

      .. code-block:: html

         See &lt;a href="MyClass.html">MyClass&lt;/a> and &lt;a href="MyClass.html#foo">MyClass's foo
         property&lt;/a>. Also, check out &lt;a href="http://www.google.com">Google&lt;/a> and
         &lt;a href="https://github.com">GitHub&lt;/a>.

      If the configuration property ``templates.cleverLinks`` were set to
      ``true``, the example above would produce the following output:

         :caption: Output with clever links enabled

      .. code-block:: html

         See &lt;a href="MyClass.html">&lt;code>MyClass&lt;/code>&lt;/a> and &lt;a href="MyClass.html#foo">
         &lt;code>MyClass's foo property&lt;/code>&lt;/a>. Also, check out
         &lt;a href="http://www.google.com">Google&lt;/a> and &lt;a href="https://github.com">GitHub&lt;/a>.


.. rst:directive:: @linkcode

   :Synonyms: :rst:dir:`@link`

.. rst:directive:: @linkplain

   :Synonyms: :rst:dir:`@link`
