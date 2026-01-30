# HTU Schedemy – Course Scheduling System

## 📌 Project Overview

At the beginning of each academic semester at **HTU University**, the academic administration faces challenges in organizing course assignments for instructors and teaching assistants (TAs). Managing a large number of courses, instructors, and time slots often leads to scheduling conflicts and inefficient tracking of assignments.

To address this issue, an electronic web-based application named **HTU Schedemy** was developed. The system helps organize and manage the course registration and scheduling process in a centralized, structured, and efficient manner.

The application is divided into multiple pages, where each page supports a specific administrative task to improve academic management.

---

## 🧩 Application Features

### 🔹 Add Schedule
- Add courses to the semester schedule
- Specify:
  - Course
  - Lecture time
  - Assigned instructor
  - Teaching assistant (TA)

### 🔹 View Schedule
- Display the complete semester schedule
- Presented in a clear and organized format

### 🔹 Manage Courses
- View all available courses
- Add, update, or remove courses

### 🔹 Manage Instructors
- Manage instructor information
- Track instructor course assignments

---

## 🏗️ System Architecture Overview

The system follows a **decoupled architecture**, where the front-end and back-end are developed, deployed, and scaled independently.

- **Front-end**: Handles user interaction and UI
- **Back-end**: Provides RESTful APIs, business logic, and database access

This separation improves scalability, availability, and maintainability.

---

## ⚙️ Technology Stack

### 🔹 Back-end
- Spring Boot
- RESTful APIs
- JPA / Hibernate
- PostgreSQL (recommended for production)

### 🔹 Front-end
- Hosted in a separate GitHub repository
- Deployed using AWS Amplify

---

## ☁️ Deployment & Infrastructure Requirements

The university requires the system to be deployed as a **production-ready platform** with the following capabilities:

- Front-end deployed using **AWS Amplify**
- Back-end deployed on **AWS EC2**
- Custom domain name support
- High availability and automatic scaling
- Fast access for users from different geographical regions
- Continuous monitoring and failure detection
- Automatic notifications for critical system events
- Safe application updates without service interruption

---

## 🧠 Task 1 – AWS Architecture Design

### 🔹 Proposed AWS Infrastructure

The proposed architecture uses the following AWS services:

### 🌐 Front-end Hosting
- **AWS Amplify**
  - Hosts the front-end application
  - Provides CI/CD integration with GitHub
  - Automatically builds and deploys the UI
  - Supports custom domain configuration

### 🖥️ Back-end Hosting
- **Amazon EC2**
  - Runs the Spring Boot application
  - Deployed inside an **Auto Scaling Group** for high availability
  - Multiple instances ensure fault tolerance

### ⚖️ Load Balancing
- **Application Load Balancer (ALB)**
  - Distributes incoming API traffic across EC2 instances
  - Improves availability and scalability
  - Enables zero-downtime deployments

### 🌍 Global Access & Performance
- **Amazon CloudFront**
  - Acts as a global content delivery network (CDN)
  - Reduces latency for users in different regions
  - Improves overall performance

### 🌐 Domain Management
- **Amazon Route 53**
  - Manages custom domain names
  - Routes traffic to Amplify (frontend) and ALB (backend)
  - Supports health checks and DNS failover

### 📈 Monitoring & Logging
- **Amazon CloudWatch**
  - Monitors EC2 instance health and application metrics
  - Collects logs and system performance data
  - Triggers alarms on abnormal behavior

### 🚨 Notifications
- **Amazon SNS (Simple Notification Service)**
  - Sends notifications when critical events occur
  - Alerts the technical team about:
    - Instance failures
    - Scaling events
    - Deployment updates

---

## 🛠️ Task 2 – Implementation

### 🔹 Front-end Deployment
- The front-end application is deployed using **AWS Amplify**
- Amplify is connected directly to the front-end GitHub repository
- Every push triggers an automatic build and deployment
- A custom domain is configured using Route 53

### 🔹 Back-end Deployment
- The Spring Boot application is deployed on **Amazon EC2**
- Java is installed on EC2 instances
- The application runs as a persistent service
- EC2 instances are placed behind an **Application Load Balancer**
- Auto Scaling Group ensures:
  - High availability
  - Automatic scaling during peak registration periods

### 🔹 Continuous Deployment
- **GitHub Actions** is used to automate backend deployment:
  - Build the Spring Boot application
  - Run tests
  - Deploy the updated application to EC2
- Enables safe updates without service interruption

```C

You push code to GitHub
        |
        v
GitHub Actions runs
        |
        ├── Build Spring Boot JAR
        ├── Run tests
        ├── SSH into EC2
        ├── Upload new JAR
        └── Restart app

```





---

## 🔄 Zero-Downtime Updates

To ensure uninterrupted service:
- Multiple EC2 instances are used
- Load balancer routes traffic only to healthy instances
- New application versions are deployed gradually
- Old instances are terminated only after new ones become healthy

---

## 🔔 Monitoring & Event Handling

- CloudWatch continuously monitors system health
- Alarms are triggered for:
  - CPU or memory spikes
  - Instance failures
  - Scaling activities
- SNS sends immediate notifications to the technical team

---

## 🎯 Conclusion

The proposed AWS-based infrastructure provides:

- High availability
- Automatic scaling
- Global accessibility
- Continuous monitoring
- Secure and reliable deployments

This architecture ensures that **HTU Schedemy** can run continuously for many years while supporting future expansion as the university grows internationally.

---

## 📎 Notes

- This repository contains the **back-end** implementation.
- The front-end is hosted in a separate [GitHub repository](https://github.com/AhmadAL-Quraan/HTU-Schedemy-Website-front-end) and deployed using AWS Amplify.











