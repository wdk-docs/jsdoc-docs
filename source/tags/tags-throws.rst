Syntax
------

-  ``@throws free-form description``
-  ``@throws {<type>}``
-  ``@throws {<type>} free-form description``

Overview
--------

The @throws tag allows you to document an error that a function might
throw. You can include the @throws tag more than once in a single JSDoc
comment.

Examples
--------

{% example “Using the @throws tag with a type” %}

.. code:: js

   /**
    * @throws {InvalidArgumentException}
    */
   function foo(x) {}

{% endexample %}

{% example “Using the @throws tag with a description” %}

.. code:: js

   /**
    * @throws Will throw an error if the argument is null.
    */
   function bar(x) {}

{% endexample %}

{% example “Using the @throws tag with a type and description” %}

.. code:: js

   /**
    * @throws {DivideByZero} Argument x must be non-zero.
    */
   function baz(x) {}

{% endexample %}
