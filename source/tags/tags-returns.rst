@return (synonyms: @return)
=============================

.. rst:directive:: @returns

   :Synonyms: :rst:dir:`@return`
   :Syntax: ``@returns [{type}] [description]``

   :Overview:

      The :rst:dir:`@returns` tag documents the value that a function returns.

      If you are documenting a generator function, use the :rst:dir:`@yields` instead of this tag.

   :Examples:

      .. code-block:: js
         :caption: Return value with a type

         /**
          * Returns the sum of a and b
          * @param {number} a
          * @param {number} b
          * @returns {number}
          */
         function sum(a, b) {
             return a + b;
         }

      .. code-block:: js
         :caption: Return value with a type and description

         /**
          * Returns the sum of a and b
          * @param {number} a
          * @param {number} b
          * @returns {number} Sum of a and b
          */
         function sum(a, b) {
             return a + b;
         }

      .. code-block:: js
         :caption: Return value with multiple types

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

      .. code-block:: js
         :caption: Returns a promise

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

.. rst:directive:: @return

   :Synonyms: :rst:dir:`@returns`
