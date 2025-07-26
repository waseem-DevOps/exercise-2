# Java Application with CI/CD Pipeline to AWS 

This project demonstrates how to build, test, and deploy a simple Java application using a CI/CD pipeline integrated with GitHub Actions and AWS. The pipeline manages deployments across **Dev**, **Test**, and **Staging (STG)** environments.

---

# Project Overview

The goal is to automate the deployment of a Java application to AWS using GitHub Actions. The deployment pipeline includes three environments:

- **Dev**: Every push to any branch triggers deployment to Dev.
- **Test**: Deploys **only if** Dev deployment is successful.
- **STG**: Deployed **only when a pull/merge request is targeting the `master` branch**.

---

##  Architecture

```plaintext
                         +---------------------+
                         |   GitHub Repo       |
                         +----------+----------+
                                    |
                        +-----------v------------+
                        |  GitHub Actions CI/CD  |
                        +-----+--------+---------+
                              |        |
              +---------------+        +-------------------+
              |                                    |
     +--------v--------+                 +---------v--------+
     |     Dev Env     |                 |     Test Env     |
     |  AWS (EC2/S3)   |                 |   AWS (EC2/S3)   |
     +-----------------+                 +------------------+
                                                  |
                                    +-------------v--------------+
                                    |         STG Env            |
                                    |     (Only on master MR)    |
                                    +----------------------------+
 Running Locally

# Clone the repo
git clone https://github.com/<your-username>/<exercise-2>.git
cd <exercise-2>

---

CI/CD Pipeline Logic
GitHub Actions .github/workflows/deploy.yml does the following:

On push to any branch:

Build & test Java app.

Deploy to Dev environment on AWS.

If Dev deployment succeeds, deploy to Test.

On pull request to main (master):

Trigger Staging deployment (STG).

---

 How to Use?
Push code to any branch → CI/CD deploys to Dev and then Test.

Open PR to main → if approved & merged → Deploy to STG.

All deployments are handled by GitHub Actions.
