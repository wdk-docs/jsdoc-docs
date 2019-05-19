@type
=============================

Syntax
------

``@type {typeName}``

Overview
--------

The @type tag allows you to provide a type expression identifying the
type of value that a symbol may contain, or the type of value returned
by a function. You can also include type expressions with many other
JSDoc tags, such as the [@param tag]\ `param-tag <tags-param.html>`__.

A type expression can include the JSDoc namepath to a symbol (for
example, ``myNamespace.MyClass``); a built-in JavaScript type (for
example, ``string``); or a combination of these. You can use any `Google
Closure Compiler type
expression <https://github.com/google/closure-compiler/wiki/Annotating-JavaScript-for-the-Closure-Compiler#type-expressions>`__,
as well as several other formats that are specific to JSDoc.

If JSDoc determines that a type expression is invalid, it will display
an error and stop running. You can turn this error into a warning by
running JSDoc with the ``--lenient`` option.

**Note**: Full support for Google Closure Compiler-style type
expressions is available in JSDoc 3.2 and later. Earlier versions of
JSDoc included partial support for Closure Compiler type expressions.

Each type is specified by providing a type expression, using one of the
formats described below. Where appropriate, JSDoc will automatically
create links to the documentation for other symbols. For example,
``@type {MyClass}`` will link to the MyClass documentation if that
symbol has been documented.

.. raw:: html

   <table id="jsdoc-types" name="jsdoc-types">

.. raw:: html

   <tr>

.. raw:: html

   <th>

Type name

.. raw:: html

   </th>

.. raw:: html

   <th>

Syntax examples

.. raw:: html

   </th>

.. raw:: html

   <th>

Description

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Symbol name (name expression)

.. raw:: html

   </td>

.. raw:: html

   <td>

{% example %}

.. raw:: html

   <pre class="prettyprint"><code>{boolean}
   {myNamespace.MyClass}
   </code></pre>

{% endexample %}

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: html

   <p>

Specifies the name of a symbol. If you have documented the symbol, JSDoc
creates a link to the documentation for that symbol.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Multiple types (type union)

.. raw:: html

   </td>

.. raw:: html

   <td>

{% example “This can be a number or a boolean.” %}

.. raw:: html

   <pre class="prettyprint"><code>{(number|boolean)}
   </code></pre>

{% endexample %}

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: html

   <p>

This means a value can have one of several types, with the entire list
of types enclosed in parentheses and separated by \|.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Arrays and objects (type applications and record types)

.. raw:: html

   </td>

.. raw:: html

   <td>

{% example “An array of MyClass instances.” %}

.. raw:: html

   <pre class="prettyprint"><code>{Array.&lt;MyClass&gt;}
   // or:
   {MyClass[]}
   </code></pre>

{% endexample %}

{% example “An object with string keys and number values:” %}

.. raw:: html

   <pre class="prettyprint"><code>{Object.&lt;string, number&gt;}
   </code></pre>

{% endexample %}

{% example “An object called ‘myObj’ with properties ‘a’ (a number), ‘b’
(a string) and ‘c’ (any type).” %}

.. raw:: html

   <pre class="prettyprint"><code>&#123;{a: number, b: string, c}} myObj
   // or:
   {Object} myObj
   {number} myObj.a
   {string} myObj.b
   {*} myObj.c
   </code></pre>

{% endexample %}

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: html

   <p>

JSDoc supports Closure Compiler’s syntax for defining array and object
types.

.. raw:: html

   <p>

.. raw:: html

   <p>

You can also indicate an array by appending [] to the type that is
contained in the array. For example, the expression string[] indicates
an array of strings.

.. raw:: html

   </p>

.. raw:: html

   <p>

For objects that have a known set of properties, you can use Closure
Compiler’s syntax for documenting record types. You can document each
property individually, which enables you to provide more detailed
information about each property.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Nullable type

.. raw:: html

   </td>

.. raw:: html

   <td>

{% example “A number or null.” %}

.. raw:: html

   <pre class="prettyprint"><code>{?number}
   </code></pre>

{% endexample %}

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: html

   <p>

This indicates that the type is either the specified type, or null.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Non-nullable type

.. raw:: html

   </td>

.. raw:: html

   <td>

{% example “A number, but never null.” %}

.. raw:: html

   <pre class="prettyprint"><code>{!number}
   </code></pre>

{% endexample %}

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: html

   <p>

Indicates that the value is of the specified type, but cannot be null.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Variable number of that type

.. raw:: html

   </td>

.. raw:: html

   <td>

{% example “This function accepts a variable number of numeric
parameters.” %}

.. raw:: html

   <pre class="prettyprint"><code>@param {...number} num
   </code></pre>

{% endexample %}

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: html

   <p>

Indicates that the function accepts a variable number of parameters, and
specifies a type for the parameters. For example:

.. raw:: html

   </p>

{% example %}

.. raw:: html

   <pre class="prettyprint"><code>/**
    * Returns the sum of all numbers passed to the function.
    * @param {...number} num A positive or negative number
    */
   function sum(num) {
       var i=0, n=arguments.length, t=0;
       for (; i&lt;n; i++) {
           t += arguments[i];
       }
       return t;
   }
   </code></pre>

{% endexample %}

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Optional parameter

.. raw:: html

   </td>

.. raw:: html

   <td>

{% example “An optional parameter named foo.” %}

.. raw:: html

   <pre class="prettyprint"><code>@param {number} [foo]
   // or:
   @param {number=} foo
   </code></pre>

{% endexample %}

{% example “An optional parameter foo with default value 1.” %}

.. raw:: html

   <pre class="prettyprint"><code>@param {number} [foo=1]
   </code></pre>

{% endexample %}

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: html

   <p>

Indicates that the parameter is optional. When using JSDoc’s syntax for
optional parameters, you can also indicate the value that will be used
if a parameter is omitted.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Callbacks

.. raw:: html

   </td>

.. raw:: html

   <td>

{% example %}

.. raw:: html

   <pre class="prettyprint"><code>/**
    * @callback myCallback
    * @param {number} x - ...
    */

   /** @type {myCallback} */
   var cb;
   </code></pre>

{% endexample %}

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: html

   <p>

Document a callback using the @callback tag. The syntax is identical to
the @typedef tag, except that a callback’s type is always “function.”

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Type definitions

.. raw:: html

   </td>

.. raw:: html

   <td>

{% example “Documenting a type with properties ‘id’, ‘name’, ‘age’.” %}

.. raw:: html

   <pre class="prettyprint"><code>/**
    * @typedef PropertiesHash
    * @type {object}
    * @property {string} id - an ID.
    * @property {string} name - your name.
    * @property {number} age - your age.
    */

   /** @type {PropertiesHash} */
   var props;
   </code></pre>

{% endexample %}

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: html

   <p>

You can document complex types using the @typedef tag, then refer to the
type definition elsewhere in your documentation.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

Examples
--------

{% example “Example” %}

.. code-block:: js

   /** @type {(string|Array.<string>)} */
   var foo;
   /** @type {number} */
   var bar = 1;

{% endexample %}

In many cases, you can include a type expression as part of another tag,
rather than including a separate @type tag in your JSDoc comment.

{% example “Type expressions can accompany many tags.” %}

.. code-block:: js

   /**
    * @type {number}
    * @const
    */
   var FOO = 1;

   // same as:

   /** @const {number} */
   var FOO = 1;

{% endexample %}
