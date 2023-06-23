# CI/CD infrastructure on AWS using TerraForm

## Description



The goal of this project is to set up a CI/CD pipeline using AWS CodePipeline and Terraform (Infrastructure as Code - IAC). The pipeline automates the Checkout, build, and deployment phases of the application, ensuring fast and reliable updates to both services.

> AWS services used : Codecommit, codebuild, ECS, S3, ELB, IAM

## Microservice Manual Setup Instructions

In order to execute this project, you will need to create an ECS project with two services running on it:

1. Service 1: Node.js App
   - This service will run a Node.js application on port 5001.
   - Healthcheck API: `/`
   - Testing Endpoint: `/services/service-1`
   - Description: The Node.js App service is responsible for running a Node.js application. It utilizes the evented I/O capabilities of Node.js for efficient backend operations.

2. Service 3: Go App
   - This service will run a Go application on port 5003.
   - Healthcheck API: `/`
   - Testing Endpoint: `/services/service-3`
   - Description: The Go App service is responsible for running a Go application. Go is an open-source programming language supported by Google and known for its efficiency and simplicity.

Please ensure that you have set up ECS Clusters and services before proceeding with the following steps to set up CI/CD for the Cluster's services using Terraform.

## Terraform Instructions

1. First, make sure AWS CLI is installed and you have properly configured authorization.

2. Initialize Terraform from the `terraform_infra_deployment` project folder:

   ```shell
   cd terraform_infra_deployment
   terraform init
   
3. After initialization is complete, change the values of variables found in `variables.tf`:
    ```
    vi variables.tf
    ```
4. Once you have finished modifying the variables/parameters, verify the resources that will be created using a dry run:
    ```
    terraform plan
    ```
5. Verify the output and if everything looks good, create the actual remote infrastructure in AWS:
    ```
    terraform apply
    ```
    `Note: Remove any Python-related configurations if they exist, since the Python service has been deleted. 
    Please note that the above instructions assume you have the necessary access and credentials to perform the tasks mentioned.`


- By following the instructions mentioned above, you will be able to deploy the Node.js and Go applications on an ECS cluster using AWS        CodePipeline and Terraform will enable you to automate the checkout, build, and deployment process for the services. This approach ensures   fast and reliable updates to the applications.

  For more details, please refer to the in this repository and feel free to contact me in case of any issues regarding the same.

  >Happy coding!


