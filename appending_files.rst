.. _appending-files:

===================
Appending to a File
===================

Alright, so now we get to appending a to a file in python. It should be
stated again that writing will clear the file and write just the data you
specify in the write operation. Appending will simply take what was already
there, and add to it.

That said, when you actually go to add to the file, you will still use
``write()``. You only specify that you will be appending instead of writing
when you open the file and specify your intentions.

Generally it is a good idea to start with a newline, since otherwise it will
append data on the same line as the file left off. You might want that, but
this example will use a new line.

Another option to use is to first append just a simple newline then append
what you want. (Don't forget to close the file!)

.. code-block:: python
    appendMe = '\nNew bit of information'

    appendFile = open('exampleFile.txt','a')
    appendFile.write(appendMe)
    appendFile.close()
