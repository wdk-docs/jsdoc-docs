Syntax
------

``@yields [{type}] [description]``

Overview
--------

The ``@yields`` tag documents the value that is yielded by a generator
function. This tag is available in JSDoc 3.5.0 and later.

If you are documenting a regular function, use the ```@returns``
tag <tags-returns.html>`__ instead of this tag.

Examples
--------

{% example “@yields tag with a type” %}

.. code:: js

   /**
    * Generate the Fibonacci sequence of numbers.
    *
    * @yields {number}
    */
   function* fibonacci() {}

{% endexample %}

{% example “@yields tag with a type and description” %}

.. code:: js

   /**
    * Generate the Fibonacci sequence of numbers.
    *
    * @yields {number} The next number in the Fibonacci sequence.
    */
   function* fibonacci() {}

{% endexample %}
