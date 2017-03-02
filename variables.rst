..variables:

===============
Variables
===============

Variables are very useful in python programming.A variable in simple terms is a any name the your choice that you 
store data inside.In python we use the  ``=``  to assign data to a variable.There are two types of data and these 
often confuse people.

When users begin using functions, they can quickly become confused when it comes
to global and local variables.Getting the dreadfull error ``variable is not defined`` 
even when they clearly see that it is or so they think.
These terms of **global** and **local**
correspond to a variable's reach within a script or program.

A **global variable** is one that can be accessed anywhere.

A **local variable** is the opposite, it can only be accessed within its frame.

The difference is that global variables can be accessed locally, but not modified
locally  inherently.

A local variable cannot be accessed globally, inherently.
Now, don't worry about committing that to memory right now, I think it makes a lot more sense when you just see and
do it, so let's do that. 


Global Variable
---------------

``x = 6``

This variable has no parent function, but is actually **NOT** a global variable.
It just so happens that it is committed to memory before the function is called
so we are able to iterate, or call it out, but we cannot do much else.


.. code-block:: python

    
    x = 6
    
    def example():
        # z, however, is a local variable.  
        z = 5
        # this works
        print(z)


    
``example()`` this does not, which often confuses people, because z has been defined
and successfully even was called, the problem is that it is a local
variable only, and you are attempting to access it globally.

``print(z)``

next up is an example that i've seen cause even more trouble, and that's.the attempt to play with a
global variable locally. The reason why this is so troubling is because you can access it... you just 
cannot play with it, and this often frustrates people for a while.

.. code-block:: python

    x = 6
    
    def example2():
        # works
        print(x)
        print(x+5)

but then what happens when we go to modify:
    ``x+=6``

so there we attempted to take the x var and add 6 to it... but now we are told that we cannot, as we're referencing 
the variable before its assignment.


*So now you know the rules, what can we do about it?*

.. code-block:: python

    x = 6
    
    def example3():
        # what we do here is defined x as a global variable. 
        global x
        # now we can:
        print(x)
        x+=5
        print(x)





So that is all for global and local, though I will show 1 last thing.
Sometimes you want a sort of global variable as a starting point, but
you do not actually wish to modify the "global" variable outside of the
functions themselves. You can just do the following:

.. code-block:: python


    def example4():
        globx = x
        # now we can:
        print(globx)
        globx+=5
        print(globx)


and that's it!

Variables can really give you massive problems.l really hope that this will take care of everything involving
variable errors. Ofcourse there is so documentation out side of this but l think this is good enough to get you start.
