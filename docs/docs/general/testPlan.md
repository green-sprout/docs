# Test plan

- [Test plan](#test-plan)
    - [1. Introduction](#1-introduction)
        - [1.1 Purpose](#11-purpose)
        - [1.2 Scope](#12-scope)
        - [1.3 Intended Audience](#13-intended-audience)
        - [1.4 Document Terminology and Acronyms](#14-document-terminology-and-acronyms)
        - [1.5  References](#15--references)
    - [2. Evaluation Mission and Test Motivation](#2-evaluation-mission-and-test-motivation)
        - [2.1 Background](#21-background)
        - [2.2 Evaluation Mission](#22-evaluation-mission)
        - [2.3 Test Motivators](#23-test-motivators)
    - [3. Target Test Items](#3-target-test-items)
    - [4. Outline of Planned Tests](#4-outline-of-planned-tests)
        - [4.1 Outline of Test Inclusions](#41-outline-of-test-inclusions)
        - [4.2 Outline of Other Candidates for Potential Inclusion](#42-outline-of-other-candidates-for-potential-inclusion)
        - [4.3 Outline of Test Exclusions](#43-outline-of-test-exclusions)
    - [5. Test Approach](#5-test-approach)
        - [5.1 Testing Techniques and Types](#51-testing-techniques-and-types)
            - [5.1.1 Unit Testing](#511-unit-testing)
            - [5.1.2 Integration Testing (API Testing)](#512-integration-testing-api-testing)
    - [6. Entry and Exit Criteria](#6-entry-and-exit-criteria)
        - [6.1 Test Plan](#61-test-plan)
            - [6.1.1 Test Plan Entry Criteria](#611-test-plan-entry-criteria)
            - [6.1.2 Test Plan Exit Criteria](#612-test-plan-exit-criteria)
    - [7. Deliverables](#7-deliverables)
        - [7.1 Test Evaluation Summaries](#71-test-evaluation-summaries)
        - [7.2 Reporting on Test Coverage](#72-reporting-on-test-coverage)
        - [7.3 Perceived Quality Reports](#73-perceived-quality-reports)
        - [7.4 Incident Logs and Change Requests](#74-incident-logs-and-change-requests)
        - [7.5 Smoke Test Suite and Supporting Test Scripts](#75-smoke-test-suite-and-supporting-test-scripts)
    - [8. Testing Workflow](#8-testing-workflow)
    - [9. Environmental Needs](#9-environmental-needs)
        - [9.1 Base System Hardware](#91-base-system-hardware)
        - [9.2 Base Software Elements in the Test Environment](#92-base-software-elements-in-the-test-environment)
        - [9.3 Productivity and Support Tools](#93-productivity-and-support-tools)
    - [10. Responsibilities, Staffing, and Training Needs](#10-responsibilities-staffing-and-training-needs)
        - [10.1 People and Roles](#101-people-and-roles)
        - [10.2 Staffing and Training Needs](#102-staffing-and-training-needs)
    - [11. Iteration Milestones](#11-iteration-milestones)
    - [12. Risks, Dependencies, Assumptions, and Constraints](#12-risks-dependencies-assumptions-and-constraints)
    - [13. Management Process and Procedures](#13-management-process-and-procedures)

## 1. Introduction

### 1.1 Purpose

The purpose of the Iteration Test Plan is to gather all of the information necessary to plan and control the test effort for a given iteration. It describes the approach to testing the software.
This Test Plan for Green Sprout supports the following objectives:

- Identifies the issues to be addressed by the tests.
- Identifies the motivation and ideas behind the test areas to be covered.
- Outlines the testing approach to be used.
- Identifies the resources required and provides an estimate of the testing effort.

### 1.2 Scope

This test plan outlines the tests designed to verify the functionality of the front-end and back-end of the application and the interaction between them.

The document includes the following types of testing:

- Unit testing
- Integration testing
- Data Consistency Tests
- API testing

Excluded from this plan are tests related to performance, user interface, scalability and usability.

### 1.3 Intended Audience

This test plan is written primarily for internal documentation purposes. It serves as a guideline for developers and as documentation for measuring compliance with quality requirements.

### 1.4 Document Terminology and Acronyms

| Abbr | Abbreviation                        |
|------|-------------------------------------|
| API  | Application Programmable Interface  |
| n/a  | not applicable                      |
| SRS  | Software Requirements Specification |

### 1.5  References

| Title                                                                   | Date       | Publishing organization   |
| ------------------------------------------------------------------------|:----------:| ------------------------- |
| SRS                                                                     | unknown    | Green Sprout              |


## 2. Evaluation Mission and Test Motivation

### 2.1 Background

The primary reason for the testing effort outlined in this test plan is to validate the integration of the various components of the web-based restaurant discovery platform. Since the system relies on interactions between a dynamic front-end, a data-driven back-end, and third-party services such as map APIs, integration testing is essential to ensure that these components work together reliably.

Without proper integration testing, issues may arise that are not visible in isolated unit tests, but could significantly impact the user experience.

This testing phase will help identify interface mismatches and data inconsistencies across the system. A full description of the system architecture and features can be found in the [SRS](./srs.md) document.

### 2.2 Evaluation Mission

The purpose is to verify that all integrated components of the application work together as intended, and meet the requirements defined in the [SRS](./srs.md). This ensures a seamless and reliable user experience across all key functions.


### 2.3 Test Motivators

The motivation for unit testing is to ensure that individual components function correctly in isolation, while integration testing validates the seamless interaction of these components within the overall system. Both are critical to ensuring reliability and robustness before release.

## 3. Target Test Items

- Server backend (and APIs)
- Database Interaction

## 4. Outline of Planned Tests

### 4.1 Outline of Test Inclusions

*Backend: Spring Boot Application*:

- Unit testing
- Integration testing
- Api testing

*Database (PostgreSQL)*

- Integration Tests
- Data Consistency Tests

### 4.2 Outline of Other Candidates for Potential Inclusion

n/a

### 4.3 Outline of Test Exclusions

Because of time and resource constraints we will not do:

- Stress test
- Load/performance tests
- Usability tests
- any further tests

## 5. Test Approach

### 5.1 Testing Techniques and Types

#### 5.1.1 Unit Testing

Unit testing ensures, that the tested sourcecode works as expected. Therefore small parts of the sourcecode are tested independently.

|                        | Description                                                                                 |
| ---------------------- | ------------------------------------------------------------------------------------------- |
| Technique Objective    | Ensure that the implemented code works as expected                                          |
| Technique              | Implement test methods using the JUnit 5 Framework (Backend)                                |
| Oracles                | Test execution logs results to the command line, logging manually ( for now, to be changed) |
| Required Tools         | JUnit 5 dependencies in our Backend                                                         |
| Success Criteria       | All tests pass. Coverage is above 66% (2/3, Backend)                                        |
|                        | CI/CD Pipeline: Github Actions                                                              |
| Special Considerations | -                                                                                           |

#### 5.1.2 Integration Testing (API Testing)

Api Testing is part of integration testing. Integration tests test multiple modules of an application together. The main goal of Api testing is to ensure, that the provided Apis of the Backend behave as expected.


|                        | Description                                                                                 |
| ---------------------- | ------------------------------------------------------------------------------------------- |
| Technique Objective    | Test API-Requests                                                                           |
| Technique              | Usage of Mock-API-Requests                                                                  |
| Oracles                | Test execution logs results to the command line, logging manually ( for now, to be changed) |
| Required Tools         | JUnit                                                                                       |
| Success Criteria       | All tests pass. Coverage is above 66% (2/3)                                                 |
|                        | CI/CD Pipeline: Github Actions                                                              |
| Special Considerations | -                                                                                           |

## 6. Entry and Exit Criteria

### 6.1 Test Plan

#### 6.1.1 Test Plan Entry Criteria

n/a

#### 6.1.2 Test Plan Exit Criteria

n/a

## 7. Deliverables

## 7.1 Test Evaluation Summaries

The current version of the project includes only backend testing, more specifically JUnit 5 tests with mocking for the Spring boot backend classes. The final version of the project is so planned, so that integration tests are also implemented
and the automation is realised through the implementation of CI/CD Pipelines. These would eventually be responsible for the evaluation of the tests, which would take place every time changes are pushed into the 
code repository, GitHub Actions being the chosen platform for the workflow.

At this point of the project Unit tests can be manually and locally evaluated through either starting the tests from the IDE oder executing the following command: `mvn test`

As shown in the screenshot below, the IDE specifies the number of passed tests as well as gives logs and where applicable warnings/error messages. 
The content of the currently implemented test classes, for example the OsmControllerTest Class, can be explained as followed: 

The OsmControllerTest class is a unit test designed to validate the functionality of the OsmController class, specifically its getNodes method. It uses Mockito to mock the OsmService dependency, allowing for controlled testing of the controller's behavior without relying on the actual service implementation. The test class includes two test cases: one that verifies a successful response when valid parameters (an amenity type and a list of coordinates) are provided, ensuring that the response status is 200 and the body contains the expected JSON data; and another that checks the handling of invalid coordinates, asserting that the response status is 400 and the body contains an appropriate error message. The setup method initializes the mocks before each test is executed.

![OsmControllerTestScreenshot](https://github.com/green-sprout/docs/blob/main/docs/assets/general/TestScreenshot.PNG)

## 7.2 Reporting on Test Coverage

For reporting our test coverage, we currently rely on manual test reports.

## 7.3 Perceived Quality Reports

Perceived quality reports for the GreenSprout application will focus on the results of the JUnit tests and integration tests conducted during the development process. If any reports are generated (when applicable), they will be generated manually, providing the development team with a clear overview of the application's quality and stability. The analysis will include a review of incidents related to test failures and any associated change requests, ensuring that the team can address quality concerns effectively.

## 7.4 Incident Logs and Change Requests

Any noticed errors during the execution of tests either locally or through triggering the CI/CD Pipeline will be immediately reported to team members, and fixing the mistakes will be added as a ticket for the following sprint.

## 7.5 Smoke Test Suite and Supporting Test Scripts

The smoke test suite for the GreenSprout application will consist of a set of automated tests designed to verify the core functionalities of the application's backend. Supporting test scripts will be developed using JUnit and Mockito for unit testing, along with integration tests to ensure that different components of the application work together seamlessly. The smoke test suite will be executed as part of the CI/CD pipeline using GitHub Actions, allowing for immediate feedback on the stability of new builds and helping to detect regressions in product quality early in the development process.

## 8. Testing Workflow

Currently, the Test-Workflow is as follows.:
1) Local testing in the IDE before a commit - Results are manually logged

Ideally, the Test-Workflow will eventually take the following form or be similar to it.:
1) Local testing in the IDE
2) Commit and Push triggers build and test execption in the CI/CD Pipeline
3) Each PR triggers the pipeline (build and test)
4) Before the automated deployment the build and test stages are executed

## 9. Environmental Needs

### 9.1 Base System Hardware

The following table sets forth the system resources for the test effort presented in this Test Plan.

| Resource            | Quantity | Name and Type                                      |
| ------------------- | :------: | -------------------------------------------------- |
| CI/CD server        |    1     | Github Actions                                     |
| local test machine  |    1     | notebook (Jonas,Safae,Samuel,Paula,Valentin)       |
| Android test device |    1     | Android device (Jonas,Safae,Samuel,Paula,Valentin) |

### 9.2 Base Software Elements in the Test Environment

The following base software elements are required in the test environment for this Test Plan.

| Software Element Name | Type and Other Notes |
| --------------------- | -------------------- |
| IntelliJ              | Test Runner / IDE    |
| JUnit  5              | Unit testing library |


### 9.3 Productivity and Support Tools

The following tools will be employed to support the test process for this Test Plan.

| Tool Category or Type | Tool Brand Name                    |
| --------------------- | ---------------------------------- |
| Repository            | [github.com](http://github.com/)   |
| CI/CD Service         | [Github Actions](https://docs.github.com/en/actions/writing-workflows/quickstart) |


## 10. Responsibilities, Staffing, and Training Needs

### 10.1 People and Roles


| Role                      | Person Assigned  | Specific Responsibilities or Comments                                    |
| ------------------------- | :--------------: | ------------------------------------------------------------------------ |
| Test Manager              |   Safae, Jonas   | Provides management oversight.                                           |
| Test Designer             |   Safae, Paula   | Defines the technical approach to the implementation of the test effort. |
| Test System Administrator | Valentin, Samuel | Ensures test environment and assets are managed and maintained.          |

### 10.2 Staffing and Training Needs

n/a

## 11. Iteration Milestones

We want to keep over 66% code coverage.

## 12. Risks, Dependencies, Assumptions, and Constraints

| Risk                                     | Mitigation Strategy                                      | Contingency (Risk is realized)      |
| ---------------------------------------- | -------------------------------------------------------- | ----------------------------------- |
| Code has lots of side effects            | Refactor code (Clean Code principles)                    | publish new refactored tests        |
| Test Runner is not able to execute tests | Use standard libraries which include working Test Runner | fix test execution configuration    |
| UI tests fail                            | Refactor test                                            | publish refactored test and restart |

## 13. Management Process and Procedures

n/a
