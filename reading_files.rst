.. _reading-files:

=============
Reading Files
=============

Now that you know how to write and append to files, we can learn how
to read from files! 

Similar to the syntax in :ref:`Writing to a File <writing-files>` using ``w``
for "write", ``r`` can be used for "read". You can just throw a ``.read()``
at the end of the ``open`` function call, and you get:

.. code-block:: python

    readMe = open('exampleFile.txt','r').read()
    print(readMe)

Now that is great and useful, but a lot of times people want to read by line.
There are a few things you can do here, but probably the easiest is to read
the file into a Python list:

.. code-block:: python
    readMe = open('exampleFile.txt','r').readlines()
    print(readMe)
