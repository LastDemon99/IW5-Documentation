Loops
=====

A loop, in general—whether it's a ``for``, ``while``, or ``foreach`` loop—is a control flow structure in programming used to repeat a block of code based on certain conditions.

**While:** A ``while`` loop is used to repeat a block of code as long as a specific condition is met.

.. code:: c

    number = 5;
    while (number) 
    {
        print("Number equals: " + number);
        number--;
    }

    print("The while loop has ended."); // this will only be seen if the loop ended

    /*

    5 prints should have been made:
    "Number equals: 5"
    "Number equals: 4"
    "Number equals: 3"
    "Number equals: 2"
    "Number equals: 1"
    "The while loop has ended."

    */

**For:** For loops can be infinite or run only until a specific condition is met; the latter is used when the exact number of iterations is known in advance.

.. code:: c

    for(;;) 
    {
        print("Infinite loop!");
        wait 0.05; // If this ``wait`` is called on a non-threaded function, it will hold the server/entity. 
    }

A loop that will stop when ``i`` is no longer less than ``var``, where var is equal to ``10``

.. code:: c

    var = 10;
    for(i = 0; i < var; i++) 
    {
        print("Looping! " + i);
    }

A loop that will stop when ``i`` is no longer greater than ``var``, where var is equal to ``0``

.. code:: c

    var = 0;
    for(i = 10; i > var; i--) 
    {
        print("Looping! " + i);
    }

A loop that will iterate through all lookups by row in column 1 of a table until no value is found.

.. code:: c

    table = "mp/camotable.csv";
    for (row = 0; tableLookupByRow(table, row, 1) != ""; row++)
		print(tableLookupByRow(table, row, 1));

**Foreach:** Specifically used to iterate over elements in a collection, eliminating the need for an index to access each element.

.. code:: c

    foreach(something in array)
    {
        // Do something
    }

.. code:: c

    foreach(player in level.players) // "For every player in the game"
    {
        player giveWeapon("iw5_usp45_mp"); // Give a usp
    }

This code creates an associative array, assigns values to string keys, and uses a foreach loop to print each key and its value.

.. code:: c

    newarray = [];
    newarray["hi"] = 10;
    newarray["test"] = 5;

    foreach (index, value in newarray)
    {
        print(index);
        print(value);
    }

Within loops, you can also use reserved words such as ``break`` or ``continue``.

**break:** Used to immediately exit the loop and resume code execution after the loop.

.. code:: c

    i = 0;
    for (i; i < 10; i++) 
    {
        if (i == 5)
            break;        
    }

print("i is equal to 5, not 10: " + i);

**continue:** Used inside a loop to skip the rest of the code in the current iteration and jump to the next iteration.

.. code:: c

    for (i = 0; i < 10; i++) 
    {
        //print only even numbers

        if (i % 2 != 0)
            continue; //skip odd

        print(i);
    }
