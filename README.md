# Postman API Automation Integration with GitHub Actions

## Overview

This project demonstrates an end-to-end API test automation setup using **Postman, Newman, and GitHub Actions**.

The API test scenarios are created and maintained in Postman and executed using **Newman**. The automation pipeline is integrated with **GitHub Actions**, enabling automated test execution through multiple triggers, including:

* Push to the `main` branch
* Manual workflow execution using `workflow_dispatch`
* Scheduled execution using a cron schedule

The project generates detailed HTML test reports using **Newman Reporter Htmlextra**. The latest report is automatically published using **GitHub Pages**, allowing the test execution results to be viewed online.

Test execution reports are also archived as **GitHub Actions artifacts** for download and future reference.

Additionally, the latest test report is automatically shared with team members through **Gmail SMTP**.

---

## GitHub Pages

You can directly view the latest test report of the Postman test execution at the GitHub Pages link:

https://codebyshakti.github.io/Phoenix-Inwarrenty-Flow/

---

## HTML Test Report

The HTML report is generated using **Newman Reporter Htmlextra**.

![Postman Report](https://github.com/codebyshakti/Phoenix-Inwarrenty-Flow/blob/static-content/newman-report.png)

---

## Key Features

* Automated API testing using Postman and Newman
* CI/CD integration using GitHub Actions
* Automatic execution on every push to the `main` branch
* Manual workflow execution using `workflow_dispatch`
* Scheduled test execution using cron jobs
* Data-driven API testing using CSV test data
* Positive, negative, and edge-case testing
* Token and authentication validation
* API schema validation
* Secrets management using GitHub Secrets
* Detailed HTML reporting using Newman Reporter Htmlextra
* Automated report publishing using GitHub Pages
* Test report archival using GitHub Actions artifacts
* Automated email notifications using Gmail SMTP
* Self-hosted GitHub Actions runner configured on an AWS EC2 instance

---

## Testing Coverage

The automated API test suite includes the following types of testing:

1. Happy Flow Testing
2. Negative Testing
3. Edge Case Testing
4. Authentication and Token Validation
5. Data-Driven Testing using CSV
6. API Schema Validation
7. Response Validation
8. Secrets and Environment Variable Management

---

## Tech Stack

| Technology                | Purpose                                 |
| ------------------------- | --------------------------------------- |
| Postman                   | API test development and validation     |
| Node.js                   | Runtime environment                     |
| Newman                    | Postman collection execution            |
| Newman Reporter Htmlextra | HTML test reporting                     |
| GitHub Actions            | CI/CD and workflow automation           |
| GitHub Secrets            | Secure credential and secret management |
| GitHub Pages              | Publishing the latest HTML test report  |
| Gmail SMTP                | Automated email notifications           |
| CSV                       | Data-driven test execution              |
| AWS EC2                   | Self-hosted GitHub Actions runner       |

---

## Architecture and Execution Flow

The overall automation workflow follows this flow:

**Postman Collection → GitHub Actions Workflow → Self-Hosted AWS EC2 Runner → Newman → HTML Report → GitHub Pages / GitHub Artifacts → Email Notification**

The workflow is triggered automatically based on the configured GitHub Actions events.

After execution:

1. GitHub Actions triggers the workflow.
2. The job is picked up and executed by the self-hosted AWS EC2 runner.
3. Newman executes the Postman collection.
4. Test results are displayed in the GitHub Actions logs.
5. A detailed HTML report is generated using Newman Reporter Htmlextra.
6. The report is uploaded as a GitHub Actions artifact.
7. The latest report is published to GitHub Pages.
8. Test execution results are sent to team members through Gmail SMTP.

---

## Project Structure

```text
Phoenix-Inwarrenty-Flow
│
├── Inwarrenty-flow Collection.postman_collection.json
│   └── Postman API test collection
│
├── QA.postman_environment.json
│   └── QA environment configuration
│
├── testdata.csv
│   └── Test data for data-driven execution
│
├── newman/
│   └── Generated HTML test reports
│
└── .github/
    └── workflows/
        └── GitHub Actions workflow configuration
```

---

## How to Run the Project Locally

### 1. Clone the Repository

Clone the repository to your local system:

https://github.com/codebyshakti/Phoenix-Inwarrenty-Flow.git

### 2. Install Node.js

Install Node.js and npm:

https://nodejs.org/

Verify the installation:

```bash
node -v
npm -v
```

### 3. Install Newman

```bash
npm install -g newman
```

### 4. Install Newman Reporter Htmlextra

```bash
npm install -g newman-reporter-htmlextra
```

### 5. Execute the Postman Collection

Run the following Newman command:

```bash
newman run "Inwarrenty-flow Collection.postman_collection.json" \
  -e "QA.postman_environment.json" \
  -d testdata.csv \
  -r cli,htmlextra \
  --reporter-htmlextra-export "./newman/index.html"
```

After execution, the HTML report will be generated inside the `newman` directory.

---
## About Me

Hi, I'm **Shakti Mishra**, an **SDET / QA Automation Engineer with 5+ years of experience in software testing and automation**.

My experience includes:

* UI Automation using Selenium WebDriver and Playwright
* API Testing and Automation using Postman and REST Assured
* API validation using GraphQL and SQL
* Test automation using TestNG and BDD Cucumber
* Testing of Microservices and Kafka-based applications
* Test framework development using Java and Maven
* CI/CD pipeline automation using Jenkins, Ansible, and Docker
* CI/CD and test automation using GitHub Actions and Azure DevOps
* AWS-based testing environments
* Git and version control workflows
* Agile and Scrum methodologies

You can connect with me on LinkedIn:

[www.linkedin.com/in/shaktisworup-mishra1998/](http://www.linkedin.com/in/shaktisworup-mishra1998/)

---
