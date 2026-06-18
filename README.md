# 🚀 RESTful Booker API Testing & Automation Project

This repository contains a comprehensive **End-to-End (E2E) Testing Project** for the famous **RESTful Booker application**. The project covers the full QA lifecycle, integrating professional Manual Test Cases, detailed Bug Reports, and a robust **Postman Automation Suite** executed via **Newman CLI**.

---

## 📁 Repository Structure
```text
RESTful-Booker-API-Testing/
│
├── README.md
├── Test-Cases/
│   └── API_Test_Cases.xlsx              # Comprehensive Manual Test Cases Sheet
│
├── Bug-Reports/
│   └── API_Bug_Reports.xlsx             # Documented Bugs with Steps to Reproduce
│
├── Test-Execution/
│   └── Test_Execution_Report.xlsx       # Manual Execution Tracking Sheet
│
├── Postman/
│   ├── RESTful_Booker_Collection.json   # Automated Postman Collection (55+ Assertions)
│   └── RESTful_Booker_Environment.json  # Environment Variables Configuration
│
└── Screenshots/
    ├── Execution_Dashboard.png          # Newman htmlextra Dashboard Summary
    ├── Invalid_Header_Bug.png           # Evidence for discovered bugs
    └── Missing_Body_Bug.png             # Evidence for server crashes
🛠️ Tools & Technologies Used
Postman: For building the API collection, variable chaining, and scripting.

Newman CLI: For running the test automation directly via Command Line Interface.

Newman-Reporter-HtmlExtra: For generating deep-dive visual HTML dashboards.

Microsoft Excel: For designing Test Cases, Bug Reports, and Execution logs.

JavaScript (Chai Assertion Library): For crafting detailed automated test scripts.

📊 Test Coverage & Scenarios (Scope)
The testing scope covers both Positive and Negative scenarios across the complete booking lifecycle (8 core requests):

Create Token (POST): Generates authentication tokens.

Create Booking (POST): Validates successful data entry and structure mapping.

Get Booking (GET): Verifies data persistence and payload content types.

Update Booking (PUT): Fully replaces booking parameters (Requires Auth).

Partial Update Booking (PATCH): Partially mutates parameters.

Delete Booking (DELETE): Purges data from the system.

Get Deleted Booking (GET): Confirms absolute data erasure via 404 Not Found.

💡 Key Automation Features
55 Comprehensive Assertions: Thorough validation of Status Codes, Response Times (<1500ms), Data Types, and Date formats using RegEx (YYYY-MM-DD).

Dynamic Variable Chaining: Zero hardcoded data; parameters like Tokens and Booking IDs flow dynamically from request to request.

🚀 How to Run the Automation Locally
1. Prerequisites
Ensure Node.js, Newman, and the extra HTML reporter are installed:

Bash
npm install -g newman
npm install -g newman-reporter-htmlextra
2. Execution Command
Open your terminal inside the project directory and run:

Bash
newman run "Postman/RESTful_Booker_Collection.json" -e "Postman/RESTful_Booker_Environment.json" --env-var "BaseURL=https://restful-booker.herokuapp.com/" -r cli,htmlextra
🐞 Deliverables & Key Findings
During test execution, critical server vulnerabilities were discovered and documented:

Bug #1: API returns 500 Internal Server Error when trying to create a booking with a completely missing/empty request body.

Bug #2: API crashes with 500 Internal Server Error when invalid headers are provided in secure endpoints instead of returning a clean 400 Bad Request.

📈 Execution Dashboard (HtmlExtra)
