This repository contains the user documentation for `JSDoc
3 <https://github.com/jsdoc/jsdoc>`__. Use this repository to report
documentation bugs, and to submit pull requests for improving the docs.

If you just want to read the documentation, please visit `Use
JSDoc <https://jsdoc.app/>`__.

Contributing to the documentation
---------------------------------

The HTML docs are generated with
`Metalsmith <https://www.metalsmith.io/>`__ and
`Gulp <https://gulpjs.com/>`__. If you’d like to contribute to the docs,
make sure Node.js and npm are installed, then follow these steps:

1. Clone this repository:

   ::

       git@github.com:jsdoc3/jsdoc3.github.com.git

2. Install Bower and Gulp globally:

   ::

       npm install -g gulp
       npm install -g bower

3. Install the dependencies:

   ::

       npm install
       bower install

4. Make your changes in the ``content`` directory, which contains the
   source files for the docs.

   The first few lines of each source file contain
   `YAML <https://www.yaml.org/spec/1.2/spec.html>`__ front matter,
   which is metadata in
   `YAML <https://www.yaml.org/spec/1.2/spec.html>`__ format. If you
   need to use the character ``@`` or ``[`` at the start of a YAML
   value, you can escape it with a backslash. For example, write
   ``title: @class`` as ``title: \@class``.

5. Rebuild the HTML files:

   ::

       gulp

6. Review the updated HTML files, and make sure your changes look okay.
   In particular, if you edited the YAML front matter, make sure your
   changes are reflected in the generated HTML files.

7. Submit a pull request with your changes.

Legal stuff
-----------

Copyright (c) 2011-2014 by Michael Mathews and the JSDoc 3 documentation
`contributors <https://github.com/jsdoc/jsdoc.github.io/graphs/contributors>`__.

This repository is licensed under the `Creative Commons
Attribution-ShareAlike 3.0
Unported <https://creativecommons.org/licenses/by-sa/3.0/legalcode>`__
license. A copy of the license is included in the ```LICENSE``
file <https://github.com/jsdoc/jsdoc.github.io/LICENSE>`__.
