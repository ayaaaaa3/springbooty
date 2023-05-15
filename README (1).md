
# Spring Boot Application Deployment Guide on Azure Cloud
This guide will walk you through the steps to deploy a Spring Boot application on Azure Cloud using Azure DevOps, SonarQube, Azure Registry, and Kubernetes. This will enable you to have a reliable and scalable infrastructure that can handle your application's requirements.



# Requirements

- SonarQube Stage: This is used to scan the code for potential issues and vulnerabilities.
We created sonar vm with below details:
Name :sonarrr
Public ip :40.124.184.104
Usernameto ssh :Cloud
Password:P@ssw0rd@123
Username to ui :admin
Password: P@ssw0rd@123
 SonarQube version : 10.0.0.68432
Service connection name between pipeline and sonarQube:Token_Aya


- Build Image Stage: This is used to build a Docker image of your application.
- Push Image to Azure Registry: This is used to store the Docker image in the Azure Registry.
- Pull Image from Registry: This is used to pull the Docker image from the Azure Registry.
- Deploy Spring Boot app to Kubernetes cluster on Azure Cloud: This is used to run your application on a Kubernetes cluster on Azure Cloud.
- Create Ingress for the app linked with a domain name referring to the endpoint: This is used to create an endpoint for your application that users can access.
- Deploy on development environment (dev-env): This is used to test your application before deploying it to production.
- Deploy on production environment (main): This is used to deploy your application to the live environment.
# Dependencies
- Java JDK 11: This is the Java Development Kit that is required to run your Spring Boot application.
- Maven: This is the build tool that is used to build your application.
- Azure Repo: This is the repository where your application code is stored.
- Azure Kubernetes cluster: This is the Kubernetes cluster where your application will be deployed.
- SonarQube VM on Azure Cloud: This is the virtual machine that is used to scan your code for potential issues and vulnerabilities.
- Self-host as VM on Azure Cloud: This is the virtual machine that is used to host your application.
# Deploying to Azure Cloud
- Commit your code to the Azure repo to trigger the SonarQube test and build in the pipeline. This will scan your code for potential issues and vulnerabilities and build a Docker image of your application.
- The pipeline build will create an image on the Azure Registry. This will store the Docker image in the Azure Registry.

- A trigger will deploy the image to 3 replicas on the dev branch. This will run your application on a Kubernetes cluster on Azure Cloud.
- Admin approval is required to proceed. This is to ensure that the deployment is authorized and does not cause any issues.
- After approval, the main stage will be triggered to deploy on the main branch. This is the live environment where your application will be accessible to users.
- A final build will create an ingress to link the public IP to the Spring Boot app's three live pods. This is used to create an endpoint for your application that users can access.
   Ingress puplic ip :20.225.119.196
Congratulations! Your Spring Boot application is now deployed on Azure Cloud using Azure DevOps, SonarQube, Azure Registry, and Kubernetes. This will provide you with a reliable and scalable infrastructure that can handle your application's requirements.

-Bonus Points
1- we created self host agent with below details 
Name:self-hosted-agent
Public ip :40.119.42.190
Username ssh :Cloud
Password:P@ssw0rd@123
2-We created readme file attached on azure repo 
 

