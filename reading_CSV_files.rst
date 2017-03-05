.. _readingCSVfile:

=======================
Reading for a CSV file
=======================

Let us cover the reading of CSV files into memory.
One of the more popularly requested file types for reading into
memory is csv files, so let us cover them.
here I will just create a simple ``example.csv`` file

here are the contains of the csv file which is example.csv:
jake,black,03/06/2016
jane,brown,09/07/2016
jonh,white,08/12/2016

Just write a simple csv file like that.I gues i should also cover how to create a csv file.Just open your notepad and place the information above,then simple save it as a ``.csv`` this will tell windows how we want to save it.If you do this it will be converted into a an excel file.Moving on right along.

.. code-block:: python

    import csv
    
    with open('example.csv') as csvfile:
        readCSV = csv.reader(csvfile, delimiter=',')
        for row in readCSV:
            print(row)
            print(row[0])
            print(row[0],row[1],row[2],)


Make sure you save and run that.You will see that we have succesfully read that using the python.That mean we can manipulate the data which is in csv.let make the data more readable as very easy use and also add some more data on top.

.. code-block:: python

    import csv
    
    with open('example.csv') as csvfile:
        readCSV = csv.reader(csvfile, delimiter=',')
        dates = []
        colors = []
        for row in readCSV:
            color = row[3]
            date = row[0]
    
            dates.append(date)
            colors.append(color)
    
        print(dates)
        print(colors)
    

Now you want to maybe ask some questions with data...
what day was the color green let's ask?

.. code-block:: python

    import csv
    
    with open('example.csv') as csvfile:
        readCSV = csv.reader(csvfile, delimiter=',')
        dates = []
        colors = []
        for row in readCSV:
            color = row[3]
            date = row[0]
    
            dates.append(date)
            colors.append(color)
    
        print(dates)
        print(colors)
    
        # now, remember our lists?
    
        whatColor = input('What color do you wish to know the date of?:')
        coldex = colors.index(whatColor)
        theDate = dates[coldex]
        print('The date of',whatColor,'is:',theDate)


What if we enter something that is non-existent?oh you guessed it right we will get an error.
    


    
