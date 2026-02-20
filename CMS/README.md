# Callearte CMS: Enterprise Information Systems & Digital Transformation

This repository contains the complete systems architecture and requirements specification for **Callearte**, a professional flamenco musical organization. This project documents the digital transformation from a decentralized, manual workflow to an integrated **Content Management System (CMS)**.

## 📖 Business Context

Callearte is a 15-employee organization (marketing, musicians, and technical staff).

### Current State vs. Objectives

* **Current State:** The organization lacks integrated management systems, relying on email for bookings, WhatsApp for coordination, and individual hard drives for document storage, which leads to data duplication and potential loss.
* **Primary Objectives:**
* **OBJ-0001 (Promotion):** Facilitate live bookings with a target of a 20% increase in digital contracts within three months.
* **OBJ-0002 (Publication):** Increase visibility by publishing concert schedules, band biographies, and multimedia content.
* **OBJ-0003 (Communication):** Offer an integrated direct contact channel with organizers and followers.



---

## 🛠️ Requirements Catalog

### 1. Information Requirements (Data Entities)

The system is architected to manage the following data structures:

* **IRQ-0001 (Contact):** Storage of social media links, corporate email, and phone numbers.
* **IRQ-0002 (About Us):** Detailed profiles of band members, including professional roles and high-resolution imagery.
* **IRQ-0003 (Upcoming Events):** Metadata for public performances (dates, images, and descriptions).
* **IRQ-0004 (Multimedia):** A structured repository for performance videos and photo galleries.
* **IRQ-0005 (Bookings):** Capture of event logistics (location, date, time) and client contact information.

### 2. Functional Requirements (System Actions)

* **FRQ-0004 (Event Creation):** Administrative capability to add/delete public events.
* **FRQ-0005 (Booking Workflow):** Automated routing of client forms to the communication lead.
* **FRQ-0006 (Multimedia Management):** Tools for managers to upload and organize promotional assets.
* **FRQ-0010/0015 (Interactive Gallery):** Visually organized interface for multimedia consumption.
* **FRQ-0011 (Event Billboard):** A dynamic public-facing display of the performance calendar.
* **FRQ-0016 (Visual Validation):** A date selector that provides real-time feedback by disabling invalid dates based on business logic.

### 3. Non-Functional Requirements (Quality Standards)

* **NFR-0001 (Performance):** Mandatory use of lightweight themes and caching plugins to ensure rapid load times.
* **NFR-0002 (Maintenance):** Simplified UI for administrative tasks, accessible to non-technical users.
* **NFR-0003 (Security):** Implementation of SSL (HTTPS) for all data in transit, particularly for booking submissions.

---

## 💼 Business Rules (Logic Layer)

The system enforces strict operational policies through its architecture:

| ID | Rule Name | Business Logic |
| --- | --- | --- |
| **CRQ-0001** | **Authorized Access** | Modification of content is restricted to authenticated managers (e.g., Mari Carmen Atienza). |
| **CRQ-0002** | **Booking Antelation** | The system automatically blocks any booking requests made with less than **72 hours notice**. |
| **CRQ-0003** | **Weekly Rest Policy** | No events or bookings are permitted on **Mondays**, designated as the organization's mandatory rest day. |

---

## 🎨 User Interface (UI) Specifications

* **Brand Compliance (FRQ-0007):** The visual theme is strictly built on the corporate palette: **Yellow and Dark Blue**.
* **Navigation (FRQ-0009):** A persistent menu including About Us, Multimedia, Upcoming Events, and Bookings.
* **Global Components (FRQ-0008):** A common footer across all pages containing the official logo and social media links (Instagram, TikTok, YouTube).

---

## 📂 Project Structure

* **/Analysis**: UML modeling and system requirements documentation.
* **/CMS**: Content Management System core logic and requirement mapping.
* **/DMS**: Document Management System specifications for contract and file handling.
* **/WSCT**: Web Service and Commerce Tool integration for booking automation.

---

¿Te gustaría que te ayude a redactar alguna sección adicional para este repositorio o a pasar estos requerimientos a un formato de tickets para desarrollo?