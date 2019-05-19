@public
=============================

Overview
--------

The ``@public`` tag indicates that a symbol should be documented as if
it were public.

By default, JSDoc treats all symbols as public, so using this tag does
not normally affect the generated documentation. However, you may prefer
to use the ``@public`` tag explicitly so it is clear to others that you
intended to make the symbol public.

In JSDoc 3, the ``@public`` tag does *not* affect a symbol’s scope. Use
the ```@instance`` <tags-instance.html>`__,
```@static`` <tags-static.html>`__, and
```@global`` <tags-global.html>`__ tags to change a symbol’s scope.

Examples
--------

{% example “Using the @public tag” %}

.. code-block:: js

   /**
    * The Thingy class is available to all.
    * @public
    * @class
    */
   function Thingy() {
       /**
        * The Thingy~foo member. Note that 'foo' is still an inner member
        * of 'Thingy', in spite of the @public tag.
        * @public
        */
       var foo = 0;
   }

{% endexample %}
