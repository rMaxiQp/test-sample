# Integration Testing

## Overview

> Integration testing is the phase in software testing in which individual software modules are combined and tested as a group.

Imagine you have lego bricks (function or program), unit testing would be testing if each brick is a proper brick. On the other hand, integration testing will be the attempt of combing those bricks together to test its functionality. For example, are bricks aligned to the others? Will combine all of them destroy one of the bricks?

## Approaches

- [Big Bang Approach](#Big-Bang)
- [Incremental Approach](#Incremental)
  - [Top Down Approach](#Top-Down)
  - [Bottom Up Approach](#Bottom-Up)
  - [Sandwich Approach](#Sandwich)

### Big Bang

  > most of the developed modules are coupled together to form a complete software system or major part of the system and then used for integration testing

  Effective method for saving time. However, the recording system is crucial. If the test cases and their results are not saved properly, the goal of integration testing will fail.

### Incremental

> Testing is done by joining two or more modules that are logically related. Then the other related modules are added and tested for the proper functioning. The process continues until all of the modules are joined and tested successfully.

In an incremental approach, there are dummy programs called __Stubs and Drivers__. Stubs and Drivers are used to mock data communication with the calling module.

__Stub__ is called by the module used test.

__Driver__ calls the module to be tested.

#### Top Down

> Testing takes place from top to down following the control flow of the software system.

The top integrated modules are tested and the branch of the module is tested step by step until the end of the related module. It takes help of stubs for testing.

This method locates fault easier and can be applied to an early prototype. Also, critical modules which control the flow of application will be tested on priority. Hence, major design flaws could be found and fixed first.

However, the method requires lots of Stubs to simulate modules from lower hierarchy. Also, modules at a lower level may be tested inadequately.

#### Bottom-up

> The lowest level components are tests first, then used to facilitate the testing of higher level components.

This method requires drivers to simulate higher modules. This method depends on all or most of the modules of the same development level. It helps to locate fault easier and there is no time waste on waiting for all modules be completed (Big-bang approach). Furthermore, it is easier to report testing progress in the form of a percentage for tracking purpose.

However, the critical modules which control the flow of application will be tested last and may be prone to defects. Given the nature of bottom-up approach, it is impossible to provide an early prototype.

#### Sandwich

> Top modules are tested with lower modules at the same time lower modules are integrated with top modules and tested

This hybrid method requires both drivers and stubs to simulate bottom-up and up-down approaches.

## Reference

- <https://www.guru99.com/integration-testing.html>
- <https://en.wikipedia.org/wiki/Integration_testing>
