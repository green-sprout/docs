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

---
# **------- Done Until here -------**
---

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

|                       | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    | Ensure that the implemented code works as expected                  |
|Technique              | Implement test methods using JUnit Framework (Frontend & Backend)   |
|Oracles                | Test execution logs results to the command line, logs in CI/CD Tool (Travis) |
|Required Tools         | JUnit 4 & 5 Dependencies in Frontend and Backend                    |
|Success Criteria       | All tests pass. Coverage is above 10% (Frontend) / 60% (Backend)    |
|                       | CI/CD Pipeline with test stages for Frontend and Backend: [Travis CI](https://travis-ci.com/nilskre/CommonPlayground)|
|Special Considerations | -                                                                   |

#### 5.1.2 Integration Testing (API Testing)

Api Testing is part of integration testing. Integration tests test multiple modules of an application together. The main goal of Api testing is to ensure, that the provided Apis of the Backend behave as expected.

|                       | Description                                                          |
|-----------------------|----------------------------------------------------------------------|
|Technique Objective    | Test the provided Apis with Cucumber                                 |
|Technique              | For every meaningful api a Gherkin `.feature` exists and the steps are implemented.  |            |
|Oracles                | Test execution logs results to the command line, Logs in CI/CD Tool (Travis) |
|Required Tools         | JUnit, Cucumber, Rest assured, Hamcrest                                     |
|Success Criteria       | All tests pass. Coverage is above 60%                                |
|                       | CI/CD Pipeline with test stages for Frontend and Backend: [Travis CI](https://travis-ci.com/nilskre/CommonPlayground) |
|Special Considerations | -                                                                    |

## 6. Entry and Exit Criteria

### 6.1 Test Plan

#### 6.1.1 Test Plan Entry Criteria

n/a

#### 6.1.2 Test Plan Exit Criteria

n/a

## 7. Deliverables

## 7.1 Test Evaluation Summaries

The project owns a certain amount of tests in the Frontend and Backend. Each pushed commit triggers our CI/CD Pipeline, which builds the application and executes the tests. Furthermore a code analysis with Codacy is triggered. We use a monorepo which includes the docs and the sourcecode for our Backend and Frontend. That´s why we have one CI/CD Pipeline for our whole project. 

Continuous Integration/Delivery/Deployment Pipeline based on Travis CI: [Travis CI](https://travis-ci.com/nilskre/CommonPlayground) [![Build Status](https://travis-ci.com/nilskre/CommonPlayground.svg?branch=master)](https://travis-ci.com/nilskre/CommonPlayground)

Code Analysis with Codacy: [Codacy](https://app.codacy.com/project/DRiXD/CommonPlayground/dashboard) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/aff81896be354fc48280efd8135fb3ef)](https://app.codacy.com/app/DRiXD/CommonPlayground?utm_source=github.com&utm_medium=referral&utm_content=nilskre/CommonPlayground&utm_campaign=Badge_Grade_Settings)

CI/CD Pipeline stages: Build, Test, Deploy(only on the master branch):  
![CI/CD Pipeline stages: Build, Test, Deploy(only on the master branch) ](./CICD_stages.png)  
Integration of CI/CD Pipeline pipeline with github:  
![Integration of CI/CD Pipeline pipeline with github](./CICD_github_commits.png)  
Frontend IDE test execution:  
![Frontend IDE test execution](./frontend_test_execution.png)  
Backend IDE test execution:  
![Backend IDE test execution](./backend_test_execution.png)

## 7.2 Reporting on Test Coverage

For reporting our test coverage we use Jacoco and Codacy. 

Code Test Coverage: [![Codacy Badge](https://api.codacy.com/project/badge/Coverage/7fdcfeca10b94f4c9b6bc1a809669c2b)](https://www.codacy.com/app/CommonPlayground/CommonPlayground?utm_source=github.com&utm_medium=referral&utm_content=nilskre/CommonPlayground&utm_campaign=Badge_Coverage)

## 7.3 Perceived Quality Reports

The code quality tool is Codacy. [![Codacy Badge](https://api.codacy.com/project/badge/Grade/7fdcfeca10b94f4c9b6bc1a809669c2b)](https://www.codacy.com/app/CommonPlayground/CommonPlayground?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=nilskre/CommonPlayground&amp;utm_campaign=Badge_Grade)

## 7.4 Incident Logs and Change Requests

We integrated the tools mentioned above into our GitHub pull request workflow. If a build fails this is directly visible in the PR. Furthermore the team is alerted by an email.
The screenshot shows the integration:

![GitHub PR integrated tools](./integrated_tools.png)

## 7.5 Smoke Test Suite and Supporting Test Scripts

The automated test execution in our CI/CD Pipeline enables regression testing. With this approach it is clearly visible when changes break existing functions and affect the correct behaviour of the application.

## 8. Testing Workflow

1) Local testing in the IDE
2) Commit and Push triggers build and test exection in the CI/CD Pipeline
3) Each PR triggers the pipeline (build and test)
4) Before the automated deployment the build and test stages are executed

## 9. Environmental Needs

### 9.1 Base System Hardware

The following table sets forth the system resources for the test effort presented in this Test Plan.

| Resource              | Quantity | Name and Type                |
|-----------------------|:--------:|------------------------------|
| CI/CD server          |    1     | Travis CI Cloud              |
| local test machine    |    1     | notebook (Inga, Celina, Denis, Nils)       |
| Android test device   |    1     | Android device (Inga, Celina, Denis, Nils) |

### 9.2 Base Software Elements in the Test Environment

The following base software elements are required in the test environment for this Test Plan.

| Software Element Name |  Type and Other Notes                        |
|-----------------------|----------------------------------------------|
| Android Studio        | Test Runner / IDE                            |
| IntelliJ              | Test Runner / IDE                            |
| JUnit 4 & 5           | Unit testing library                         |
| Espresso              | UI testing library                           |
| Cucumber              | human readable test definitions              |

### 9.3 Productivity and Support Tools

The following tools will be employed to support the test process for this Test Plan.

| Tool Category or Type | Tool Brand Name                              |
|-----------------------|----------------------------------------------|
| Repository            | [github.com](http://github.com/)             |
| Test Coverage Monitor | [codacy](https://app.codacy.com/)            |
| CI/CD Service         | [Travis CI](http://travis-ci.org/)           |
| Metrics Tool          | [codacy](https://app.codacy.com/)            |

## 10. Responsibilities, Staffing, and Training Needs

### 10.1 People and Roles

| Role          | Person Assigned |  Specific Responsibilities or Comments |
|---------------|:--------------:|----------------------------------------|
| Test Manager | Denis, Inga | Provides management oversight. |
| Test Designer | Denis, Celina | Defines the technical approach to the implementation of the test effort. |
| Test System Administrator | Nils | Ensures test environment and assets are managed and maintained. |

### 10.2 Staffing and Training Needs

n/a

## 11. Iteration Milestones

We want to keep over 20% code coverage.

## 12. Risks, Dependencies, Assumptions, and Constraints

| Risk | Mitigation Strategy | Contingency (Risk is realized) |
|------|---------------------|--------------------------------|
| Code has lots of side effects | Refactor code (Clean Code principles) | publish new refactored tests |
| Test Runner is not able to execute tests | Use standard libraries which include working Test Runner | fix test execution configuration |
| UI tests fail | Refactor test | publish refactored test and restart |

## 13. Management Process and Procedures

n/a
