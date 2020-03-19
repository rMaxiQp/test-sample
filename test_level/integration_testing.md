# Integration Testing

## Overview

> Integration testing is the phase in software testing in which individual software modules are combined and tested as a group.

Imagine you have lego bricks (function or program), unit testing would be testing if each brick is a proper brick. On the other hand, integration testing will be the attempt of combing those bricks together to test its functionality. For example, are bricks aligned to the others? Will combine all of them destroy one of the bricks?

## Approaches

- [Big Bang Approach](#Big-Bang)
- Incremental Approach
  - [Top Down Approach](#Top-Down)
  - [Bottom Up Approach](#Bottom-Up)
  - [Sandwich Approach](#Sandwich)

### Big Bang

  > most of the developed modules are coupled together to form a complete software system or major part of the system and then used for integration testing

  Effective method for saving time. However, the recording system is crucial. If the test cases and their results are not saved properly, the goal of integration testing will fail.

### Top Down

The top integrated modules are tested and the branch of the module is tested step by step until the end of the related module.

### Bottom-up

> The lowest level components are tests first, then used to facilitate the testing of higher level components.

This approach is helpful only when all or most of the modules of the same development level are ready. This method also helps to determine the levels of software developed and makes it easier to report testing progress in the form of a percentage.

### Sandwich

## Reference

- <https://www.softwaretestinghelp.com/what-is-integration-testing/>
- <https://www.guru99.com/integration-testing.html>
- <https://en.wikipedia.org/wiki/Integration_testing>
