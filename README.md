# test-sample

Bookmarks:

- [Overview](#Overview)
- [Testing Levels](#Testing-levels)
- [Testing Techniques](#testing-types,-techniques-and-tactics)
- [Testing Artifacts](#testing-artifacts)

## Overview

> The general aim of testing is to affirm the quality of software systems by systematically exercising the software in carefully controlled circumstances.

In short, testing can be divided into different approaches:

- Static, dynamic and passive testing
- Exploratory approach
- The "box" approach
        - White-box testing
        - Black-box testing
        - Grey-box testing

### Static, dynamic and passive testing

> Static testing is often implicit, like proofreading, plus when programming tools/text editors check source code structure or compilers (pre-compilers) check syntax and data flow as static program analysis.

Code reviews and syntax checking are examples for static testings. Static testing is responsible to verify the code satisfy the basic requirements.

> Dynamic testing takes place when the program itself is run.

Code execution is involved in dynamic testings. Typically, those tests are executed in a debugger environment.

> Passive testing means verifying the system behavior without any interaction with the software product.

Testers do not provide any test data but look at system log and traces for patterns and specific behaviors. Such approach is relative to offline runtime verification and log analysis.

### Exploratory approach

> a style of software testing that emphasizes the personal freedom and responsibility of the individual tester to continually optimize the quality of his/her work by treating test-related learning, test design, test execution, and test result interpretation as mutually supportive activities that run in parallel throughout the project

Exploratory testing is performed by skilled testers. The tester learns from the software by testing it, and he/she applies such knowledge to generate new good tests to run.

### The "box" approach

The "box" approach is used to describe the point of view that the tester takes when designing test cases, i.e. the knowledge about the code itself.

#### White-box testing

> White-box testing (also known as clear box testing, glass box testing, transparent box testing, and structural testing) verifies the internal structures or workings of a program, as opposed to the functionality exposed to the end-user.

The testers are aware of the internal design of the system (the source code). They choose inputs to exercise paths through the code and determine the appropriate outputs. It is usually related to unit testing.

[//]: # "Include following testing into testing techniques"

Techniques used in white-box testing:

- API testing
- Code coverage
- Fault injection
- Mutation testing
- Static testing

Code coverage tools allow the software team to examine parts of a system that are rarely tested and ensures that the most important function points have been tested.

Code coverage as a software metric can be reported as a percentage for:

- Function coverage -- number of functions being executed
- Statement coverage -- number of lines of code being executed
- Decision coverage -- number of branches being executed

#### Black-box testing

> Black-box testing (also known as functional testing) treats the software as a "black box," examining functionality without any knowledge of internal implementation, without seeing the source code.

Testers are only aware of the program's expected behavior rather than the knowledge of its source code.

[//]: # "Include following testing into testing techniques"

Techniques used in black-box testing:

- Equivalence partitioning
- Boundary value analysis
- All-pairs testing
- State transition tables
- Decision table testing
- Fuzz testing
- Model-based testing
- Use case testing
- Exploratory testing
- Specification-based testing

One advantage of the black box techniques is that no programming knowledge is required. On the other hand, the code coverage of the black-box testing may be lower since the tester does not know the source code. This method of test can be applied to all levels of software testing.

#### Gray-box testing

> Grey-box testing (American spelling: gray-box testing) involves having knowledge of internal data structures and algorithms for purposes of designing tests while executing those tests at the user, or black-box level.

The tester will often access to both "the source code and the executable binary." It may also include reverse engineering. Manipulating input data and formatting output is outside of the "black box", and it is not a practice of gray-box testing. 

A gray-box tester usually apply the knowledge to test on data type handling, exception handling, and so on inside a sandbox to observe the state of the product.

## [Testing levels](/test_level)

- Unit testing
- Integration testing
- System testing
- Operational acceptance testing

## [Testing types, techniques and tactics](/test_techniques)

- Installation testing
- Compatibility testing
- Smoke and sanity testing
- Regression testing
- Acceptance testing
- Alpha testing
- Beta testing
- Functional vs non-functional testing
- Continuous testing
- Destructive testing
- Software performance testing
- Usability testing
- Accessibility testing
- Security testing
- Internationalization and localization
- Development testing
- A/B testing
- Concurrent testing
- Conformance testing or type testing
- Output comparison testing

## [Testing artifacts](/test_artifacts)

- Test plan
- Traceability matrix
- Test case
- Test script
- Test suite
- Test fixture or test data
- Test harness

## Reference

- <https://en.wikipedia.org/wiki/Software_testing>
- <https://www.cs.cmu.edu/~luluo/Courses/17939Report.pdf>
