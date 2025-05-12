#  Pump Monitoring and History Management System

An Android-based application developed during an internship at **APDCL Datacenter**, this project replaces traditional paper-based pump logbooks with a digital system that ensures transparent tracking, real-time updates, and better resource management. The system supports manual logging of pump activities, improving efficiency, reducing errors, and streamlining history management.



##  Introduction

The manual process of recording pump operations using physical registers has multiple drawbacks — it is prone to human error, lacks transparency, makes historical tracking difficult, and leads to unmonitored use of water and electricity. This mobile application offers a reliable alternative by enabling operators to log pump actions digitally in near real-time, making monitoring structured and efficient.



##  Features

- **User Authentication** – Only authorized personnel can log in and use the app.
- **Location-Based Logging** – Tracks which pump/location is in use.
- **Pump Operation Buttons** – ON, OFF, and CANCEL buttons control logging of operations.
- **Timer Functionality** – Measures how long the pump was in use.
- **History Records** – Detailed list of all past pump activities.
- **Structured Logs** – Logs include timestamp, user info, location, duration, and status.
- **Manual Tracking** – Ensures logs match actual physical operations.



##  How It Works 

###  1. Login Page

- The app begins with a **login screen** requiring a valid username and password.
- Users are authenticated via stored credentials in a MySQL database.
- If valid, they are redirected to the **Main Page**; otherwise, access is denied.
- Each logged-in session helps track who performed which operation.

###  2. Main Page - Pump Control Interface

The core functionality lies here, broken down as follows:

#### a. Location Selection

- Before using the pump, the user **must select a location** from a dropdown.
- This ensures the activity is tied to a specific pump site.
- Until a location is selected, the **ON** button remains **disabled**.

#### b. ON Button – Start Operation

- Once a location is selected, the **ON** button becomes active.
- When pressed:
  - The **current timestamp** is recorded.
  - A **timer starts** to track duration.
  - The ON button is disabled to prevent multiple logs.
  - **OFF** and **CANCEL** buttons become active.

#### c. OFF Button – End Operation

- Pressing OFF stops the timer.
- The **end timestamp** and **total duration** are calculated.
- A log entry is created with:
  - Start & end time
  - Duration
  - Selected location
  - User identity
  - Status: ✅ Valid

#### d. CANCEL Button – Abort Operation

- If the user needs to stop without completing the session:
  - Timer is stopped.
  - Only start time is recorded.
  - The log is saved with status ❌ Invalid.
  - Useful in case of errors or unintentional starts.

> 🔄 After any operation, all buttons reset, and a new operation can begin after location re-selection.



###  3. History Page – Record Management

- Shows a **chronological list** of all past pump operations.
- Each entry includes:
  -  Start and End Timestamps
  -  User Name
  -  Location
  -  Duration
  -  Status: Valid or Invalid
- Helps supervisors and staff quickly review pump activity without checking physical registers.



###  4. Backend Integration

- The app is connected to a **MySQL database** using **REST APIs**.
- APIs handle:
  - User authentication
  - Inserting new pump logs
  - Fetching history for display
- Database tables:
  - `users`: stores login credentials
  - `pump_logs`: stores all operational records with foreign keys to users

---

##  System Flowchart

![APDCL Project Report](https://github.com/user-attachments/assets/a23b08d8-e304-41f3-80ac-adc17a5afffe)


## 🚀 Getting Started

### Requirements

- Android Studio
- Java
- XML for UI Design
- MySQL for database
- PHPMyAdmin for DB Management
- REST APIs (PHP-based or Node.js backend)



##  Benefits

-  Reduces water and electricity wastage
-  Eliminates physical registers and manual errors
-  Provides searchable, structured records
-  Tracks user accountability
-  Saves time and simplifies management


## 📌 Final Note

> ❗ **Important**: This application does **not** control the physical pump. It is a **manual digital tracking system**. Users must operate the actual pump and then log their action using the app to maintain accurate records.

---

## 📃 License

This project is intended for internal use within APDCL. All rights reserved.

## Contact Details

| Name              | Email                         | GitHub Username  | LinkedIn Profile  |
|-------------------|-------------------------------|------------------|------------------|
| Pragyan Kalita | pragyankalita137004@gmail.com |   | [LinkedIn]() |
| Sneha Sharma      | snehasnehasharma0918@gmail.com| SnehaSharma041  | [LinkedIn](www.linkedin.com/in/sneha-sharma-90012b296) |
| Swayam Biyala   |  swayamsharma2712@gmail.com | SSwayamM | [LinkedIn]() |
| Prastab Raaj Singha    | prastabraaj1234@gmail.com|  | [LinkedIn]() |


