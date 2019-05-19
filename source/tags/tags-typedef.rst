@typedef
=============================

Syntax
------

``@typedef [<type>] <namepath>``

Overview
--------

The @typedef tag is useful for documenting custom types, particularly if
you wish to refer to them repeatedly. These types can then be used
within other tags expecting a type, such as
[@type]\ `type-tag <tags-type.html>`__ or
[@param]\ `param-tag <tags-param.html>`__.

Use the [@callback]\ `callback-tag <tags-callback.html>`__ tag to
document the type of callback functions.

Examples
--------

This example defines a union type for parameters that can contain either
numbers or strings that represent numbers.

{% example “Using the @typedef tag” %}

.. code-block:: js

   /**
    * A number, or a string containing a number.
    * @typedef {(number|string)} NumberLike
    */

   /**
    * Set the magic number.
    * @param {NumberLike} x - The magic number.
    */
   function setMagicNumber(x) {
   }

{% endexample %}

This example defines a more complex type, an object with several
properties, and sets its namepath so it will be displayed along with the
class that uses the type. Because the type definition is not actually
exposed by the class, it is customary to document the type definition as
an inner member.

{% example “Using @typedef to document a complex type for a class” %}

.. code-block:: js

   /**
    * The complete Triforce, or one or more components of the Triforce.
    * @typedef {Object} WishGranter~Triforce
    * @property {boolean} hasCourage - Indicates whether the Courage component is present.
    * @property {boolean} hasPower - Indicates whether the Power component is present.
    * @property {boolean} hasWisdom - Indicates whether the Wisdom component is present.
    */

   /**
    * A class for granting wishes, powered by the Triforce.
    * @class
    * @param {...WishGranter~Triforce} triforce - One to three {@link WishGranter~Triforce} objects
    * containing all three components of the Triforce.
    */
   function WishGranter(triforce) {}

{% endexample %}
