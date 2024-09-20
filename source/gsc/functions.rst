Declaring Functions
===================
You can declare functions in GSC by giving them a name, followed by ``()`` and a closing ``{}`` at the end of the function.

.. code:: c

    myFunction()
    {
        print("^2My First Function!"); // print message on console
    }

You can also declare functions associated with an entity. To reference the entity within the function, use ``self``.

.. code:: c

    init()
    {
        foreach(player in level.players)
        {
            player myFunction();
        }
    }


    myFunction()
    {
        self iprintlnbold("^2My First Function!"); // print message in center of player screen
    }

When declaring functions we can also define the need to pass values when calling it to perform various operations, the ``arguments``.

.. code:: c
    
    sum(a, b)
    {
        print(a + b);
    }

In certain cases, for practical reasons, we may need arguments that can be ``undefined``. If a second argument is not provided when calling the function, it will be received as ``undefined`` and assigned a default value.

.. code:: c

    init()
    {
        attachs = getRandomAttachs("iw5_usp45");
    }

    getRandomAttachs(weapon, attachs_count)
    {

        if (!isDefined(attachs_count)) 
            attachs_count = 2;

        // Function logic

    }

Functions using ``return`` can return a value or interrupt their execution.

.. code:: c

    init()
    {
        print(sum(5, 10));
    }

    sum(a, b) //when calling it it will return the value
    {
        return a + b;
    }

    function()
    {
        if (!isPlayer(self) || self.team == "axis") //If this condition is met we directly interrupt the execution
            return;

        // Do something
    }

Calling Functions
=================
There are different ways to call a function.

**Sequential Call:** When a function is called sequentially, the script waits for the function to complete before continuing to execute the next command. This means that script execution temporarily pauses at the line where the function is called and does not continue until the function has finished executing.

.. code:: c

    myFunction(); // The script stops here and executes the() function before continuing to the next line.

**Thread Call:** In contrast, when a thread function is called, script execution does not stop at the line where the function call is made. Instead, the script continues to run while the function executes in the other thread. This allows the script to proceed without waiting for the function to finish.

.. code:: c

    thread myFunction(); // This will start the() function but continue executing the next line.

**Associated Functions:** Functions can also be associated with objects, helping to organize code more clearly. This makes it easier to understand which actions or behaviors are related to each object.

.. code:: c

    ent myFunction();

.. code:: c

    ent thread myFunction();

To send arguments we will simply write the values separated by ``,``

.. code:: c

    sum(5, 10); //sending arguments to declared function

You can also declare a variable, assign a function to it, and then call the function using that variable.

.. code:: c

    level.myVarFunction = ::myFunction; //global var

To call the function assigned to a variable, you need to use the following syntax, where the variable must be inside ``[[ ]]``, followed by ``()``.

.. code:: c

    [[level.myVarFunction]](); //function called from another script file

To call functions defined in other gsc file we need to write ``path\filename`` followed by ``::`` and the function name.

.. code:: text

    comonm_scripts\utility::cointoss(); // 50/50 return true
