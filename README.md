**Multi-Cluster CI/CD Pipeline on EKS**

This project implements a robust Continuous Integration and Continuous Deployment (CI/CD) pipeline for deploying applications across multi-cluster environments on Amazon Elastic Kubernetes Service (EKS). The pipeline automates the testing, building, scanning, and deployment processes to ensure seamless application delivery and adherence to quality and security standards.

**Project Workflow**

1.**Development Phase (Dev Cluster - Testing Environment)**

• **Source Control:** The application source code is managed using GitHub.
• **CI Pipeline:**
• Unit Testing: Automated unit tests are executed to validate application functionality.
• Trivy Scan: Security scans are conducted to detect vulnerabilities in dependencies.
• Code Quality Check: SonarQube is used to ensure the code meets quality standards.
**• Build Process:**
• The application is compiled and packaged.
• A Docker image is built and tagged for the development phase.

• **Deployment:**
• The application is deployed to a managed EKS cluster.
• A load balancer URL is generated for accessing the application in the testing environment.

2. **Production Phase (Prod Cluster - Production Environment)**

   • After successful testing in the development phase, the application undergoes the following steps:
   • CI Pipeline:
   • The GitHub Actions workflow is triggered for the production environment.
   • The Docker image is rebuilt and tagged specifically for production.
   • Trivy scans are rerun to ensure the final image is free of vulnerabilities.
   • Deployment:
   • The Docker image is pushed to Docker Hub with a prod tag.
   • The application is deployed to the production EKS cluster.
   • A custom domain is used to make the application accessible in production.
