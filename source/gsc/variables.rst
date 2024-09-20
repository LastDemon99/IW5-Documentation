Variable Types
==============

Variables are used to store data for the duration of the game. They come in various types and can be utilized in different ways:

- **Integers:** Store whole numbers, such as ``1`` , ``2`` , ``-5`` , etc.

- **Floats:** Store decimal numbers, such as ``3.14`` , ``2.5`` , ``-0.75`` , etc.

- **Strings:** Store text, such as ``"hello"`` , ``"game"`` , ``"number one"`` , etc.

- **Booleans:** Represent true/false values, such as ``true`` or ``false`` .

- **Arrays:** Structures that store multiple values, e.g., ``[1, 3.5, "hi", true]`` .

- **Associative Arrays:** Structures that store values in an ordered list by means of a key. Internally, the key is converted into a numerical index to access the corresponding element, e.g., ``Groups["Admin"]`` , ``Groups["Moderator"]`` .

- **Vectors:** Data structures representing an ordered sequence of elements of the same type, arranged in a single dimension. They are used to represent directional magnitudes or quantities with magnitude and direction, e.g., ``(0, 0, 1)`` .

- **Structs:** Data structures that allow fields of different types to be grouped under the same name, e.g., ``sentry.health`` .

- **Entities:** Refers to objects within the game environment, such as players and dynamic objects, e.g., ``player.health`` . While their syntax is similar to structures, entities encompass not only multiple attributes but also behaviors.

Variable Declaration
====================

To declare a variable, simply type the name of the variable followed by an ``=`` sign to assign the desired value.

.. code:: c

    num = 1; // int

    num_2 = 0.5; // float

    msg = "hello"; // string

    game_start = true; // bool

    data = [num, num_2, msg]; // array

    Groups["Admin"] = [player1, player2, player3]; // associative array

    direction = (0, 0, 1000); // vector

    explosion = spawnStruct(); // struct
    explosion.fx = loadfx("explosions/tanker_explosion");
    explosion.origin = (0, 0, 0);
    explosion.sound = "cobra_helicopter_crash";

    entity = spawnEnt((0, 0, 0), "com_plasticcase_friendly", (0, 0, 0)); // entity
    entity.health = 999;

When a variable is declared but no value is assigned, its default value is ``undefined`` , indicating the absence of an assigned value. It can also be explicitly declared as ``undefined`` .

.. code:: c

    explosion.health // is undefined; not previously declared

    my_var = undefined; // explicitly declared as undefined

Variable Scopes
===============

**Local Variable:** Variable accessible only within the function where it was declared.

.. code:: c

    exampleFunction()
    {
        num = 0; // local variable
    }

**Global Variable:** Variable accessible from any function and from any gsc file.

.. code:: c

    level.num = 0; // global variable

**Struct Field:** Variable associated with a specific object and accessible only from that object.

.. code:: c

    self.num = 0; // struct field

Persistent Variable
===================
Variables that do not change with each script initialization you will have to access data structure assigned in the following way ``self.pers['key']`` & ``game['key']``

.. code:: c

    self.pers["num"] = 0; // local entity
    game["num"] = 0; // global
