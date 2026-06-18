# 🚀 Restful Booker API Automation Testing Project

This repository contains a comprehensive **End-to-End (E2E) API Automation Testing** suite for the famous **Restful Booker** application. The project is designed with modularity and robust test coverage using **Postman** and executed via **Newman CLI** with a professional HTML reporter.

---

## 🛠️ Tools & Technologies Used
* **Postman:** For test development, chaining requests, and environments setup.
* **Newman CLI:** For running the collection directly via Command Line Interface.
* **Newman-Reporter-HtmlExtra:** For generating deep-dive visual HTML dashboards.
* **JavaScript (Chai Assertion Library):** For crafting detailed automated test scripts.

---

## 📊 Test Coverage & Scenarios
The collection contains **8 major requests** designed to run sequentially to simulate a complete booking lifestyle flow:
1. **Create Token (`POST`):** Generates the authentication token needed for secure actions.
2. **Create Booking (`POST`):** Dynamically creates a booking and saves `BookingID`, `firstname`, and `lastname`.
3. **Get Booking (`GET`):** Retrieves the booking data and validates fields against environment variables.
4. **Update Booking (`PUT`):** Fully updates booking details dynamically (Requires Auth Cookie).
5. **Partial Update Booking (`PATCH`):** Partially updates fields to check runtime modifications.
6. **Delete Booking (`DELETE`):** Removes the created booking completely.
7. **Get Deleted Booking (`GET`):** Verifies the database rejection with a `404 Not Found` response.

---

## 💡 Key Testing Implementations
* **High Test Coverage:** Implemented **55 comprehensive assertions** checking HTTP Status Codes, Response Times, Data Types, Data Integrity, and Regular Expressions (RegEx) for Date formats (`YYYY-MM-DD`).
* **Dynamic Variable Chaining:** Zero hardcoded data; the scripts automatically capture IDs, tokens, and names from the responses and inject them into subsequent execution steps.
* **Error Prevention:** Robust validation paths ensuring nested response structures (like `jsonData.booking.bookingdates`) are parsed correctly according to the response body map.

---

## 🚀 How to Run the Project Locally

### 1. Prerequisites
Make sure you have Node.js and Newman installed:
```bash
npm install -g newman
npm install -g newman-reporter-htmlextra
