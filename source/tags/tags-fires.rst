@fires (synonyms: @emits)
=============================

.. rst:directive:: @fires

   :Synonyms: :rst:dir:`@emits`
   :Syntax: ``@fires <className>#[event:]<eventName>``
   :Overview:

      The @fires tag indicates that a method can fire a specified type of
      event when it is called. Use the [@event
      tag]\ `event-tag <tags-event.html>`__ to document the event’s content.

   :Examples:

      .. code-block:: js
         :caption: Method that fires a ‘drain’ event

         /**
          * Drink the milkshake.
          *
          * @fires Milkshake#drain
          */
         Milkshake.prototype.drink = function() {
             // ...
         };

.. rst:directive:: @emits

   :Synonyms: :rst:dir:`@fires`
