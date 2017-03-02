.. _classes:

===============
Python Classes
===============

classes are very use full in python.They house functions under them.The best way to describe a
function is by using and example.In in this example we are going to create a calculator that can
add, multipy, divide and also subtract. *Functions which are under classes are called **methods** *

The way we are going to create this calculator is by using the methods to calculate each section.We
will name the methods in a way that will allow us to know what we are talking about.Which is something 
l always like to do when we are talking about naming things.


.. code-block:: python

    class calculator:
        
        def addition(x,y):
            added = x + y
            print(added)
            
        def subtraction(x,y):
            sub = x - y
            print(sub)
    
        def multiplication(x,y):
            mult = x * y
            print(mult)
    
        def division(x,y):
            div = x / y
            print(div)

To run this code we are going to use something that we have been using a lot.We first state the 
name of our function and then go ahead and state the name of the method which we want to run.Let jump
into the console/command prompt to see our results.



>>> calculator.subtraction(5,8)
-3
>>> calculator.multiplication(3,5)
15
>>> calculator.division(5,3)
1.6666666666666667
>>> calculator.addition(5,2)
7
>>> 

Again feel free to experiment and see what happens when you change numbers.You can also add other methods to so
what ever you want to do.I think this should be enough to cover the basics of classes. Ofcourse there is so much 
more to be learn when it comes to class,more to can get in the python.org docs.
