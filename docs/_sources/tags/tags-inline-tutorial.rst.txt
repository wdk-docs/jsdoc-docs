@inline-tutorial
=============================

.. rst:directive:: @inline-tutorial

   :Syntax:

      .. code-block::

         {@tutorial tutorialID}
         [link text]{@tutorial tutorialID}
         {@tutorial tutorialID|link text}
         {@tutorial tutorialID link text (after the first space)}

   :Overview:

      The :rst:dir:`@tutorial` inline tag creates a link to the tutorial identifier
      that you specify. When you use the :rst:dir:`@tutorial` tag, you can also
      provide link text, using one of several different formats. If you don’t
      provide any link text, JSDoc uses the tutorial’s title as the link text.

      If you need to link to a namepath or a URL,
      use the :rst:dir:`@link` :rst:dir:`@inline` instead of the :rst:dir:`@tutorial` tag.

   :Examples:

      The following example shows all of the ways to provide link text for the
      :rst:dir:`@tutorial` tag:

      .. code-block:: js
         :caption: Providing link text

         /**
          * See {@tutorial gettingstarted} and [Configuring the Dashboard]{@tutorial dashboard}.
          * For more information, see {@tutorial create|Creating a Widget} and
          * {@tutorial destroy Destroying a Widget}.
          */
         function myFunction() {}

      If all of these tutorials are defined, and the title of the
      ``gettingstarted`` tutorial is “Getting Started,” the example above
      produces output similar to the following:



      .. code-block:: html
         :caption: Output for :rst:dir:`@link` tags

         See &lt;a href="tutorial-gettingstarted.html">Getting Started&lt;/a> and
         &lt;a href="tutorial-dashboard.html">Configuring the Dashboard&lt;/a>.
         For more information, see &lt;a href="tutorial-create.html">Creating a Widget&lt;/a> and
         &lt;a href="tutorial-destroy.html">Destroying a Widget&lt;/a>.
