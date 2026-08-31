# Metro-Ticket-Booking-ServiceNow
ServiceNow-based Metro Ticket Booking System with automated payment processing, QR ticket generation, booking management, email confirmation, and notifications.

# 🚇 Metro Ticket Booking System — ServiceNow

A complete **automated Metro Ticket Booking System built on ServiceNow** that streamlines the ticket-booking journey from passenger details and fare calculation to payment processing, QR ticket generation, booking record management, and confirmation notifications.

The project demonstrates how **ServiceNow Service Catalog, Flow Designer, custom Actions, REST integrations, Script logic, and automated notifications** can be combined to build an end-to-end business workflow.

---

## 📌 Project Overview

The Metro Ticket Booking System provides passengers with a simple way to book metro tickets through a ServiceNow Service Catalog.

The system automatically:

- Collects passenger and journey details
- Auto-populates passenger information
- Validates travel information
- Calculates travel distance and fare
- Creates a Metro Booking record
- Processes the payment through a mock REST API
- Generates a unique QR ticket
- Updates the booking with payment and QR information
- Sends a booking confirmation email
- Triggers a confirmation notification

The entire process is orchestrated through a **ServiceNow Flow Designer workflow**, reducing manual intervention and providing a consistent booking experience.

---

## 🎯 Objectives

The main objectives of this project are to:

1. Automate the metro ticket booking process.
2. Reduce manual data entry and processing.
3. Provide automatic fare calculation.
4. Integrate an external REST-based payment service.
5. Generate a unique QR code for every successful booking.
6. Maintain a centralized booking record.
7. Automate passenger confirmation through email and notifications.
8. Demonstrate real-world ServiceNow workflow automation.

---

## ✨ Key Features

### 👤 Passenger Information

The system captures passenger information including:

- Passenger
- Email Address
- Mobile Number
- Passenger Type

Passenger-related information can be automatically populated where applicable.

---

### 🚉 Journey Management

Passengers provide:

- Source Station
- Destination Station
- Travel Date
- Number of Tickets

The system uses station information and journey details to determine the applicable distance and fare.

---

### 💰 Automatic Fare Calculation

The system calculates:

**Total Fare = Fare Per Ticket × Number of Tickets**

The booking record maintains information such as:

- Travel Distance
- Fare Per Ticket
- Total Fare
- Number of Tickets

This eliminates the need for manual fare calculation.

---

### 💳 Automated Payment Processing

The project integrates ServiceNow with a **mock payment REST API**.

The payment process returns:

- Payment Status
- Transaction ID
- Response information

A successful payment produces a transaction identifier similar to:

`MOCK-XXXXXXXXXX`

This demonstrates how ServiceNow can communicate with an external REST service.

---

### 🎫 Automatic Booking Number

Every Metro Booking record receives a unique booking number automatically.

Example:

`MTB1001`

`MTB1002`

`MTB1003`

The booking number is generated when the booking record is created.

---

### 📱 QR Ticket Generation

After payment processing, the system executes a custom **Generate QR** action.

The action generates:

- QR ID
- QR Data
- QR Image URL

The QR data contains important ticket information such as:

- Booking Number
- Passenger Name
- Source
- Destination
- Journey Date

The generated QR information is then stored against the Metro Booking record.

---

### 📧 Automated Email Confirmation

After successful booking processing, the system sends an automated confirmation email containing:

- Booking Number
- Passenger Name
- Source
- Destination
- Journey Date
- Number of Tickets
- Total Fare
- Payment Status
- Transaction ID
- QR Image URL

This provides the passenger with all important booking information in one place.

---

### 🔔 Automated Notification

A ServiceNow notification is triggered after the booking workflow completes.

Notification:

`Metro Ticket Booking Confirmation`

This provides an additional confirmation mechanism for the booking.

---

# 🔄 End-to-End Workflow

```text
Passenger
   │
   ▼
Service Catalog
   │
   │  Enter journey & passenger details
   ▼
Get Catalog Variables
   │
   ▼
Create Metro Booking Record
   │
   │  Generate Booking Number
   ▼
Process Metro Payment
   │
   │  REST API
   ▼
Generate QR
   │
   │  QR ID
   │  QR Data
   │  QR Image URL
   ▼
Update Metro Booking Record
   │
   │  Payment + Transaction + QR details
   ▼
Send Confirmation Email
   │
   ▼
Send Booking Notification
   │
   ▼
🎫 Metro Ticket Booking Completed
