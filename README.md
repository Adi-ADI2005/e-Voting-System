# AI Powered E-Voting System

This is an **AI powered e-voting system** built using:

-   **HTML, CSS, Bootstrap** -- Frontend\
-   **Python Flask** -- Backend\
-   **OpenCV** -- Face Verification\
-   **MySQL** -- Store all voting-related data

The system is fully **responsive** (mobile + desktop) and includes 3
types of users:

-   **Voter** -- Cast the vote\
-   **Candidate** -- Do nomination\
-   **Admin** -- Manage voting system

------------------------------------------------------------------------

## 🏠 Home Page

**![Home Page](home.png)
**

AI powered e-voting home interface.

------------------------------------------------------------------------

## 📝 Signup Page
![signup.png](signup.png)
SQL used for user registration:

``` sql
CREATE TABLE users (
    id INT AUTO_INCREMENT unique,
    username VARCHAR(50) PRIMARY KEY,
    password VARCHAR(100) NOT NULL,
    mobile_no VARCHAR(10) NOT NULL,
    branch VARCHAR(50) NOT NULL,
    gender VARCHAR(10) NOT NULL
);
```

------------------------------------------------------------------------

## 🔐 Signin Page

**![signin.png](signin.png)**

✅ Username Rules\
- Voter: **Alphanumeric**\
- Candidate: **Alphabetic**\
- Admin: **Numeric**

------------------------------------------------------------------------

## 🧑‍🏫 Candidate Panel

### Candidate Home


![chome.png](chome.png)
Candidate can see how many votes he/she received.

### Candidate Nomination

**(Add screenshot: `candidate_reg.png`)**
![creg.png](creg.png)
SQL for candidate nomination:

``` sql
CREATE TABLE candidate_reg (
    id VARCHAR(100) PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    dob DATE NOT NULL,
    age INT NOT NULL,
    gender VARCHAR(15) NOT NULL,
    mobile VARCHAR(15) NOT NULL,
    email VARCHAR(100) NOT NULL,
    branch VARCHAR(100),
    parti_name VARCHAR(100) NOT NULL,
    candidate_type VARCHAR(100) NOT NULL,
    party_logo VARCHAR(255)
);
```

------------------------------------------------------------------------

## 🧑‍💼 Voter Panel

### Voter Home


![uhomeb.png](uhomeb.png)
Voter must upload a photo to enable the **Vote Cast** button.

### Upload Photo


![upload.png](upload.png)
After photo upload, the button becomes enabled.

### Ready to Vote
![uhomea.png](uhomea.png)

------------------------------------------------------------------------

## 📸 Face Verification (OpenCV)

**(Add screenshot: `face_verification.png`)**
![faceverifiction.png](faceverifiction.png)
Face scan matches the user's photo stored in the database.\
If matched → **Next button appears**

------------------------------------------------------------------------

## ✅ Vote Cast Page

![vote_cast.png](vote_cast.png)

SQL for storing votes:

``` sql
CREATE TABLE vote_cast (
    id INT AUTO_INCREMENT PRIMARY KEY,
    candidate_id VARCHAR(50) NOT NULL,
    candidate_name VARCHAR(100) NOT NULL,
    parti_name VARCHAR(100) NOT NULL,
    candidate_type VARCHAR(50) NOT NULL,
    user_name VARCHAR(100) NOT NULL
);
```

------------------------------------------------------------------------

## 🛠️ Admin Dashboard

**(Add screenshot: `admin_dashboard.png`)**
![admindashboard.png](admindashbordś.png)
Admin can: - Update user details\
- Delete nomination\
- View results

### Update Page


![update.png](update.png)
### Results Page

![result.png](result.png)
See which candidate won and total votes.

------------------------------------------------------------------------

## ✅ Summary

This is a complete **AI powered e-voting system** using Flask, OpenCV
and MySQL with role-based access for Admin, Candidate and Voter.\
Screenshots should be placed in a folder like:

    /docs/images/

and referenced inside the README.

------------------------------------------------------------------------

## ✅ How to Run the Project

``` bash
git clone <your-repo-url>
cd e-voting-system
pip install -r requirements.txt
python app.py
```


