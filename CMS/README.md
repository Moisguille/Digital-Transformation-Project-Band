# Callearte CMS: Enterprise Information Systems & Digital Transformation

This repository contains the complete systems architecture and requirements specification for **Callearte**, a professional flamenco musical organization. This project documents the digital transformation from a decentralized, manual workflow to an integrated **Content Management System (CMS)**.

## 📖 Business Context
[cite_start]Callearte is a 15-employee organization (marketing, musicians, and technical staff)[cite: 2]. 

### Current State vs. Objectives
* [cite_start]**Current State:** The organization lacks integrated management systems, relying on email for bookings, WhatsApp for coordination, and individual hard drives for document storage, which leads to data duplication and potential loss[cite: 5, 7, 8, 9].
* **Primary Objectives:**
    * [cite_start]**OBJ-0001 (Promotion):** Facilitate live bookings with a target of a 20% increase in digital contracts within three months[cite: 10].
    * [cite_start]**OBJ-0002 (Publication):** Increase visibility by publishing concert schedules, band biographies, and multimedia content[cite: 10].
    * [cite_start]**OBJ-0003 (Communication):** Offer an integrated direct contact channel with organizers and followers[cite: 12].

---

## 🛠️ Requirements Catalog

### 1. Information Requirements (Data Entities)
The system is architected to manage the following data structures:
* [cite_start]**IRQ-0001 (Contact):** Storage of social media links, corporate email, and phone numbers[cite: 14].
* [cite_start]**IRQ-0002 (About Us):** Detailed profiles of band members, including professional roles and high-resolution imagery[cite: 16, 17, 18].
* [cite_start]**IRQ-0003 (Upcoming Events):** Metadata for public performances (dates, images, and descriptions)[cite: 21].
* [cite_start]**IRQ-0004 (Multimedia):** A structured repository for performance videos and photo galleries[cite: 24, 25].
* [cite_start]**IRQ-0005 (Bookings):** Capture of event logistics (location, date, time) and client contact information[cite: 28, 29].

### 2. Functional Requirements (System Actions)
* [cite_start]**FRQ-0004 (Event Creation):** Administrative capability to add/delete public events[cite: 35].
* [cite_start]**FRQ-0005 (Booking Workflow):** Automated routing of client forms to the communication lead[cite: 36].
* [cite_start]**FRQ-0006 (Multimedia Management):** Tools for managers to upload and organize promotional assets[cite: 39].
* [cite_start]**FRQ-0010/0015 (Interactive Gallery):** Visually organized interface for multimedia consumption[cite: 40, 52].
* [cite_start]**FRQ-0011 (Event Billboard):** A dynamic public-facing display of the performance calendar[cite: 41].
* [cite_start]**FRQ-0016 (Visual Validation):** A date selector that provides real-time feedback by disabling invalid dates based on business logic[cite: 54].

### 3. Non-Functional Requirements (Quality Standards)
* [cite_start]**NFR-0001 (Performance):** Mandatory use of lightweight themes and caching plugins to ensure rapid load times[cite: 43, 44].
* [cite_start]**NFR-0002 (Maintenance):** Simplified UI for administrative tasks, accessible to non-technical users[cite: 45].
* [cite_start]**NFR-0003 (Security):** Implementation of SSL (HTTPS) for all data in transit, particularly for booking submissions[cite: 46].

---

## 💼 Business Rules (Logic Layer)
The system enforces strict operational policies through its architecture:

| ID | Rule Name | Business Logic |
| :--- | :--- | :--- |
| **CRQ-0001** | **Authorized Access** | [cite_start]Modification of content is restricted to authenticated managers (e.g., Mari Carmen Atienza)[cite: 31]. |
| **CRQ-0002** | **Booking Antelation** | [cite_start]The system automatically blocks any booking requests made with less than **72 hours notice**[cite: 31, 33]. |
| **CRQ-0003** | **Weekly Rest Policy** | [cite_start]No events or bookings are permitted on **Mondays**, designated as the organization's mandatory rest day. |

---

## 🎨 User Interface (UI) Specifications
* [cite_start]**Brand Compliance (FRQ-0007):** The visual theme is strictly built on the corporate palette: **Yellow and Dark Blue**[cite: 47, 48].
* [cite_start]**Navigation (FRQ-0009):** A persistent menu including About Us, Multimedia, Upcoming Events, and Bookings[cite: 51].
* [cite_start]**Global Components (FRQ-0008):** A common footer across all pages containing the official logo and social media links (Instagram, TikTok, YouTube)[cite: 49, 50].

---

## 📂 Project Structure
* **/Analysis**: UML modeling and system requirements documentation.
* **/CMS**: Content Management System core logic and requirement mapping.
* **/DMS**: Document Management System specifications for contract and file handling.
* **/WSCT**: Web Service and Commerce Tool integration for booking automation.