Template
========

This is what a basic script would look like

.. code:: c

    init()
    {
        level thread onPlayerConnect();
    }

    onPlayerConnect()
    {
        level endon("game_ended");

        for (;;)
        {
            level waittill("connected", player);
            
            player thread onPlayerSpawn();
        }
    }

    onPlayerSpawn()
    {
        self endon("disconnect");
        
        for(;;)
        {
            self waittill("spawned_player");

            // Do something       
        }
    }
