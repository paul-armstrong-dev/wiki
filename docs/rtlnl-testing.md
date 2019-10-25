# Testing in Python

There are several ways of doing testing in Python and choosing the right one it's a tricky job. There are some assumptions that we need make in order to be able to standardize the way we can create and run tests both locally and in the CI/CD.

We can split this subject in subsections:

1. Unit Tests
2. Integration Tests

## Unit Tests

The most basic type of test. This is what the code-coverage in general they count. Becuase the unit test will evaluate a particular function , the code coverage is able to identify which part of the code in the function is being executed.
Testing single functions is not as easy as it seems. It all depends how the code has been designed and without proper usage of the [SOLID](https://itnext.io/solid-principles-explanation-and-examples-715b975dcad4) principles, we are not able to create tests.

Let's assume that the code is actually testable. The Python Standard Library comes with a `unittest` package that helps the developer in writing tests. `unittest` contains both a `testing framework` and a `test runner`. `unittest` has some important requirements for writing and executing tests. More information about this package can be found in the [official documentation](https://docs.python.org/3/library/unittest.html).

`unittest` requires that:

- You put your tests into classes as methods
- You use a series of special assertion methods in the `unittest.TestCase` class instead of the built-in `assert` statement

In your code you need to:

- Import `unittest` from the standard library
- Create a class called `TestSomething` that inherits from the `TestCase` class
- Convert the test functions into methods by adding self as the first argument
- Use the entry point to call `unittest.main()`

Let's take a look at this example:

```python
import unittest


class TestSum(unittest.TestCase):

    def test_sum(self):
        self.assertEqual(sum([1, 2, 3]), 6, "Should be 6")

    def test_sum_tuple(self):
        self.assertEqual(sum((1, 2, 2)), 6, "Should be 6")

if __name__ == '__main__':
    unittest.main()
```

Assuming that the above code is in a file called `test_sum.py`, we can run the tests with simply cally `python test_sum.py`. Test files can be put in a separate folder called `tests` at root level. Because your code should be able to be called from anywhere since it's in a package, having all the tests in one place makes it easy to work on them. Since we also have different type of tests, we shoudl put the unit tests in a folder called `unit`. See the tree below as example:

```bash
project/
│
├── my_app/
│   └── __init__.py
│
└── tests/
    |
    ├── unit/
    |   ├── __init__.py
    |   └── test_sum.py
    |
    └── integration/
        ├── __init__.py
        └── test_integration.py

```

### Test Discovery

This is an important step especially when you have multiple test files. We don't want to run tests one by one, but we want to run all of them in one single command. Test Discovery is a functionality that will automatically run all the tests that is in the code base. In order to make it possible, we need to respect the following rule:

- All of the test files must be modules or packages (including namespace packages) importable from the top-level directory of the project (this means that their filenames must be valid identifiers).

To run the test discovery, you can execute the following command from the root of your project: `python -m unittest discover`.

### SetUp and TearDown

There are two special functions that can be used in order to initialize some objects that are needed for your tests. `setUp()` is a special method that is called before the tests in the class are run. This is useful, for example, if you need to upload some data into a testing database in order to check the functionality. Becuase you can initialize things, it's important that you clean them up to avoid inconsistency in your tests.

`tearDown()` is a special function that is run when all the tests are being executed independently whether they failes or passed. If you `raise` an exception in your tests, then the function `tearDown()` won't be called becuase the program exited before completing. Make sure that you are able to handle all the errors in your test and make them `fail` with appropriate instructions rather then brutally terminate with an exception.

More information can be found at this [link](https://docs.python.org/3/library/unittest.html#organizing-test-code).

## Integration Tests

Integration testing is the testing of multiple components of the application to check that they work together. Integration testing might require acting like a consumer or user of the application by:

- Calling an HTTP REST API
- Calling a Python API
- Calling a web service
- Running a command line

The most significant difference is that integration tests are checking more components at once and therefore will have more side effects than a unit test. Also, integration tests will require more fixtures to be in place, like a database, a network socket, or a configuration file.

This is why it’s good practice to separate your unit tests and your integration tests. The creation of fixtures required for an integration like a test database and the test cases themselves often take a lot longer to execute than unit tests, so you may only want to run integration tests before you push to production instead of once on every commit. This can be set it up in the CI/CD because we make the distincion on a folder level.

Since we are using `Docker` and `docker-compose` it's easy to reproduce the "production" environment locally. Hence, by having docker-compose up and running you can write intergation tests exaclty like the unit tests explained above. The difference is that you may call the "upper most" function and wait for the result to verify that all the components are working together. That's the goal of Integration Tests.

There are no particular libraries to use. The Standard Library is sufficient to cover all the type of tests.

### Concourse CI

Currently we are investigating how to run multiple components in our CI system so that we can run integration tests when merging to master and before going to production.