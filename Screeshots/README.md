# Jenkins GitHub CI Pipeline

## Overview

This project demonstrates the implementation of a **Continuous Integration (CI) pipeline using Jenkins and GitHub**.

The pipeline automatically reacts to code changes pushed to GitHub, retrieves the source code, executes the required build and testing steps, and generates the project deliverables.

The objective is to demonstrate a practical DevOps workflow based on **GitHub, Webhooks, Jenkins, automated builds, testing, and artifact management**.

---

## Objectives

The main objectives of this project are to:

- Integrate Jenkins with a GitHub repository.
- Automatically trigger Jenkins builds after GitHub pushes.
- Retrieve and checkout the latest source code.
- Automate testing and build processes.
- Generate project artifacts.
- Monitor build execution through Jenkins.
- Document a complete CI workflow following DevOps practices.

---

## Technologies

| Technology | Purpose |
|---|---|
| **Jenkins** | Continuous Integration and build automation |
| **GitHub** | Source code management |
| **Git** | Version control |
| **GitHub Webhooks** | Automatic build triggering |
| **CI/CD** | Development workflow automation |

---

## CI Architecture

```text
                Developer
                    │
                    │ git push
                    ▼
              ┌───────────┐
              │   GitHub  │
              └─────┬─────┘
                    │
                    │ Webhook
                    ▼
              ┌───────────┐
              │  Jenkins  │
              └─────┬─────┘
                    │
                    ▼
            ┌─────────────────┐
            │ Checkout Source │
            └────────┬────────┘
                     │
                     ▼
            ┌─────────────────┐
            │  Tests / Build  │
            └────────┬────────┘
                     │
                     ▼
              ┌────────────┐
              │  Artifact  │
              │   target/  │
              └────────────┘
```

---

## CI Workflow

The implemented workflow follows these steps:

### 1. Source Code Management

Jenkins is connected to the GitHub repository using Git.

The pipeline retrieves the project from the `main` branch.

```text
Repository:
https://github.com/Moncef101930/Retail-BI-Platform.git

Branch:
*/main
```

### 2. GitHub Webhook

A GitHub Webhook is configured to notify Jenkins whenever a push is made to the repository.

This removes the need for manually starting a Jenkins build after every code change.

```text
GitHub Push
     │
     ▼
GitHub Webhook
     │
     ▼
Jenkins Build Trigger
```

### 3. Jenkins Build Trigger

The Jenkins job uses:

**GitHub hook trigger for GITScm polling**

When GitHub sends a push event, Jenkins detects the change and starts the CI process automatically.

### 4. Source Code Checkout

Jenkins automatically clones the repository and checks out the latest commit from the configured branch.

### 5. Testing and Build

The CI process executes the configured testing and build operations.

The objective is to detect integration or build problems as early as possible.

### 6. Artifact Generation

The generated project deliverables are stored under:

```text
target/
```

These artifacts can then be archived and used as build outputs.

---

## Jenkins Job

The Jenkins Freestyle project used for this implementation is:

```text
Retail-BI-Platform-CI
```

The job is configured with:

- GitHub repository integration
- Git source code management
- `main` branch
- GitHub Webhook trigger
- Automated build execution
- Testing/build steps
- Artifact generation

---

## Project Structure

```text
Jenkins-GitHub-CI-Pipeline/
│
├── README.md
│
├── docs/
│   └── CI-Setup.md
│
└── screenshots/
    ├── 01-jenkins-job.png
    ├── 02-github-scm.png
    ├── 03-github-webhook.png
    ├── 04-jenkins-trigger.png
    ├── 05-build-success.png
    └── 06-console-output.png
```

---

## Screenshots

### Jenkins CI Job

This screenshot shows the Jenkins job created for the CI workflow.

![Jenkins Job](screenshots/01-jenkins-job.png)

### GitHub Repository Configuration

Jenkins is configured to retrieve the source code directly from GitHub.

![GitHub SCM](screenshots/02-github-scm.png)

### GitHub Webhook

The GitHub repository sends push events to Jenkins through a webhook.

![GitHub Webhook](screenshots/03-github-webhook.png)

### Jenkins Build Trigger

The Jenkins job is configured to automatically react to GitHub webhook events.

![Jenkins Trigger](screenshots/04-jenkins-trigger.png)

### Successful Build

The Jenkins build completed successfully.

![Build Success](screenshots/05-build-success.png)

### Jenkins Console Output

The console output provides detailed information about source code checkout and build execution.

![Console Output](screenshots/06-console-output.png)

---

## Key Skills Demonstrated

This project demonstrates practical experience with:

- Continuous Integration
- Jenkins
- GitHub integration
- Git Webhooks
- Git version control
- Automated build processes
- Automated testing
- Build artifact management
- CI workflow configuration
- DevOps practices

---

## DevOps Workflow

The project follows a simplified Continuous Integration workflow:

```text
Code Change
    ↓
Git Push
    ↓
GitHub
    ↓
Webhook
    ↓
Jenkins
    ↓
Source Checkout
    ↓
Tests
    ↓
Build
    ↓
Artifact
```

---

## Future Improvements

Possible improvements for this CI project include:

- Migrating from a Jenkins Freestyle job to a **Jenkinsfile**.
- Implementing a complete **CI/CD pipeline**.
- Adding automated code quality analysis with SonarQube.
- Integrating Docker image creation.
- Adding automated deployment stages.
- Integrating notifications through Slack or Microsoft Teams.
- Implementing security and dependency scanning.

---

## Author

**Moncef Ben Maatallah**

Engineering Student — Business Intelligence & Data Analytics

Interests:

- Business Intelligence
- Data Analytics
- Data Engineering
- DevOps
- CI/CD
- Cloud & Data Platforms

---

## Conclusion

This project demonstrates how **GitHub and Jenkins can be integrated to create an automated Continuous Integration workflow**.

The implementation connects source code management, webhook-based automation, build execution, testing, and artifact generation into a reproducible DevOps workflow.
