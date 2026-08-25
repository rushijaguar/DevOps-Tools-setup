<img width="694" height="417" alt="CI-CD Diagram" src="https://github.com/user-attachments/assets/e2114a3c-a570-4dff-81b0-5dc3982bf3f9" />

[!NOTE]
# Jenkins — CI/CD Automation Server

Jenkins is a free, open-source automation server used to automatically build, test, and deploy applications. It is commonly used to implement CI/CD pipelines. [Official docs](https://www.jenkins.io/doc/)

## Example workflow

```text
Developer pushes code
        ↓
Jenkins downloads code
        ↓
Jenkins builds the application
        ↓
Jenkins runs tests
        ↓
Jenkins deploys the application
```

## What is CI/CD?

### Continuous Integration (CI)
Developers frequently push code to a shared Git repository. Jenkins automatically downloads the latest code, compiles or builds the application, runs unit tests, and reports success or failure.

### Continuous Delivery (CD)
Automatically prepares a tested application for release. Deployment may still require manual approval.

### Continuous Deployment (CD)
Automatically deploys the application to an environment such as development, staging, or production.

## Important Jenkins terms

- **Job or Project** — A task configured in Jenkins.
- **Build** — One execution of a job.
- **Pipeline** — A sequence of automated stages.
- **Jenkinsfile** — A file containing pipeline instructions (Groovy).
- **Controller** — Main Jenkins server that manages jobs and configuration.
- **Agent/Node** — Machine that executes jobs.
- **Workspace** — Directory where Jenkins checks out and builds code.
- **Plugin** — Extension that adds Jenkins functionality.
- **Artifact** — Output produced by a build, such as a JAR or Docker image.
- **Credential** — Securely stored password, token, or SSH key.

## Jenkins architecture

Jenkins typically has two major parts:

- **Controller** — Stores configuration, schedules jobs, manages plugins, and assigns work.
- **Agent** — Executes commands such as Git checkout, Maven builds, Docker builds, or tests.

### Notes

- For small installations, the controller can also execute jobs.
- For larger environments, use separate agents to improve scalability and security.

## Common Jenkins workflow

1. Developer pushes code to GitHub or GitLab.
2. A webhook informs Jenkins about the change.
3. Jenkins starts a pipeline.
4. Jenkins checks out the source code.
5. The application is built.
6. Automated tests are executed.
7. A package or Docker image is created.
8. The result is deployed.
9. Jenkins displays logs and final status.

## Types of Jenkins jobs

### Freestyle Project
Configured through the Jenkins web UI. Good for simple shell commands, basic Git projects, and demos.

### Pipeline Project
Defined using Groovy pipeline syntax. Ideal for multi-stage CI/CD, version-controlled configuration, and complex deployment workflows.

### Multibranch Pipeline
Automatically discovers branches with a Jenkinsfile and creates pipelines for them. Useful for feature branches and pull requests.
