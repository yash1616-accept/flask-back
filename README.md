# CI/CD Deployment Assignment

## Flask Backend and Express Frontend Deployment on AWS EC2 using Jenkins

---

## 🔗 GitHub Repository Links

* **Flask Backend Repository**
  [https://github.com/yash1616-accept/flask-back](https://github.com/yash1616-accept/flask-back)

* **Express Frontend Repository**
  [https://github.com/yash1616-accept/express-frontend](https://github.com/yash1616-accept/express-frontend)

---

## 🎯 Objective

The objective of this project is to deploy a **Flask backend** and an **Express frontend** on a **single Amazon EC2 instance** and implement a **CI/CD pipeline using Jenkins** to automate the deployment process whenever code is pushed to GitHub.

---

## 🏗️ System Architecture

```
Developer → GitHub → Jenkins → EC2 Instance
                          ├── Flask Backend (Port 5000)
                          └── Express Frontend (Port 3000)
```

* Jenkins pulls the latest code from GitHub
* Dependencies are installed automatically
* Applications are restarted using PM2
* Applications are accessible using EC2 Public IP

---

## ⚙️ Part 1: Deployment on EC2

### 1. EC2 Instance Setup

* **AMI**: Amazon Linux 2
* **Instance Type**: t2.micro (Free Tier)
* **Security Group Ports**:

  * 22 (SSH)
  * 3000 (Express)
  * 5000 (Flask)
  * 8080 (Jenkins)

---

### 2. Software Installed on EC2

* Python 3 (Flask backend)
* Node.js and npm (Express frontend)
* Git
* PM2 (Process Manager)
* Jenkins (CI/CD Automation)

---

### 3. Application Configuration

#### Flask Backend

* Runs on **port 5000**
* Provides REST API response
* Managed using PM2

**Access URL:**

```
http://<EC2_PUBLIC_IP>:5000
```

---

#### Express Frontend

* Runs on **port 3000**
* Provides frontend response
* Managed using PM2

**Access URL:**

```
http://<EC2_PUBLIC_IP>:3000
```

---

## 🔁 Part 2: CI/CD Pipeline using Jenkins

### Jenkins Installation and Setup

* Jenkins installed on EC2
* Required plugins installed:

  * Git
  * Pipeline
  * NodeJS
  * GitHub Integration

---

### Jenkins Pipeline Workflow

1. Developer pushes code to GitHub
2. GitHub webhook triggers Jenkins
3. Jenkins performs the following steps:

   * Clone the repository
   * Install dependencies
   * Restart the application using PM2
4. Updated application is deployed automatically

---

### Jenkinsfile

Each repository contains a `Jenkinsfile` defining the pipeline stages:

* Clone Repository
* Install Dependencies
* Restart Application

---

## 🔐 CI/CD Automation

* GitHub Webhooks are configured
* Jenkins automatically triggers on every push
* No manual deployment is required

---

## 📸 Screenshots Required for Submission

1. EC2 Instance in running state (AWS Console)
2. Flask Backend running in browser (`:5000`)
3. Express Frontend running in browser (`:3000`)
4. Jenkins dashboard
5. Jenkins pipeline console output showing successful build
6. PM2 process list (`pm2 list`)

---

## ✅ Conclusion

This project demonstrates successful deployment of Flask and Express applications on AWS EC2 with a fully automated CI/CD pipeline using Jenkins. The setup ensures continuous integration, continuous deployment, and minimal manual intervention.

---

## 🎤 Viva Explanation (Short)

"Jenkins is used as a CI/CD tool to automate deployment. Whenever code is pushed to GitHub, Jenkins pulls the code, installs dependencies, and restarts the Flask and Express applications using PM2 on an EC2 instance."

---

## 👤 Author

**Name:** Yash Gaikwad
**Branch:** INFT
**Semester:** 6
