Logical Operators
=================
Operators used to compare data:

.. code:: c

    == :: Equal To
    != :: Not Equal To
    !  :: Negation (Not equal to)
    <  :: Less than
    >  :: Greater than
    <= :: Less or Equal to
    >= :: Greater or Equal to
    && :: And
    || :: Or

If Statements
=============
An ``if`` statement is used to verify whether some data satisfies certain conditions, and then to execute code block depending on the outcome.

.. code:: c

    if (3 < 5) 
    {
        print("Condition met"); // print a message in killing spree feed
    } 
    else 
    {
        print("Condition not met");
    }

This can also be used to check the conditions of player variables or just variables. 

.. code:: c

    self.condition = false;

    if (self.condition) 
    {
        // is true?
        self print("condition is true");
    } 
    else 
    {
        self print("condition is false");
    }

You can also use an ``else if`` & ``else`` conditions. This is used in a scenario where you want to check multiple comparisons.

.. code:: c

    if(var1 == var2)
    {
        // If above arguement is true
    }
    else if(!var1 && var3)
    {
        // If var1 is false but var3 is true
    }
    else
    {
        // If all other if statements were false
    }

Keep in mind that you will find different ways to write the code, for example, you can see that you can ignore the use of ``{ }``, in case you consider unnecessary and messy only if there is a single line. `remember to check that the indentation is correct`

.. code:: c

    if (condicion)
    {
        // A block with several lines of code
        print("Condition met");
        print("Condition met");
        print("Condition met");
    }

    if (condicion)
        print("Condition met"); // one line of code

    if (condicion)
        print("Condition met"); // one line of code
    else 
        print("Condition not met"); // one line of code


    if (condicion) print("Condition met"); // one line of code
    else print("Condition not met"); // one line of code

In GSC, you can check if a variable is defined as a condition. This function is called isDefined, it takes the variable as the only parameter, and returns `true/false.`

.. code:: c

    var = 5;
    var2 = 6;

    if (isDefined(var))
    {
        // var is defined as 5
        print("var is defined");
        var2 = undefined; // undefine var2
    }

    if (isDefined(var2))
    {
        // this should not be met as var2 was undefined.
        print("var2 is defined");
    } 
    else if (!isDefined(var2)) 
    {
        print("var2 is undefined");
    }

Switch
======
Switch cases are useful for checking the case of a lot of values. This is usually seen to be faster and recommended to use than a if statement.

.. code:: c

    value = 3;
    switch (value)
    {

        case 1:
            print("Value was 1");
            break;
        case 2:
            print("Value was 2");
            break;
        case 3:
            print("Value was 3");
            break;
        default:
            print("Value was not found");
            break;

    }

.. warning::
    - If you use a ``switch`` inside a loop, using ``break`` or ``return`` will terminate the entire flow, not just the ``switch``.
    
    ----

    - Sometimes the engine does what it wants and ignores the ``break`` or ``return`` behavior in a ``switch`` statement inside loops, just as it can give error in ``switch`` statement for no apparent reason and you will have to use ``if`` statements, these behaviors occur rarely and in environments where there is a lot of modularization.
