# Java CI/CD Project with GitHub Actions and AWS Deployment

This project demonstrates a complete CI/CD pipeline for a Java application using **GitHub Actions**, deployed to **AWS** in three environments: `dev`, `test`, and `stg`.

---

## Requirements Fulfilled

 Java Application  
 GitHub Repository  
 develop & master Branches  
 CI/CD Pipeline for Dev, Test, Stg  
 STG only on PR to `master`  
 Protected `master` branch  
 ReadMe file for project & pipeline  
 Two Pull Requests (to `develop` and `master`)  
 two Merge requests one to develop branch and the other to the master branch
---

 ## GitHub Actions: CI/CD Pipeline
Located in .github/workflows/ci-cd.yml.

 Features:
Runs on push and pull_request

Deploys to:

Dev on push to develop

Test only after successful Dev

STG only on PR to master
---

## protecting Master Branch
Go to Settings > Branches in GitHub repo.

Add branch rule for master.

Check:

✅ Require pull request before merging

✅ Require status checks to pass

✅ Restrict who can push (only Owners or Admins)

✅ Require approvals

---


## Running Locally

git clone https://github.com/waseem-DevOps/exercise-2 
cd exercise-2 
docker-compose up --build
