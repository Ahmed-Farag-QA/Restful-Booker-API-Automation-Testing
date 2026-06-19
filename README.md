# 🚀 Restful Booker API Testing Project

This repository contains a comprehensive **End-to-End (E2E) Testing Project** for the famous **RESTful Booker application**. The project covers the full QA lifecycle, integrating professional Manual Test Cases, detailed Bug Reports, and a robust **Postman Suite** executed via **Newman CLI**.

---

## 📁 Repository Structure
```text
RESTful-Booker-API-Testing/
│
├── README.md
├── Test_Cases.csv                   # Comprehensive Manual Test Cases Sheet
│
├── Bug_Report.csv                   # Documented Bugs with Steps to Reproduce
│
├── RESTful_Booker_Collection.json   # Postman Collection (55+ Assertions)
├── RESTful_Booker_Environment.json  # Environment Variables Configuration
│
└── Execution_Dashboard.png          # Newman htmlextra Dashboard Summary



```



## 🛠️ Tools & Technologies Used
* **Postman:** For building the API collection, variable chaining, and scripting.
* **Newman CLI:** For running the test automation directly via Command Line Interface.
* **Newman-Reporter-HtmlExtra:** For generating deep-dive visual HTML dashboards.
* **Google Sheet:** For designing Test Cases, Bug Reports, and Execution logs.
* **JavaScript (Chai Assertion Library):** For crafting detailed automated test scripts.

---

## 📋 Manual Test Cases & Scenarios
Before jumping into automation, a comprehensive test coverage plan was established. You can review the full manual test cases designed for this project here:
* 📝 **[View Test Cases Sheet](Test-cases.csv)**
     

---

## 🐞 Deliverables & Key Findings
During test execution, critical server vulnerabilities were discovered and documented:

* 🚨 **Bug #1:** API returns `500 Internal Server Error` when trying to create a booking with a completely **missing/empty request body**.
* 🚨 **Bug #2:** API crashes with `500 Internal Server Error` when **invalid headers** are provided in secure endpoints instead of returning a clean `400 Bad Request`.

* 📝 **[View Bug Report Sheet](Bug-report.csv)**

---

## 📊 Test Coverage & Scenarios (Scope)
The testing scope covers both **Positive and Negative** scenarios across the complete booking lifecycle (8 core requests):

* **Create Token (`POST`):** Generates authentication tokens.
* **Create Booking (`POST`):** Validates successful data entry and structure mapping.
* **Get Booking (`GET`):** Verifies data persistence and payload content types.
* **Update Booking (`PUT`):** Fully replaces booking parameters (Requires Auth).
* **Partial Update Booking (`PATCH`):** Partially mutates parameters.
* **Delete Booking (`DELETE`):** Purges data from the system.
* **Get Deleted Booking (`GET`):** Confirms absolute data erasure via `404 Not Found`.

---

## 💡 Key Automation Features
* **55 Comprehensive Assertions:** Thorough validation of Status Codes, Response Times (<1500ms), Data Types, and Date formats using RegEx (`YYYY-MM-DD`).
* **Dynamic Variable Chaining:** Zero hardcoded data; parameters like Tokens and Booking IDs flow dynamically from request to request.

---

## 📈 Execution Dashboard (HtmlExtra)

> 💡 **Visual Report Summary:** Below is the execution dashboard generated via `htmlextra` showing a **100% Pass Rate** across all automated scripts.

<img width="1088" height="561" alt="screenshot-1781789366246" src="https://github.com/user-attachments/assets/119bd0aa-3e29-4c9d-8a57-4a1549fb4f0c" />
<img width="1068" height="469" alt="screenshot-1781789396454" src="https://github.com/user-attachments/assets/fe591003-f23c-4f55-abb5-d77af717dbf4" />

---

## 🚀 How to Run the Automation Locally

### 1. Prerequisites
Ensure Node.js, Newman, and the extra HTML reporter are installed:

```bash
npm install -g newman
npm install -g newman-reporter-htmlextra

newman run "Postman/RESTful_Booker_Collection.json" -e "Postman/RESTful_Booker_Environment.json" --env-var "BaseURL=[https://restful-booker.herokuapp.com/](https://restful-booker.herokuapp.com/)" -r cli,htmlextra

