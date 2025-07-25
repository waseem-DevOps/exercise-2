# ☕ Simple Java App with CI/CD Pipeline to AWS

This project is a **simple Java console application** integrated with a **CI/CD pipeline** using **GitHub Actions**, which automatically deploys to **AWS** in three environments: **Dev**, **Test**, and **STG**.

---

## 📦 Application Overview

This Java application simply prints a greeting message to the console.

### 🧾 Technologies Used

- Java 17
- GitHub Actions
- AWS ( S3)

---

🌐 Environments Summary
Dev: Triggered on push to develop

Test: Triggered only if Dev succeeds

STG: Triggered on PR merge into master



