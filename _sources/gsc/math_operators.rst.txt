Math operators
==============
Mathematical operators are special symbols used to perform arithmetic operations on numerical values. These operators allow you to perform basic mathematical operations.

.. code:: c

    +  :: Addition
    -  :: Subtraction
    *  :: Multiplication
    /  :: Division
    %  :: Modulus
    =  :: Equals
    ++ :: One Increment
    -- :: One Decrement
    += :: Incrementation
    -= :: Decrementation

Increment & decrement
=====================

.. code:: c

    var++;      // Set var to var + 1
    var--;      // Set var to var - 1
    var += 5;   // Set var to var + 5
    var -= 5;   // Set var to var - 5

The ``+`` and ``+=`` operator can also be used to concatenate text

.. code:: c

    var = "hi";
    var += "!"; // Set var to concat var + "!"
