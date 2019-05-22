.. _command-line:

Command-line arguments to JSDoc
=================================

At its most basic level, JSDoc is used like so:

.. code-block:: sh

   /path/to/jsdoc yourSourceCodeFile.js anotherSourceCodeFile.js ...

where ``...`` are paths to other files to generate documentation for.

Additionally, one may provide the path to a `Markdown file`_ (ending in “.md”)
or a file named “README”, and this will be added to the documentation on
the front page. See :ref:`including-readme`.

JSDoc supports a number of command-line options, many of which have both
long and short forms. Alternatively, the command-line options may be :ref:`configuring-jsdoc`
given to JSDoc. The command-line options are:

+-------------------------+---------------------------------------------+
|         Option          |                 Description                 |
+=========================+=============================================+
| ``-a <value>``,         | Only display symbols with the given         |
| ``--access <value>``    | ``access`` property: ``private``,           |
|                         | ``protected``, ``public``, or               |
|                         | ``undefined``, or ``all`` for all access    |
|                         | levels. By default, all except ``private``  |
|                         | symbols are shown.                          |
+-------------------------+---------------------------------------------+
| ``-c <value>``,         | The path to a JSDoc                         |
| ``--configure <value>`` | :ref:`configuring-jsdoc`.                   |
|                         | Defaults to ``conf.json`` or                |
|                         | ``conf.json.EXAMPLE`` in the directory      |
|                         | where JSDoc is installed.                   |
+-------------------------+---------------------------------------------+
| ``-d <value>``,         | The path to the output folder for the       |
| ``--destination <value  | generated documentation. For JSDoc’s        |
| >``                     | built-in Haruki template, use ``console``   |
|                         | to dump data to the console. Defaults to    |
|                         | ``./out``.                                  |
+-------------------------+---------------------------------------------+
| ``--debug``             | Log information that can help debug issues  |
|                         | in JSDoc itself.                            |
+-------------------------+---------------------------------------------+
| ``-e <value>``,         | Assume this encoding when reading all       |
| ``--encoding <value>``  | source files. Defaults to ``utf8``.         |
+-------------------------+---------------------------------------------+
| ``-h``, ``--help``      | Display information about JSDoc’s           |
|                         | command-line options, then exit.            |
+-------------------------+---------------------------------------------+
| ``--match <value>``     | Only run tests whose names contain          |
|                         | ``value``.                                  |
+-------------------------+---------------------------------------------+
| ``--nocolor``           | When running tests, do not use color in the |
|                         | console output. On Windows, this option is  |
|                         | enabled by default.                         |
+-------------------------+---------------------------------------------+
| ``-p``, ``--private``   | Include symbols marked with the             |
|                         | :rst:dir:`@private` in                      |
|                         | the generated documentation. By default,    |
|                         | private symbols are not included.           |
+-------------------------+---------------------------------------------+
| ``-P``, ``--package``   | The ``package.json`` file that contains the |
|                         | project name, version, and other details.   |
|                         | Defaults to the first ``package.json`` file |
|                         | found in the source paths.                  |
+-------------------------+---------------------------------------------+
| ``--pedantic``          | Treat errors as fatal errors, and treat     |
|                         | warnings as errors. Defaults to ``false``.  |
+-------------------------+---------------------------------------------+
| ``-q <value>``,         | A query string to parse and store in the    |
| ``--query <value>``     | global variable ``env.opts.query``.         |
|                         | Example: ``foo=bar&baz=true``.              |
+-------------------------+---------------------------------------------+
| ``-r``, ``--recurse``   | Recurse into subdirectories when scanning   |
|                         | for source files and tutorials.             |
+-------------------------+---------------------------------------------+
| ``-R``, ``--readme``    | The ``README.md`` file to include in the    |
|                         | generated documentation. Defaults to the    |
|                         | first ``README.md`` file found in the       |
|                         | source paths.                               |
+-------------------------+---------------------------------------------+
| ``-t <value>``,         | The path to the template to use for         |
| ``--template <value>``  | generating output. Defaults to              |
|                         | ``templates/default``, JSDoc’s built-in     |
|                         | default template.                           |
+-------------------------+---------------------------------------------+
| ``-T``, ``--test``      | Run JSDoc’s test suite, and print the       |
|                         | results to the console.                     |
+-------------------------+---------------------------------------------+
| ``-u <value>``,         | Directory in which JSDoc should search for  |
| ``--tutorials <value>`  | tutorials. If omitted, no tutorial pages    |
| `                       | will be generated. See the `tutorial        |
|                         | instructions <about-tutorials.html>`__ for  |
|                         | more information.                           |
+-------------------------+---------------------------------------------+
| ``-v``, ``--version``   | Displays JSDoc’s version number, then       |
|                         | exits.                                      |
+-------------------------+---------------------------------------------+
| ``--verbose``           | Log detailed information to the console as  |
|                         | JSDoc runs. Defaults to ``false``.          |
+-------------------------+---------------------------------------------+
| ``-X``, ``--explain``   | Dump all doclets to the console in JSON     |
|                         | format, then exit.                          |
+-------------------------+---------------------------------------------+

Examples
----------

Generate documentation for files in the ``./src`` directory,
using the configuration file ``/path/to/my/conf.json``,
and save the output in the ``./docs`` directory:

.. code-block:: sh

   /path/to/jsdoc src -r -c /path/to/my/conf.json -d docs

Run all JSDoc tests whose names include the word ``tag``, and log information about each test:

.. code-block:: sh

   /path/to/jsdoc -T --match tag --verbose


.. _Markdown file: http://daringfireball.net/projects/markdown/
