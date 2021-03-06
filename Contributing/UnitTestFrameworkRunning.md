# Running Tests for Seattle's Unit Testing Framework

(For information about writing tests, visit [UnitTestFramework Writing Unit Tests for Seattle's Unit Test Framework].)

----



----

You've written your unit tests so that they work under the unit testing framework, but how do you run them?

----

## Setup

----

Before you can actually begin running your tests, you need to set them up correctly. There are a few requirements that need to be fulfilled:

**All of your unit tests must have a '.py' extension.**

All of your python unit tests should already have this extension, but your repy test files may not if they have not been preprocessed. To learn about preprocessing, visit [PythonVsRepy Python Versus Repy].

```python

$ python repypp.py ut_tests_filetobeprocessed.mix ut_tests_filetobeprocessed.py

```

The first argument, repypp.py, is the preprocessor for repy files. It must be used before you can run repy files. The second argument is your repy unit test (note that it should follow the UTF naming convention, but with a .mix extension instead). The third argument is the filename that the preprocessor will process the file into. This new filename will be the useable version of your repy unit test.

**All of your preprocessed unit tests must be in the same directory as utf.py and utfutil.py.**

If you've got a lot of tests to run, it's usually best to write a script to move all the tests and preprocess them for you to avoid doing it every time you need to run your tests. utf.py and utfutil.py are located in the 'utf' folder in your trunk directory.

**All tests which test the same module should use the same module name for batch testing.**

That's all you really need to do to set up your tests.

----

## Running Unit Tests

----

There are three different ways you can run tests.

 * You can choose to run all UTF tests in the current directory:

```python

$ python utf.py

```

 * You can choose to run all tests belonging to one module:

```python

$ python utf.py --module <module name>
$ python utf.py -m <module name>

```

 * And you can run one specific test file:

```python

$ python utf.py --file <file>
$ python utf.py -f <file>

```


That's all you really need to know!

You can also choose to use the verbose option -v or --verbose if you want the report to show you how long it took to run each individual tests or the how long it took for the entire module.

```python

$ python utf.py --verbose --module <module name>
$ python utf.py -v -m <module name>

or

$ python utf.py --verbose --file <file>
$ python utf.py -v -f <file>
```