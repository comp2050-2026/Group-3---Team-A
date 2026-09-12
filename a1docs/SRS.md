# A1 Submission including Software Requirements Specification

> [!info] 2026 SRS starting point
> This is the confirmed SRS skeleton for the linked project. The A1 package is one PDF plus one video; verify the 50-page limit and all rubric-level requirements against the released A1 specification.

> Use this Markdown file to create the report and include it in the single A1 PDF submitted through iLearn. The existing template specifies an absolute maximum of 50 A4 pages including title pages, diagrams and the table of contents; apply that limit only if it is retained in the released 2026 A1 specification.

> Use the document structure below. You may, if you wish, split the file up into multiple files to make the management easier. You can then leverage some GitHub automation to 'assemble' your file and or generate the PDF.

> 1. SRS
> 2. Group Activity Record
> 3. Appendices

# SRS Structure

### Title Page

# ChargeMate Customer

## Team A Members
* **Cooper Went** 
* **Isaac Lynn** 
* **Yousef Mustafa** 
* **Harrison McLuckie** 

ChargeMate provides a seamless power bank rental service for visitors to Harbour North Plaza. Its aim is to reduce battery-related anxiety by allowing customers to easily find, rent, use and return portable power banks while keeping the experience clear, convenient and largely self-service.

## Table of Contents

