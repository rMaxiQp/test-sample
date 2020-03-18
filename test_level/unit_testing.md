# Unit Testing

## Overview

> In computer programming, unit testing is a software testing method by which individual units of source code, sets of one or more computer program modules together with associated control data, usage procedures, and operating procedures, are tested to determine whether they are fit for use.

Unit tests are typically automated tests to test on individual functions or procedures.

In the scope of object-oriented programming, a unit can be a class that we created. We can write testing to make sure that the implementation produce correct output.

Unit testing will be broken into following sections:

- [Advantages](#Advantages)
- [Disadvantages](#Disadvantages)
- [Java Example](#Java)
- [JavaScript Example](#JavaScript)
- [Python Example](#Python)

## Advantages

> The goal of unit testing is to isolate each part of the program and show that the individual parts are correct.

A unit test prevents side effect, aiming to prove the correctness of each function, the units of a program.

The following list talks about unit testing benefits:

- Find problems early in the development cycle
  - The process of writing tests forces the author to think through inputs, outputs, and error conditions, and thus have a better definition on the unit's desired behavior
  - The cost of finding a bug in early stage in lower than the cost of detecting one later
  - Unit testing can force developers to structure functions and objects in better ways

- The code is complete when the tests pass
  - Unit tests are created before the code itself in test-driven development

- Allow the location of the fault or failure to be easily traced
  - The same unit tests will run frequently as the larger code base is developed. 
  - If the unit tests fail, there is a bug either in the changed code or the tests themselves.
  - Allow the programmer to refactor code or upgrade system libraries in the future

- Reduce uncertainty in the units themselves
  - Provide living documentations of the system
  - Embody critical characteristics of each unit

## Disadvantages

> Testing will not catch every error in the program, because it cannot evaluate every execution path in any but the most trivial programs.

Testing is a machine testing the correctness of another machine. If testing is flawless, the halting problem is decidable. Hence, unit testing cannot guarantee the system will not fail.

Unit testing be definition only tests the functionality of the units themselves. Therefore, it will not catch integration errors or broader system-level errors. To provide a better and more comprehensive coverage, unit testing should be done in conjunction with other software testing activities.

The following list talks about unit testing limitations and disadvantages:

- Nondeterministic or concurrency problems is hard to be tested
- Unit test code itself can be at least buggy as the code it is testing
  - Given two different outputs, it is hard to find the correct one

- A version control system is needed for debugging purpose
  - If a later version of the unit fails a particular test that it had previously passed, the version control system can provide a list of the source code change since that time

- Setting up realistic and useful tests is difficult
  - Functions involving external interactions, e.g. database interactions, often lack complexity
  - Relevant initial conditions are required to test the application as a part of the complete system

## Java

```.java
// Derived from https://junit.org/junit5/docs/current/user-guide/#writing-tests

import static org.junit.jupiter.api.Assertions.assertEquals;

import example.util.Calculator; // Testing subject

import org.junit.jupiter.api.Test;
import org.junit.jupiter.api.Before;

class JunitJupiterTests {

  private Calculator calculator;

  @Before
  public void initCalculator() {
    calculator = new Calculator();
  }

  @Test
  public void additionTest() {
    assertEquals(2, calculator.add(1, 1));
    assertEquals(99999, calculator.add(9999, 90000));
    assertEquals(333, calculator.add(666, -333));
  }

  @Test
  public void multiplyTest() {
    assertEquals(5, calculator.multiply(1, 5));
    assertEquals(0, calculator.multiply(0, 100));
    assertEquals(-6, calculator.multiply(2, -3));
    assertEquals(6, calculator.multiply(-2, -3));
  }

  @Test (expected = DivideByZeroException.class)
  public void divideTest() {
    assertEquals(5, calculator.divide(5, 1));
    assertEquals(-5, calculator.divide(-5, 1));

    // Throw DivideByZeroException
    assertEquals(1, calculator.divide(4, 0));

    // Test fails
    assertEquals(0, 1);
  }

}


```

## JavaScript

```.js

// Derived from:
// - https://jestjs.io/docs/en/mock-functions
// - https://jestjs.io/docs/en/setup-teardown
// - https://jestjs.io/docs/en/using-matchers

import axios from 'axios';

describe('mock testing group', () => {

  beforeAll(() => {
    jest.mock('axios');
  })

  test('mock forEach callback', () => {

    // Testing subject
    function forEach(items, callback) {
      for (let index = 0; index < items.length; index++) {
        callback(items[index]);
      }
    }

    const mockCallback = jest.fn(x => 42 + x);
    forEach([0, 1], mockCallback);

    // The mock function is called twice
    expect(mockCallback.mock.calls.length).toBe(2);

    // The first argument of the first call to the function was 0
    expect(mockCallback.mock.calls[0][0]).toBe(0);

    // The first argument of the second call to the function was 1
    expect(mockCallback.mock.calls[1][0]).toBe(1);

    // The return value of the first call to the function was 42
    expect(mockCallback.mock.results[0].value).toBe(42);
  })

  test('mock axios module', () => {
    const users = [{name : 'Bob'}];
    const resp = {data: users};

    // axios.get.mockImplementation(() => Promise.resolve(resp)) also works
    axios.get.mockResolvedValue(resp);

    axios
      .get('/users.json')
      .then(resp => resp.data)
      .then(data => expect(data).toEqual(users))
  })

  test('mock return value', () => {
    const myMock = jest.fn();
    expect(myMock()).toBeUndefined();

    myMock
      .mockReturnValueOnce(10)
      .mockReturnValueOnce('x')

    expect(myMock()).toBe(10)
    expect(myMock()).toMatch(/x/)
  })
})
```

## Python

```.py

# Directed copied from https://docs.python.org/3/library/unittest.html

import unittest

class TestStringMethods(unittest.TestCase):

    def test_upper(self):
        self.assertEqual('foo'.toUpper(), 'FOO')

    def test_isupper(self):
        self.assertTrue('FOO'.isupper())
        self.assertFalse('Foo'.isupper())

    def test_split(self):
        s = 'hello world'
        self.assertEqual(s.split(), ['hello', 'world'])

        # check that s.split fails when the separator is not a string
        with self.assertRaises(TypeError):
          s.split(2)

if __name__ == '__main__':
    unittest.main()
```

## Reference

- <https://en.wikipedia.org/wiki/Unit_testing>
- <https://junit.org/junit5/>
- <https://jestjs.io/>
- <https://docs.python.org/3/library/unittest.html>
