# E-Voting System with Face Verification

An **AI-powered E-Voting System** built using **Flask**, **MySQL**, **OpenCV**, and **face recognition**, supporting three types of users: **Voter**, **Candidate**, and **Admin**. The system ensures secure voting through **face verification** and provides real-time results.

---

## Table of Contents

1. [Features](#features)  
2. [User Roles](#user-roles)  
3. [Database Schema](#database-schema)  
4. [User Workflow](#user-workflow)  
5. [Setup](#setup)  
6. [Dependencies](#dependencies)  

---

## Features

- Secure user authentication (Signup / Signin).  
- Candidate registration with party details and profile photo upload.  
- Voter registration with photo upload for face verification.  
- Real-time face verification at the time of voting using **OpenCV**.  
- Admin dashboard to monitor votes and update candidate details.  
- Automatic vote counting and results display.  
- Responsive and user-friendly UI.

---

## User Roles

### 1. Voter
- Pages: `UserHome`, `Photo Upload / Face Scan`, `Vote Cast`.  
- Workflow:
  - Upload a photo (optional).  
  - Vote cast button is disabled until face verification if photo is uploaded.  
  - Real-time face verification ensures only authorized voters cast votes.

### 2. Candidate
- Pages: `CandidateHome`, `Candidate Registration (CReg)`.  
- Workflow:
  - Candidate registers with personal and party information.  
  - Candidate can view the number of votes they have received in real-time on `CandidateHome`.

### 3. Admin
- Pages: `AdminDashboard`, `Result`, `Update Candidate`.  
- Workflow:
  - Dashboard displays total voters and votes per candidate.  
  - `Result` page shows who won the election.  
  - `Update` page allows admin to edit candidate details.

---

## Database Schema

### Users Table
Stores voter credentials and details.

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT UNIQUE,
    username VARCHAR(50) PRIMARY KEY,
    password VARCHAR(100) NOT NULL,
    mobile_no VARCHAR(10) NOT NULL,
    branch VARCHAR(50) NOT NULL,
    gender VARCHAR(10) NOT NULL,
    user_type ENUM('voter','candidate','admin') NOT NULL
);
