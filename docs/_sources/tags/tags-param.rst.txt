@param
=============================

.. rst:directive:: @param

   :Overview:


      The :rst:dir:`@param` tag provides the name, type, and description of a
      function parameter.

      The :rst:dir:`@param` tag requires you to specify the name of the parameter you
      are documenting. You can also include the parameter’s type, enclosed in
      curly brackets, and a description of the parameter.

      The parameter type can be a built-in JavaScript type, such as ``string``
      or ``Object``, or a `JSDoc namepath <about-namepaths.html>`__ to another
      symbol in your code. If you have written documentation for the symbol at
      that namepath, JSDoc will automatically link to the documentation for
      that symbol. You can also use a type expression to indicate, for
      example, that a parameter is not nullable or can accept any type; see
      the `@type  tag documentation <tags-type.html>`__ for details.

      If you provide a description, you can make the JSDoc comment more
      readable by inserting a hyphen before the description. Be sure to
      include a space before and after the hyphen.

   :Examples:

      Names, types, and descriptions
      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

      The following examples show how to include names, types, and
      descriptions in a :rst:dir:`@param` tag.

      .. code-block:: js
         :caption: Name only

         /**
          * @param somebody
          */
         function sayHello(somebody) {
             alert('Hello ' + somebody);
         }

      .. code-block:: js
         :caption: Name and type

         /**
          * @param {string} somebody
          */
         function sayHello(somebody) {
             alert('Hello ' + somebody);
         }

      .. code-block:: js
         :caption: Name, type, and description

         /**
          * @param {string} somebody Somebody's name.
          */
         function sayHello(somebody) {
             alert('Hello ' + somebody);
         }

      You can add a hyphen before the description to make it more readable. Be
      sure to include a space before and after the hyphen.

      .. code-block:: js
         :caption: Name, type, and description, with a hyphen before the description

         /**
          * @param {string} somebody - Somebody's name.
          */
         function sayHello(somebody) {
             alert('Hello ' + somebody);
         }

      Parameters with properties
      ~~~~~~~~~~~~~~~~~~~~~~~~~~

      If a parameter is expected to have a specific property, you can document
      that property by providing an additional :rst:dir:`@param` tag. For example, if
      an ``employee`` parameter is expected to have ``name`` and
      ``department`` properties, you can document it as follows:

      .. code-block:: js
         :caption: Documenting a parameter’s properties

         /**
          * Assign the project to an employee.
          * @param {Object} employee - The employee who is responsible for the project.
          * @param {string} employee.name - The name of the employee.
          * @param {string} employee.department - The employee's department.
          */
         Project.prototype.assign = function(employee) {
             // ...
         };

      If a parameter is destructured without an explicit name, you can give
      the object an appropriate one and document its properties.

      .. code-block:: js
         :caption: Documenting a destructuring parameter

         /**
          * Assign the project to an employee.
          * @param {Object} employee - The employee who is responsible for the project.
          * @param {string} employee.name - The name of the employee.
          * @param {string} employee.department - The employee's department.
          */
         Project.prototype.assign = function({ name, department }) {
             // ...
         };

      You can also combine this syntax with JSDoc’s syntax for array
      parameters. For example, if multiple employees can be assigned to a
      project:

      .. code-block:: js
         :caption: Documenting properties of values in an array

         /**
          * Assign the project to a list of employees.
          * @param {Object[]} employees - The employees who are responsible for the project.
          * @param {string} employees[].name - The name of an employee.
          * @param {string} employees[].department - The employee's department.
          */
         Project.prototype.assign = function(employees) {
             // ...
         };

      Optional parameters and default values
      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

      The following examples show how to indicate that a parameter is optional
      and has a default value.

      .. code-block:: js
         :caption: An optional parameter (using JSDoc syntax)

         /**
          * @param {string} [somebody] - Somebody's name.
          */
         function sayHello(somebody) {
             if (!somebody) {
                 somebody = 'John Doe';
             }
             alert('Hello ' + somebody);
         }

      .. code-block:: js
         :caption: An optional parameter (using Google Closure Compiler syntax)

         /**
          * @param {string=} somebody - Somebody's name.
          */
         function sayHello(somebody) {
             if (!somebody) {
                 somebody = 'John Doe';
             }
             alert('Hello ' + somebody);
         }

      .. code-block:: js
         :caption: An optional parameter and default value

         /**
          * @param {string} [somebody=John Doe] - Somebody's name.
          */
         function sayHello(somebody) {
             if (!somebody) {
                 somebody = 'John Doe';
             }
             alert('Hello ' + somebody);
         }

      Multiple types and repeatable parameters
      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

      The following examples show how to use type expressions to indicate that
      a parameter can accept multiple types (or any type), and that a
      parameter can be provided more than once. See the `@type  tag
      documentation <tags-type.html>`__ for details about the type expressions
      that JSDoc supports.

      .. code-block:: js
         :caption: Allows one type OR another type (type union)

         /**
          * @param {(string|string[])} [somebody=John Doe] - Somebody's name, or an array of names.
          */
         function sayHello(somebody) {
             if (!somebody) {
                 somebody = 'John Doe';
             } else if (Array.isArray(somebody)) {
                 somebody = somebody.join(', ');
             }
             alert('Hello ' + somebody);
         }

      .. code-block:: js
         :caption: Allows any type

         /**
          * @param {*} somebody - Whatever you want.
          */
         function sayHello(somebody) {
             console.log('Hello ' + JSON.stringify(somebody));
         }

      .. code-block:: js
         :caption: Allows a parameter to be repeated

         /**
          * Returns the sum of all numbers passed to the function.
          * @param {...number} num - A positive or negative number.
          */
         function sum(num) {
             var i = 0, n = arguments.length, t = 0;
             for (; i &lt; n; i++) {
                 t += arguments[i];
             }
             return t;
         }

      Callback functions
      ~~~~~~~~~~~~~~~~~~

      If a parameter accepts a callback function, you can use the
      `@callback  tag <tags-callback.html>`__ to define a callback type,
      then include the callback type in the :rst:dir:`@param` tag.

      .. code-block:: js
         :caption: Parameters that accept a callback

         /**
          * This callback type is called `requestCallback` and is displayed as a global symbol.
          *
          * @callback requestCallback
          * @param {number} responseCode
          * @param {string} responseMessage
          */

         /**
          * Does something asynchronously and executes the callback on completion.
          * @param {requestCallback} cb - The callback that handles the response.
          */
         function doSomethingAsynchronously(cb) {
             // code
         };
