.. _writing-files:

=================
Writing to a File
=================

It should be noted that there are two methods for saving data to a file, and
those are writing and appending. Writing to a file will write that bit
of data, whatever it is, solely, to the file. This means if there was anything
there before, it will be gone if you use write.

If you use append, then you will basically add to whatever is previously there.

Write
=====

Here we have some simple text, but we also threw in a ``\n`` to
denote a new line. This will start a newline in the file that we write to:

.. code-block:: python

    text = 'Sample Text to Save\nNew line!'

The next example notifies Python that you are opening the file ``exampleFile.txt``,
with the intention to write something to the file using ``'w'``.

.. code-block:: python

    saveFile = open('exampleFile.txt','w')

Now we need to write the ``text`` to the file:

.. code-block:: python

    saveFile.write(text)

It is important to remember to actually close the file, otherwise it will
hang for a while and could cause problems in your script:

.. code-block:: python

    saveFile.close()
