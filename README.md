# jenkins-cloudformation-pipeline


End-to-end CI/CD pipeline using Jenkins, Docker, and AWS. Automates app build, test, containerization, and ECS deployment. Infra provisioned via CloudFormation and monitored via CloudWatch for production-ready DevOps delivery.


Project Description**


A complete CI/CD pipeline to automate the deployment of a **multi-service, containerized application** on AWS.
This project uses:



* **Jenkins** for build and deployment automation
* **CloudFormation** for infrastructure provisioning
* **CloudWatch** for centralized logging and monitoring

The pipeline builds Docker images, pushes them to **Amazon ECR**, and deploys them to **Amazon ECS (Fargate)** behind an **Application Load Balancer (ALB)**.

---



## **Technologies Used**

| **Category**           | **Tools & Services**   | **Purpose**                                       |
| ---------------------- | ---------------------- | ------------------------------------------------- |
| CI/CD Pipeline         | Jenkins                | Automates build, test, image push, and deployment |
| Containerization       | Docker                 | Packages application services into containers     |
| Infrastructure as Code | AWS CloudFormation     | Provisions ECS, VPC, IAM, ALB, and CloudWatch     |
| Container Registry     | Amazon ECR             | Stores and manages Docker images                  |
| Orchestration          | Amazon ECS (Fargate)   | Runs containers in a serverless architecture      |
| Monitoring             | Amazon CloudWatch      | Logs, metrics, and alarm management               |
| Networking             | VPC, Subnets, NAT, ALB | Enables secure and scalable networking            |

---



## **Results / Outcomes**

* End-to-end automated CI/CD pipeline using **Jenkins**
* Seamless deployment to **ECS Fargate** with **zero downtime**
* Infrastructure fully provisioned using **CloudFormation**
* Real-time **logs and metrics** viewable in **CloudWatch**
* Reduced manual deployment time by over **90%**
* Ready for production-scale **microservice architectures**


