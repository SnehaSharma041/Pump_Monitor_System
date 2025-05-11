# Pump_Monitor_System
# 🚰 Pump Monitoring and History Management System

An Android-based mobile application developed during an internship at **APDCL Datacenter** to improve efficiency, accountability, and transparency in manual pump operations. The system replaces traditional paper registers with a digital logbook to track pump usage, reduce resource wastage, and ensure secure access.

---

## 🧩 Introduction

Traditionally, pump operations at APDCL were recorded in physical registers, which led to data inconsistencies, time-consuming searches, and a lack of transparency. This system provides a centralized, mobile-based solution to track pump activities in real-time. While the system does **not automate physical pumps**, it ensures that all activities are logged manually in a structured, digital format.

---

## ✨ Features

- 🔐 **Login Authentication** – Only authorized users can access the system.
- 🏠 **Main Interface** – Controls for turning the pump ON/OFF/CANCEL with location tagging.
- ⏱️ **Timer** – Tracks pump usage duration to prevent overuse.
- 📜 **History Log** – Displays a detailed activity record with timestamps, users, duration, and status.
- 📍 **Location Tracking** – Records pump activity per location for effective analysis.
- ⚙️ **Manual Logging** – Ensures accurate tracking without automating physical operations.

---

## ⚙️ How It Works

1. User logs into the app with credentials.
2. On the main screen, selects the location where the pump is being used.
3. Enables the **ON** button to start the pump and begins timer tracking.
4. Can stop the pump using **OFF**, or abort with **CANCEL**.
5. Operation details are saved in the **History Page** with all metadata for accountability.

---

## 🔁 System Workflow

```mermaid
flowchart TD
    A[Login Page] --> B{Authenticated?}
    B -- Yes --> C[Main Page]
    B -- No --> Z[Access Denied]
    C --> D[Select Location]
    D --> E[Enable ON Button]
    E --> F[Start Pump and Timer]
    F --> G[Use OFF or CANCEL]
    G --> H[Store Record in Database]
    H --> I[Display in History Page]
