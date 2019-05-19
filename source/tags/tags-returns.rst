Syntax
------

``@returns [{type}] [description]``

Overview
--------

The ``@returns`` tag documents the value that a function returns.

If you are documenting a generator function, use the ```@yields``
tag <tags-yields.html>`__ instead of this tag.

Examples
--------

{% example “Return value with a type” %}

.. code:: js

   /**
    * Returns the sum of a and b
    * @param {number} a
    * @param {number} b
    * @returns {number}
    */
   function sum(a, b) {
       return a + b;
   }

{% endexample %}

{% example “Return value with a type and description” %}

.. code:: js

   /**
    * Returns the sum of a and b
    * @param {number} a
    * @param {number} b
    * @returns {number} Sum of a and b
    */
   function sum(a, b) {
       return a + b;
   }

{% endexample %}

{% example “Return value with multiple types” %}

.. code:: js

   /**
    * Returns the sum of a and b
    * @param {number} a
    * @param {number} b
    * @param {boolean} retArr If set to true, the function will return an array
    * @returns {(number|Array)} Sum of a and b or an array that contains a, b and the sum of a and b.
    */
   function sum(a, b, retArr) {
       if (retArr) {
           return [a, b, a + b];
       }
       return a + b;
   }

{% endexample %}

{% example “Returns a promise” %}

.. code:: js

   /**
    * Returns the sum of a and b
    * @param {number} a
    * @param {number} b
    * @returns {Promise<number>} Promise object represents the sum of a and b
    */
   function sumAsync(a, b) {
       return new Promise(function(resolve, reject) {
           resolve(a + b);
       });
   }

{% endexample %}
