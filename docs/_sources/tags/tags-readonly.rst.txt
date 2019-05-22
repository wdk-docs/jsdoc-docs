@read
=============================

.. rst:directive:: @readonly

   :Syntax: ``@protected [{typeExpression}]``
   :Overview:

      The @readonly tag indicates that a symbol is intended to be read-only.
      Note this is for the purpose of documentation only - JSDoc won’t check
      whether you’ve *actually* treated the symbol as read-only in your code.

   :Examples:

      .. code-block:: js
         :caption: Using the @readonly tag

         /**
          * A constant.
          * @readonly
          * @const {number}
          */
         const FOO = 1;

      .. code-block:: js
         :caption: Using the @readonly tag with a getter

         /**
          * Options for ordering a delicious slice of pie.
          * @namespace
          */
         var pieOptions = {
             /**
              * Plain.
              */
             plain: 'pie',
             /**
              * A la mode.
              * @readonly
              */
             get aLaMode() {
                 return this.plain + ' with ice cream';
             }
         };
