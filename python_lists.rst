.. _python_lists:

===============
Python Lists
===============

Since lists are mutable, this means that we will be using lists for
things where we might intend to manipulate the list of data, so how
can we do that? Turns out we can do all sorts of things.
We can add, remove, count, sort, search, and do quite a few other things
to python lists. 

first we need an example list:

``x = [1,6,3,2,6,1,2,6,7]``

lets add something.We can do .append, which will add something to the end of the list, like:

``x.append(55)`` to  view the changes we have to call the print function.

``print(x)``


What if you have an exact place that you'd like to put something in a list?Use the following command to execute that.

``x.insert(2,33)`` again use the print function to call the function ``print(x)``

So the reason that went in the 3rd place, again, is because we start
at the zero element, then go 1, 2.. .and so on.

Now we can remove things... .remove will remove the first instance
of the value in the list. If it doesn't exist, there will be an error:

``x.remove(6)`` to check if it has been removed lets call the print function again.
``print(x)``

Next, remember how we can reference an item by index in a list? like:

``print(x[5])``

Well we can also search for this index, like so:

``print(x.index(1))``

Now here, we can see that it actually returned a ``0``, meaning the
first element was a 1.When we knew there was another with an index of 5.
So instead we might want to know before-hand how many examples there are.

``print(x.count(1))``

So we see there are actually ``2`` of them

We can also sort the list:

``x.sort()`` let call and see if the list has actually occurred.
``print(x)``


What if these were strings? like:
.. code-block:: python

    y = ['Jan','Dan','Bob','Alice','Jon','Jack']
    
    y.sort()
    print(y)

No problem there.You can also just reverse a list, but, before we go there, we should note that all of these manipulations are mutating the list. keep in mind that any
changes you make will modify the existing variable.




