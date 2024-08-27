# Jenkins Pipeline for Java based application using Maven, SonarQube, Argo CD, Helm and Kubernetes

![Screenshot 2023-03-28 at 9 38 09 PM](https://user-images.githubusercontent.com/43399466/228301952-abc02ca2-9942-4a67-8293-f76647b6f9d8.png)


Here's how I set up an end-to-end Jenkins pipeline for a Java application using SonarQube, Argo CD, Helm, and Kubernetes:

### Tools I Used:

- Java application code hosted on a Git repository.
- Jenkins server.
- Kubernetes cluster.
- Helm package manager.
- Argo CD.

### Steps I Followed:

1. **Installed the Necessary Jenkins Plugins:**
   - First, I installed the following plugins on Jenkins:
     - Git plugin.
     - Maven Integration plugin.
     - Pipeline plugin.
     - Kubernetes Continuous Deploy plugin.

2. **Created a New Jenkins Pipeline:**
   - I created a new pipeline job in Jenkins and configured it with the Git repository URL where the Java application code is hosted.
   - Then, I added a `Jenkinsfile` to the Git repository to define the various stages of the pipeline.

3. **Defined the Pipeline Stages:**
   - I structured the pipeline with the following stages:
     1. **Checkout:** Retrieved the source code from the Git repository.
     2. **Build:** Built the Java application using Maven.
     3. **Test:** Ran unit tests with JUnit and Mockito.
     4. **Code Quality:** Conducted a SonarQube analysis to ensure code quality.
     5. **Package:** Packaged the application into a JAR file.
     6. **Deploy to Test:** Deployed the application to a test environment using Helm.
     7. **User Acceptance Tests (UAT):** Ran user acceptance tests on the deployed application.
     8. **Promote to Production:** Promoted the application to the production environment using Argo CD.

4. **Configured Each Jenkins Pipeline Stage:**
   - **Checkout:** I used the Git plugin to pull the source code from the repository.
   - **Build:** I configured the Maven Integration plugin to build the Java application.
   - **Test:** I ran unit tests using the JUnit and Mockito plugins.
   - **Code Quality:** I integrated the SonarQube plugin to analyze the code quality.
   - **Package:** I used Maven to package the application into a JAR file.
   - **Deploy to Test:** I employed the Kubernetes Continuous Deploy plugin to deploy the application to a test environment using Helm.
   - **UAT:** I used a testing framework like Selenium to perform user acceptance tests.
   - **Promote to Production:** Finally, I configured Argo CD to promote the application to production.

5. **Set Up Argo CD:**
   - I installed Argo CD on my Kubernetes cluster.
   - Then, I set up a Git repository for Argo CD to monitor changes in Helm charts and Kubernetes manifests.
   - I created a Helm chart for the Java application, which included the necessary Kubernetes manifests and Helm values.
   - I added this Helm chart to the Git repository that Argo CD tracks.

6. **Integrated Jenkins with Argo CD:**
   - I added the Argo CD API token to Jenkins credentials.
   - I then updated the Jenkins pipeline to include a deployment stage with Argo CD.

7. **Ran the Jenkins Pipeline:**
   - Finally, I triggered the Jenkins pipeline to initiate the CI/CD process for the Java application.
   - I monitored the pipeline stages closely and addressed any issues that arose during the process.

This end-to-end Jenkins pipeline will automate the entire CI/CD process for a Java application, from code checkout to production deployment, using popular tools like SonarQube, Argo CD, Helm, and Kubernetes.
