# Continuous Integration and Deployment for Azure Databricks Using Azure DevOps

## Aim
This project demonstrates the entire process of committing code from the development workspace and deploying it to the production environment without manual intervention. The primary goal is to leverage Azure DevOps Services to handle new changes from recent commits, run tests, and deploy updates to the production Databricks workspace. By automating the integration and deployment process, the project ensures reliable delivery of code to production, upholds development cycle standards, and promotes collaboration among development teams while accelerating the overall delivery pipeline.

---

## Tech Stack

- **Programming**: Scala
- **Services**: Azure DevOps, Azure Repos, Azure Pipelines, Azure Databricks

---
## Architecture Diagram
![Architecture Diagram](https://github.com/Tramnddle/Build-and-deploy-CICD-data-pipeline-using-Azure-DevOps/blob/1a089d66f254967753c6f11df5832f05a36aa832/Architecture-CICD.png)
---

## Approach

### 1. Resource Setup
- Created an Azure resource group that includes two Databricks workspaces: 
  - **Development (dev)** workspace
  - **Production (prod)** workspace
- Imported necessary notebooks from the local environment to the dev Databricks workspace.

### 2. Azure DevOps Configuration
- Set up an Azure DevOps account from the Azure portal.
- Configured Azure Repos for version control in both Azure DevOps and the dev Databricks workspace.
- Cloned Azure Repos into the dev Databricks workspace to track changes directly from Databricks to Azure-hosted repositories.

### 3. Branch Management
- Established branch policies and created feature branches for every commit instead of committing directly to the main branch. This approach prevents failures in the main codebase.
- Utilized Azure DevOps' "create pull request" feature to ensure every commit from the dev workspace required approval before triggering the CI pipeline.

### 4. Folder and Script Organization
- Created necessary folders in the dev Databricks workspace, such as "CICD," which contains:
  - Scripts for Databricks tokens
  - Templates with YAML files for CI/CD pipelines
  - Other resources for developing CI and triggering CD pipelines
- Established authentication between Azure DevOps and resource groups through the library section in Azure DevOps.
- Committed scripts, templates, and YAML files from the dev workspace to the feature branch in Azure Repos.

### 5. CI/CD Pipeline Deployment
- Deployed the CI pipeline using a YAML file, which automatically triggers the CD pipeline.
- Integrated a notification system to send emails to relevant personnel for:
  - Pull requests
  - Successful or failed builds

---

## Results
- Automated the integration and deployment process for Databricks notebooks.
- Maintained the integrity of the main branch by implementing branch policies and approvals for pull requests.
- Streamlined CI/CD workflows, reducing manual effort and errors.
- Enhanced collaboration among development teams through version control and automated notifications.

---

## How to Use

1. Clone this repository to your Azure Databricks workspace.
2. Ensure that the Azure DevOps account is configured and has access to the required resources.
3. Update the YAML templates in the "CICD" folder with the necessary parameters for your environment.
4. Follow the branching strategy for committing and pushing changes to the repository.
5. Monitor the pipeline for successful builds and deployments.

---
