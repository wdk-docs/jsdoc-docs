plugins markdown
======================

JSDoc includes a Markdown plugin that automatically converts
Markdown-formatted text to HTML. You can use this plugin with any JSDoc
template. In JSDoc 3.2.2 and later, the Markdown plugin uses the `marked
Markdown parser <https://github.com/chjj/marked>`__.

**Note**: When you enable the Markdown plugin, be sure to include a
leading asterisk on each line of your JSDoc comments. If you omit the
leading asterisks, JSDoc’s parser may remove asterisks that are used for
Markdown formatting.

By default, JSDoc looks for Markdown-formatted text in the following
JSDoc tags:

-  ```@author`` <tags-author.html>`__
-  ```@classdesc`` <tags-classdesc.html>`__
-  ```@description`` <tags-description.html>`__ (including untagged
   descriptions at the start of a JSDoc comment)
-  ```@param`` <tags-param.html>`__
-  ```@property`` <tags-property.html>`__
-  ```@returns`` <tags-returns.html>`__
-  ```@see`` <tags-see.html>`__
-  ```@throws`` <tags-throws.html>`__

Enabling the Markdown plugin
----------------------------

To enable the Markdown plugin, add the string ``plugins/markdown`` to
the ``plugins`` array in your `JSDoc configuration
file <about-configuring-jsdoc.html>`__:

{% example “JSON configuration file that enables the Markdown plugin” %}

.. code-block:: json

   {
       "plugins": ["plugins/markdown"]
   }

{% endexample %}

Converting Markdown in additional JSDoc tags
--------------------------------------------

By default, the Markdown plugin only processes `specific JSDoc
tags <#default-tags>`__ for Markdown text. You can handle Markdown text
in other tags by adding a ``markdown.tags`` property to your JSDoc
configuration file. The ``markdown.tags`` property contains an array of
the additional doclet properties that can contain Markdown text. (In
most cases, the name of the doclet property is the same as the tag name.
However, some tags are stored differently; for example, the ``@param``
tag is stored in a doclet’s ``params`` property. If you’re not sure how
a tag’s text is stored in a doclet, run JSDoc with the ``-X/--explain``
tag, which prints each doclet to the console.)

For example, if the ``foo`` and ``bar`` tags accept values that are
stored in a doclet’s ``foo`` and ``bar`` properties, you could enable
Markdown processing of these tags by adding the following settings to
your JSDoc configuration file:

{% example “Converting Markdown in ‘foo’ and ‘bar’ tags” %}

.. code-block:: json

   {
       "plugins": ["plugins/markdown"],
       "markdown": {
           "tags": ["foo", "bar"]
       }
   }

{% endexample %}

Excluding the default tags from Markdown processing
---------------------------------------------------

To prevent the Markdown plugin from processing any of the `default JSDoc
tags <#default-tags>`__, add a ``markdown.excludeTags`` property to your
JSDoc configuration file. The ``markdown.excludeTags`` property contains
an array of the default tags that should not be processed for Markdown
text.

For example, to exclude the ``author`` tag from Markdown processing:

{% example “Excluding the ‘author’ tag from Markdown processing” %}

.. code-block:: json

   {
       "plugins": ["plugins/markdown"],
       "markdown": {
           "excludeTags": ["author"]
       }
   }

{% endexample %}

Hard-wrapping text at line breaks
---------------------------------

By default, the Markdown plugin does not hard-wrap text at line breaks.
This is because it’s normal for a JSDoc comment to be wrapped across
multiple lines. If you prefer to hard-wrap text at line breaks, set your
JSDoc configuration file’s ``markdown.hardwrap`` property to ``true``.
This property is available in JSDoc 3.4.0 and later.

Adding ID attributes to headings
--------------------------------

By default, the Markdown plugin does not add an ``id`` attribute to each
HTML heading. To automatically add ``id`` attributes based on the
heading’s text, set your JSDoc configuration file’s
``markdown.idInHeadings`` property to ``true``. This property is
available in JSDoc 3.4.0 and later.
