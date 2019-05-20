ECMAScript 2015 Classes
===========================

SDoc 3 makes it easy to document classes that follow the `ECMAScript
2015
specification <http://www.ecma-international.org/ecma-262/6.0/#sec-class-definitions>`__.
You don’t need to use tags such as :rst:dir:`@class` and :rst:dir:`@constructor` with
ES 2015 classes—JSDoc automatically identifies classes and their
constructors simply by parsing your code. ES 2015 classes are supported
in JSDoc 3.4.0 and later.

Documenting a simple class
--------------------------

The following example shows how to document a simple class with a
constructor, two instance methods, and one static method:

.. code-block:: js
   :caption: Simple ES 2015 class

   /** Class representing a point. */
   class Point {
       /**
        * Create a point.
        * @param {number} x - The x value.
        * @param {number} y - The y value.
        */
       constructor(x, y) {
           // ...
       }

       /**
        * Get the x value.
        * @return {number} The x value.
        */
       getX() {
           // ...
       }

       /**
        * Get the y value.
        * @return {number} The y value.
        */
       getY() {
           // ...
       }

       /**
        * Convert a string containing two comma-separated numbers into a point.
        * @param {string} str - The string containing two comma-separated numbers.
        * @return {Point} A Point object.
        */
       static fromString(str) {
           // ...
       }
   }

You can also document classes that are defined in a class expression,
which assigns the class to a variable or constant:

.. code-block:: js
   :caption: ES 2015 class expression

   /** Class representing a point. */
   const Point = class {
       // and so on
   }

Extending classes
-----------------

When you use the ``extends`` keyword to extend an existing class, you
also need to tell JSDoc which class you’re extending. You do this with
the `@augments  (or :rst:dir:`@extends`) tag <tags-augments.html>`__.

For example, to extend the ``Point`` class shown above:

.. code-block:: js
   :caption: Extending an ES 2015 class

   /**
    * Class representing a dot.
    * @extends Point
    */
   class Dot extends Point {
       /**
        * Create a dot.
        * @param {number} x - The x value.
        * @param {number} y - The y value.
        * @param {number} width - The width of the dot, in pixels.
        */
       constructor(x, y, width) {
           // ...
       }

       /**
        * Get the dot's width.
        * @return {number} The dot's width, in pixels.
        */
       getWidth() {
           // ...
       }
   }
