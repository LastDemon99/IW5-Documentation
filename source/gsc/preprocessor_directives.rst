Include Directive
=================
The preprocessor directive ``#include <path>`` includes the contents of another gsc file. Used as libraries to include functions definitions.

.. code:: c

    #include common_scripts\utility;

    init()
    {
        print(cointoss()); // cointoss is in utility function
    }


Define Directive
================
The preprocessor directive ``#define <identifier> <value>`` is used to define constants or macros that the compiler will replace in your code.

.. code:: c

    #define HI "Hello!!"

    init()
    {
        print(HI);
    }

.. code:: console

   Output: Hello!!

.. code:: c

    #define SUM(x, y) ((x) + (y))

    init()
    {
        print(SUM(5, 10));
    }

.. code:: console

   Output: 15

.. code:: c

    #define VALUE 10
    #define PRINT_VALUE(x) print("The value is", (x))

    init()
    {
        PRINT_VALUE(VALUE);
    }

.. code:: console

   Output: The value is 10

Undef Directive
=================
Undefine a previously defined macro. Used to remove the previously definition. To define a macro with the same name you must first remove it.

.. code:: c

    #define VALUE "test"
    #undef VALUE
    #define VALUE 200

    init()
    {
        print(VALUE);
    }

.. code:: console

   Output: 200

Macro definitions accept two special operators ``#`` and ``##`` , the first replaces the parameter name with a literal and ``##`` operator concatenates two arguments leaving no blank spaces between them.

.. warning::
    - ``##`` operator I haven't been able to get it to stop giving me errors

.. code:: c

    #define ARG_STR(x) #x
    #define ARG_STR_CONCAT(x, y) ((#x) + (#y))

    // #define TEST(x, y) (x ## y)

    init()
    {
        print(ARG_STR(VALUE));
        print(ARG_STR_CONCAT(HE, LLO));
    }

.. code:: console

    Output[0]: VALUE
    Output[1]: HELLO

.. note::
    I was going to continue with the #if, #else, #endif directives but I won't since plutonium in iw5 does not offer support for including headers or running a macro within the preprocessing region.