.. _test-driven-development:

=======================
Test Driven Development
=======================

Test-Driven Development, or TDD, is a development practice where writing the
tests for code is the first step of the development process. Test cases should
be small and focus on a specific desired outcome. TDD is an iterative practice
where each step is repeated until the new code project is sufficiently 
complete.

Instead of writing the code first and then adding tests to the code afterwards,
TDD forces the developer to think through the code requirements and various
design decisions before writing any functional code.


TDD Steps
=========

#. Write a Test: First write a small test case that covers a single piece of
   the new function's specifications. 
#. Run Test and Ensure Failure: Run the test and ensure that the new test fails
   in order to assert the test is running and failing properly. This rules out
   the possibility that the test is passing accidentally or was written
   incorrectly.
#. Write Functional Code: Write the code that is covered by the new test. This
   new code should allow the test to pass, ideally.
#. Run Test and Ensure Success: Run the test and ensure that the new test
   passes in order to assert that the functional code is working correctly.
#. Refactor Code: If there were problems during the test run, some refactoring
   may be needed. It is also possible in larger functions, files, or projects
   that the new functional code may be interfering with other tests, or that
   other sections of code are interfering with the new functional code. Some
   refactoring could be needed after a full test run.
#. Repeat: Iterate through the above 5 steps until the functional code is
   complete and all features and requirements have been achieved.


Python Testing Basics
=====================

We will cover writing `unit tests`_ in this document. A unit test is a way to
consider the scope of a test. In the first step in the section above, we
defined that "a small test case" should be written to cover a single piece of
a new function. This idea is called a ``unit test``.

Python comes with several helpful built-in testing features, including a
`unittest module`_, which we will be using in the example below.


Unittest Module Conventions
---------------------------

The Python interpreter comes with a unittest module. There are several testing
conventions that the unittest module follows:

#. Functions starting with ``test_`` are functions that should be run as tests.
#. The ``setUp()`` function is a reserved function to be used to prepare each
   test with certain settings or other function calls. ``setUp()`` runs at the
   beginning of each test in the testing class.
#. The ``tearDown()`` function is also a reserved function, similar to
   ``setUp()``, but is used to remove anything that needs to be cleaned up
   after an individual test completes. ``tearDown()`` runs at the end of each
   test in the testing class.
#. The three conventions mentioned above all take ``self`` as the first
   parameter and take no other arguments.


Testing Assertions
------------------

In addition to the conventions listed above, the unittest module also comes
with an array of testing assertions to be used to validate the behavior of the
code being tested. Some useful examples are:

- ``assertEqual(expected, actual)``: Asserts that the expected result is equal
  to the actual result.
- ``assertTrue(expression)``: Asserts that the provided expression is True.
- ``assertFalse(expression)``: Asserts that the provided expression is False.
- ``assertIsInstance(object, class)``: Asserts that the object is an instance
  of the given class.
- ``assertIn(first, second)``: Asserts that the first object is contained in
  the second object.
- ``assertRaises(Exception, function, *args, **kwargs)``: Asserts that the
  provided exception is raised when the provided function runs. The syntax for
  this assertion is a little different as the function's arguments should be
  passed as args/kwargs to the assertion instead of the function. See examples
  below for more information.

There are many other testing assertions provided by the unittest module that
can be utilized to cover a variety of testing use cases. For more information,
see `Python's list of assertion methods`_.


Running Tests
-------------

To run the tests, simply execute the following:

.. code-block:: python

    python -m unittest name-of-test-file


Testing Example
===============

Let's see how test classes work by writing some simple tests against the
`math.factorial`_ function. Some good places to start would be to test the
limits of the function: Negative numbers, 0, positive numbers, larger
numbers, and non-integral numbers, for example.

.. code-block:: python

    import math
    import unittest


    class TestMathFactorialFunction(unittest.TestCase):
        '''
        TestCases for the math.factorial function.
        '''

        def test_factorial_zero(self):
            '''
            Assert that providing 0 returns the value 1.
            '''
            call = math.factorial(0)
            self.assertEqual(1, call)

        def test_factorial_simple_integers(self):
            '''
            Assert that providing some simple numbers return correctly.
            '''
            call = math.factorial(1)
            self.assertEqual(1, call)

            call = math.factorial(2)
            self.assertEqual(2, call)

            call = math.factorial(5)
            self.assertEqual(120, call)

        def test_factorial_large_number(self):
            '''
            Assert that providing a larger number still works.
            '''
            call = math.factorial(20)
            self.assertEqual(2432902008176640000, call)

        def test_factorial_negative_number(self):
            '''
            Assert that a negative number raises a ValueError.
            '''
            self.assertRaises(ValueError, math.factorial, -10)

        def test_factorial_non_integral_number(self):
            '''
            Assert that a non-integral number raises a ValueError.
            '''
            self.assertRaises(ValueError, math.factorial, 1.5)


    if __name__ == '__main__':
        unittest.main()

.. _math.factorial: https://docs.python.org/3.4/library/math.html#math.factorial
.. _Python's list of assertion methods: https://docs.python.org/3.4/library/unittest.html#assert-methods
.. _unittest module: https://docs.python.org/3.4/library/unittest.html#module-unittest
.. _unit tests: https://en.wikipedia.org/wiki/Unit_testing
