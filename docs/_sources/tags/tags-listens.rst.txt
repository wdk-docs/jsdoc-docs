@listens
=============================

.. rst:directive:: @listens

   :Syntax: `@listens <eventName>`
   :Overview:

      The :rst:dir:`@listens` tag indicates that a symbol listens for the specified
      event. Use the :rst:dir:`@event` to document the event’s content.

   :Example:

      The following example shows how to document an event named
      ``module:hurler~event:snowball``, as well as a method named
      ``module:playground/monitor.reportThrowage`` that listens for the event.

      .. code-block:: js
         :caption: Documenting an event and its listener

         define('hurler', [], function () {
             /**
              * Event reporting that a snowball has been hurled.
              *
              * @event module:hurler~snowball
              * @property {number} velocity - The snowball's velocity, in meters per second.
              */

             /**
              * Snowball-hurling module.
              *
              * @module hurler
              */
             var exports = {
                 /**
                  * Attack an innocent (or guilty) person with a snowball.
                  *
                  * @method
                  * @fires module:hurler~snowball
                  */
                 attack: function () {
                     this.emit('snowball', { velocity: 10 });
                 }
             };

             return exports;
         });

         define('playground/monitor', [], function () {
             /**
              * Keeps an eye out for snowball-throwers.
              *
              * @module playground/monitor
              */
             var exports = {
                 /**
                  * Report the throwing of a snowball.
                  *
                  * @method
                  * @param {module:hurler~event:snowball} e - A snowball event.
                  * @listens module:hurler~event:snowball
                  */
                 reportThrowage: function (e) {
                     this.log('snowball thrown: velocity ' + e.velocity);
                 }
             };

             return exports;
         });