* [Change Log](#change-log)
* [Introduction](#introduction)
* [Scope](#scope)
* [Overall Description](#overall-description)
* [Product Perspective](#product-perspective)
* [Product Functions](#product-functions)
* [User Characteristics](#user-characteristics)
* [Constraints](#constraints)
* [Assumptions and Dependencies](#assumptions-and-dependencies)
* [Specific Requirements](#specific-requirements)
* [Use Cases and Interactions](#use-cases-and-interactions)
* [Group Activity Records](#group-activity-record)
* [Discussion](#discussion)
* [Invidiual Contributions](#individual-contributions)
* [Appendices](#appendices)

## Change Log
**In Progress**
- A list or table of versions with
  - The date of a new version
  - What has been changed
  - Who made the changes and
  - Who agreed to the changes

## Introduction

**Purpose**

This document specifies the software requirements for ChargeMate Customer, the customer-facing component of the ChargeMate power bank rental service at Harbour North Plaza. It defines the system's functional and non-functional requirements, scope, users, constraints, dependencies, use cases and interactions. The SRS provides a requirements baseline for the subsequent design and development of ChargeMate Customer and its interaction with ChargeMate Ops.

## Scope
**ChargeMate Customer**

ChargeMate Customer covers the customer-facing power bank rental experience at Harbour North Plaza.

The system will allow customers to:

- Find ChargeMate rental stations and view their current availability.
- View available power banks, charge status and available return slots.
- View pricing, rental-duration and applicable charge information.
- Start a power bank rental.
- View information about an active rental.
- Return a power bank to an operational ChargeMate station with an available return slot.
- Receive confirmation of successful rentals and returns.
- Receive clear information and support options when a rental, return or station-related problem occurs.
- Complete rentals using a guest or minimal-registration process.

ChargeMate Customer will exchange rental, return and station information with ChargeMate Ops.

Staff operations, maintenance, power bank redistribution, station diagnostics, operator reporting and other operational-management functions are outside the scope of ChargeMate Customer and belong to ChargeMate Ops.

**ChargeMate Ops**

ChargeMate Ops is the operator-facing system responsible for managing the operational side of the ChargeMate network. Its responsibilities include station monitoring, power bank tracking, fault management, inventory and redistribution activities, and operational information required to run the service.

The detailed requirements for ChargeMate Ops are outside the scope of this SRS and are specified separately by Team B.

Staff operations, maintenance, station diagnostics, inventory redistribution and operator reporting are therefore outside the scope of ChargeMate Customer.

## Overall Description:

### Product Perspective

ChargeMate Customer is the customer-facing part of the ChargeMate power bank rental service at Harbour North Plaza. It is intended to help customers find, rent, use and return portable power banks with minimal assistance from shopping-centre staff.

The system operates alongside the physical rental stations, power banks and ChargeMate Ops system specified by Team B. ChargeMate Customer depends on ChargeMate Ops for station locations, power bank availability and charge status, return-slot availability, station status, and rental and return confirmations.

Staff operations, station maintenance, power bank redistribution and operator reporting are outside the scope of ChargeMate Customer.

![ChargeMate Customer System Context Diagram](srsimages/ChargeMate_Customer_Context_Diagram.png)

**Figure 1: ChargeMate Customer System Context Diagram.** The diagram illustrates the system boundary and the high-level interactions between ChargeMate Customer, customers, the rental station network, and ChargeMate Ops.


### Product Functions

At a high level, ChargeMate Customer should allow customers to:

- Locate ChargeMate rental stations within Harbour North Plaza.
- Check whether a suitable power bank is available.
- View relevant rental and pricing information before beginning a rental.
- Start a power bank rental.
- View information about an active rental.
- Return a rented power bank.
- Receive confirmation when a rental or return has been completed successfully.
- Access clear help or support information if a problem occurs.


### User Characteristics

ChargeMate Customer may be used by a wide range of visitors to Harbour North Plaza, including shoppers, commuters, cinema visitors, library visitors, medical-centre visitors, and people attending weekend events.

Users may have different levels of technical experience and familiarity with the service. Some customers may be in a hurry, while others may only use ChargeMate once. Customers may also have concerns about payment, deposits, late fees, privacy, or what happens when a station does not operate correctly.

For this reason, the customer experience should aim to be clear, simple, and easy to understand without requiring extensive previous knowledge of the system.


### Constraints

**C-01:** ChargeMate Customer must remain focused on the customer-facing rental experience. Staff operations and maintenance functions are outside its scope.

**C-02:** The system should minimise the need for Harbour North Plaza customer-service staff to resolve routine technology or rental problems.

**C-03:** The rental process should avoid creating an unnecessarily large sign-up process for customers.

**C-04:** Some ChargeMate Customer functions depend on information provided by the physical rental stations and ChargeMate Ops.


### Assumptions and Dependencies

**A-01:** ChargeMate Customer depends on ChargeMate Ops for station information, including station location, exact power bank availability, power bank charge status, available return slots and station operational status.

**A-02:** ChargeMate Customer depends on ChargeMate Ops to confirm that a rental has successfully started and to identify the power bank released to the customer.

**A-03:** ChargeMate Customer depends on ChargeMate Ops to confirm that a returned power bank has been successfully recorded.

**A-04:** ChargeMate Customer manages and displays customer-facing pricing, deposit/pre-authorisation, rental-duration and late-fee information, including determining when a rental becomes overdue and calculating applicable late fees.

**A-05:** When starting a rental, ChargeMate Customer provides ChargeMate Ops with the selected power bank ID, station ID and the rental details required to record the rental.


## Specific Requirements

### Functional Requirements

**Station Information and Availability**

**FR-01: Station Location**  
The system shall display the location of each ChargeMate rental station within Harbour North Plaza.

**Fit Criterion:**  
When station information is available, the customer can view the location of every operational ChargeMate station.

---

**FR-02: Power Bank Availability**  
The system shall display the exact number of available power banks at each ChargeMate station.

**Fit Criterion:**  
For each station, the number displayed by ChargeMate Customer matches the availability information supplied by ChargeMate Ops.

---

**FR-03: Power Bank Charge Status**  
The system shall indicate whether available power banks are sufficiently charged for rental.

**Fit Criterion:**  
A power bank identified by ChargeMate Ops as sufficiently charged is shown as available for rental, while an insufficiently charged power bank is not shown as available.

---

**FR-04: Return Slot Availability**  
The system shall display the exact number of available return slots at each ChargeMate station.

**Fit Criterion:**  
For each station, the number of available return slots displayed to the customer matches the latest information supplied by ChargeMate Ops.

---

**FR-05: Station Status**  
The system shall display whether a ChargeMate station is operational or unavailable.

**Fit Criterion:**  
When ChargeMate Ops reports a station as online, offline or unavailable, ChargeMate Customer displays the corresponding station status.

---

**FR-06: Availability Updates**  
The system shall update station and power bank availability whenever a rental, return, fault or station-status change occurs.

**Fit Criterion:**  
After ChargeMate Customer receives an updated availability or status event from ChargeMate Ops, the displayed station information reflects the updated values.

#### Rental Process

**FR-07: Start Rental**  
The system shall allow a customer to start a rental for an available power bank.

**Fit Criterion:**  
When a customer starts a valid rental, ChargeMate Customer sends the selected power bank ID, station ID and required rental details to ChargeMate Ops.

---

**FR-08: Rental Confirmation**  
The system shall confirm to the customer when a rental has successfully started.

**Fit Criterion:**  
After ChargeMate Ops confirms a successful rental, ChargeMate Customer displays confirmation and identifies the released power bank.

---

**FR-09: Failed Power Bank Release**  
The system shall inform the customer when a rental is authorised but the station fails to release the power bank.

**Fit Criterion:**  
When a release failure is reported, the system displays a failure message and the unsuccessful rental or payment authorisation is cancelled or reversed.

#### Return Process

**FR-10: Cross-Station Return**  
The system shall allow customers to return a rented power bank to any operational ChargeMate station with an available return slot.

**Fit Criterion:**  
A customer can select and complete a return at a station different from the original rental station when that station is operational and has at least one available return slot.

---

**FR-11: Record Return**  
The system shall provide the power bank ID and return station information when recording a return.

**Fit Criterion:**  
When a return is processed, ChargeMate Ops receives the correct power bank ID and return-station information.

---

**FR-12: Return Confirmation**  
The system shall notify the customer when a return has been successfully recorded.

**Fit Criterion:**  
After ChargeMate Ops confirms the return, ChargeMate Customer displays a successful return confirmation.

---

**FR-13: Full Return Station**  
The system shall inform the customer when a selected station has no available return slots and provide another nearby station with available capacity.

**Fit Criterion:**  
When the selected station has zero available return slots, the system prevents the return from being directed to that station and displays at least one nearby operational station with an available return slot, where one exists.

---

**FR-14: Unconfirmed Return**  
The system shall inform the customer when a physical return cannot be confirmed.

**Fit Criterion:**  
When the return is not confirmed, the system displays an error message and provides instructions for contacting support or reporting the issue.

#### Customer and Active Rental Information

**FR-15: Guest Rental**  
The system shall support guest or minimal-registration rentals.

**Fit Criterion:**  
A customer can begin a rental without creating a full customer account and is only required to provide the necessary contact and payment information.

---

**FR-16: Active Rental Information**  
The system shall display relevant information about the customer's active rental.

**Fit Criterion:**  
During an active rental, the customer can view:

- Rental start time.
- Elapsed rental time.
- Current price.
- Rental status.
- Available return locations.

#### Pricing and Rental Charges

**FR-17: Pricing and Rental Charges**  
The system shall manage and display pricing, deposit/pre-authorisation, rental-duration and applicable late-fee information to the customer.

**Fit Criterion:**  
Before and during a rental, the customer can view the applicable pricing and rental-duration information. When a rental becomes overdue, the system identifies the overdue status and calculates and displays any applicable late fee.

#### Error Handling

**FR-18: Customer Error Messages**  
The system shall display clear messages when a rental or station-related problem occurs.

**Fit Criterion:**  
The system displays an appropriate customer-facing message when any of the following occurs:

- A station is unavailable.
- A power bank is unavailable.
- No return slots are available.
- A power bank release fails.
- A return cannot be confirmed.
- A service error occurs.

### Non-Functional Requirements

**NFR-01: Usability**  
The system shall provide a clear and simple customer experience suitable for first-time and occasional users.

**Fit Criterion:**  
A customer shall be able to identify station availability, rental information, active rental status and return options without requiring assistance from Harbour North Plaza staff.

---

**NFR-02: Self-Service Support**  
The system shall provide customers with sufficient information to resolve common rental and return problems without relying on shopping-centre staff.

**Fit Criterion:**  
For supported error conditions, including unavailable stations, failed releases, unavailable return slots and unconfirmed returns, the system displays a clear explanation and the appropriate next action or support option.

---

**NFR-03: Information Consistency**  
Customer-facing station and rental information shall remain consistent with information received from ChargeMate Ops.

**Fit Criterion:**  
When ChargeMate Ops provides updated station availability, return-slot availability or station status, ChargeMate Customer displays values that match the latest received information.

---

**NFR-04: Privacy**  
The system shall minimise the personal information required from customers when using the rental service.

**Fit Criterion:**  
A guest or minimal-registration rental can be completed using only the contact and payment information required to process and manage the rental.

---

**NFR-05: Error Clarity**  
Customer-facing error messages shall clearly communicate the problem and, where possible, what the customer should do next.

**Fit Criterion:**  
For each defined customer-facing error condition, the displayed message identifies the problem and provides either a recovery action, an alternative option or instructions for contacting support.


### Use cases and interactions

#### Use Case Diagram

![ChargeMate Customer Use Case Diagram](srsimages/ChargeMate_Customer_Use_Case_Diagram.png)

**Figure 2: ChargeMate Customer Use Case Diagram.** The diagram shows the main interactions between the Customer, ChargeMate Customer system and ChargeMate Ops. The three primary use cases selected for detailed analysis are Rent a Power Bank, Return a Power Bank, and Handle Rental/Return Problem.

2. Select the 3 "most important" use cases and create a full use case description for each (total 3 use case descriptions).
3. Interaction diagram for each the most important use cases listed in 2. (total 3 interaction diagrams).



## Group Activity Record

### Discussion

- Elicitation Methods: Explaining what techniques you used to elicit the requirements you've reported. This is very important. Be sure to include a fair amount of detail.
  
- Outlook: How you would, if you were continuing the project, further develop the requirements. What other information do you need, and how do you think you could get it? What would you do to be sure that you have the "right" requirements?

### Individual Contributions

- Outline what each team member has led, contributed to, discussed, and/or reviewed.


## Appendices

- log of interactions with stakeholders (minutes from stakeholder comms).
- log of interactions with team members (minutes from all team meetings and discussions - be they in person, chats, or online).
- References.
- Third-party-resources

> Based on the information in the minutes with the stakeholders and on the documentation of third-party resources, but condensed to itemised lists.
