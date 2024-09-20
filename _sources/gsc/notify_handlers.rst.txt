Notify Handlers
===============
The ``notify``, ``endon``, and ``waittill`` are used together to monitor and handle events, notify, interrumpt or wait for specific actions to occur. These triggers must be associated with either the level or an entity to be called from different parts of the script or across different scripts.

- **Notify:** It is used to notify a specific event so that it can be detected by other parts of the code that are waiting for it. As the first argument, a string will be assigned that will serve as a key to identify it. 

.. code:: c

    level Notify("game_ended");

If necessary, we can also pass additional parameter.

.. code:: c

    self Notify("damage", 100, attacker);

- **Endon:** Used to interrupt the execution of the function block in case the specified event is notified.

.. code:: c

    level endon("game_ended"); //If level are notified of a "game_ended", the entire block will be interrupted

    for(;;)
    {
        iprintln("test");
        wait 0.5;
    }

- **Waittill:** is used to wait for the notification, so ``waittill`` will pause the script until the notification occurs. In order not to interrupt the entire execution of the script, remember to call with thread the function that has a waittill within its scope

.. code:: c

    self waittill("spawned_player"); //The entity in this case player waits "spawned_player" notify
    self iprintln("You are spawned"); //If the entity is notified it will allow the continuation of this line

Remember that ``notify`` can send multiple parameters, so ``waittill`` can receive them

.. code:: c

    level waittill("connected", player); //We wait for the notify and receive the player parameter.
    player iprintln("You has connected");
