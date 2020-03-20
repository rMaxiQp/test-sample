# CI/CD

> In software engineering, CI/CD or CICD generally refers to the combined practices of continuous integration and either continuous delivery or continuous deployment

In this documentation, we will use CI/CD as continuous integration and continuous delivery.

## Continuous Integration

> In software engineering, continuous integration is the practice of merging all developers' working copies to a shared mainline several times a day.

CI encourages developers to merge their code and unit tests into a shared version control repository after every small task completion. Hence, developers are also required to run test before submission in case their update has a side-effect that break others' code.

## Continuous Delivery

> [Continuous Delivery] aims at building, testing, and releasing software with greater speed and frequency.

Such approach reduces the cost, time, and risk of delivering changes by allowing for more incremental updates to applications in production.

## Test Automation

> In software testing, testing automation is the use of software separate from the software being tested to control the execution of tests and the comparison of actual outcomes with predicted outcomes.

Two common approaches that are used widely:

- Graphical user interface testing

  > A testing framework that generates user interface events such as keystrokes and mouse clicks, and observers the changes that result in the user interface, to validate that the observable behavior of the program is correct.

  [Selenium](https://github.com/seleniumhq/selenium) is a popular framework on Web automation. So far, it supports C#, JavaScript, Java, Python and Ruby.

- API driven testing

  > A testing framework that uses a programming interface to the application to validate the [behavior] user test... It can also be testing public (usually) interfaces to classes, modules or libraries are tested with a variety of input arguments to validate that the results that are return are correct.

  Rather than testing using user interface, API testing focuses on interfaces to the program itself.

## Tools

There are a lot of [testing automation](https://github.com/atinfo/awesome-test-automation) frameworks that depend on the specific language.

In practice, there are also general CI/CD hosts that help you manage the pipeline:

- [Travis CI](https://travis-ci.org/)
- [CircleCI](https://circleci.com/)
- [GitHub Actions](https://github.com/features/actions)
- [Drone](https://drone.io/)

## Reference

- <https://en.wikipedia.org/wiki/CI/CD>
- <https://en.wikipedia.org/wiki/Continuous_integration>
- <https://en.wikipedia.org/wiki/Continuous_delivery>
- <https://docs.microsoft.com/en-us/azure/devops/learn/what-is-continuous-integration>
