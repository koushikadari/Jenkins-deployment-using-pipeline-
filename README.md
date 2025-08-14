--------------------------------------------
Hands-on Project: Jenkins Deployment Pipeline with Git, Maven, Nexus, and Tomcat
Designed and implemented a CI/CD pipeline using Jenkins to automate the deployment of a website. Provisioned three separate EC2 instances for Jenkins, Tomcat, and Nexus Repository Manager.
Source Code Management: Integrated Git as the version control system to pull application code from a remote repository.
Build & Test: Configured Maven within the pipeline to compile the source code and run automated tests.
Artifact Management: Published build artifacts to Nexus for centralized versioning and storage.
Deployment: Automated the deployment process to Tomcat, ensuring zero manual intervention after code changes.
Pipeline as Code: Created a Jenkins Declarative Pipeline (Jenkinsfile) that defined all stages from code checkout to final deployment.
Tech Stack: Jenkins, Git, Maven, Nexus, Tomcat, EC2, Linux.
