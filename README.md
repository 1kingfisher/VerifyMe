# VerifyMe

Secure pre-election identity verification designed to streamline the voting process.

## Problem Statement

Traditional voting processes often involve long queues and manual identity verification, which can be time-consuming, prone to errors, and potentially discourage participation. Ensuring accessible, efficient, and secure verification is crucial for maintaining trust and participation in democratic processes. This project aims to address these challenges by leveraging modern technology to create a more streamlined and reliable system.

**Alignment with UN Sustainable Development Goals (SDGs):**

This project primarily supports **SDG 16: Peace, Justice and Strong Institutions**, specifically contributing to:
* **Target 16.6:** Develop effective, accountable and transparent institutions at all levels.
* **Target 16.7:** Ensure responsive, inclusive, participatory and representative decision-making at all levels.
By making the voting verification process more efficient and secure, VerifyMe aims to strengthen the integrity and accessibility of electoral institutions.

## Proposed Solution

VerifyMe is a hybrid mobile application designed to simplify voter verification:

1.  **Pre-Verification (Day Before Election):** Users verify their identity from home using the VerifyMe app. This involves:
    * **Face Verification:** Using facial recognition technology.
    * **Document Verification:** Scanning an official government ID (like Voter Card, Aadhar Card, etc.).
2.  **Verification Status:** Upon successful pre-verification, the user receives a "Verified" status within the app.
3.  **Election Day:** Pre-verified users can use expedited lines at the polling booth, requiring only a quick final facial scan for confirmation before casting their vote.
4.  **Assisted Verification:** Volunteers are available at booths to assist voters who haven't pre-verified through the app.

## Current Status & Prototype

⚠️ **Important:** This repository currently contains the **design prototype and documentation** for the VerifyMe MVP, created for the Google Solution Challenge 2025. Functional code development is the next planned phase.

🔗 **[View the Interactive MVP Prototype (Figma)](https://www.figma.com/proto/3ClVNz4Y2hEcOjHIVJ2tQX/Verifyme?node-id=106-127&t=X5a45DtRFOHCcBQl-1&scaling=min-zoom&content-scaling=fixed&page-id=0%3A1&starting-point-node-id=106%3A127)**

## Key Features (Prototype)

* **Onboarding:** Simple start screen introducing the app.
* **Document Selection:** Allows users to choose the type of government ID they will use for verification.
* **Document Scan Interface:** Placeholder screen for capturing the ID document image via the phone's camera.
* **Face Verification Interface:** Placeholder screen for capturing the user's face via the front camera, with guidance.
* **Verification Confirmation:** Screen displaying successful verification and next steps for election day.

## Technology Stack (Planned)

This project plans to leverage the following Google technologies:

* **Frontend Framework:** **Flutter** - For building a high-quality, cross-platform (iOS/Android) mobile application from a single codebase.
* **Backend Platform:** **Firebase**
    * **Firebase Authentication:** To potentially manage user sessions securely (linked to voter data).
    * **Firestore:** To store user verification status securely.
    * **Cloud Functions for Firebase:** To orchestrate backend logic, including calls to AI services.
* **AI & Machine Learning:** **Google Cloud Vertex AI**
    * **Vertex AI Vision:**
        * **Document OCR:** To accurately extract text (name, ID number, DOB) from various government ID documents.
        * **Facial Detection & Comparison:** To compare the user's live face scan with the photo on their ID or a registered image.
        * **Liveness Detection:** To help ensure the user is physically present during face verification and prevent spoofing.
* **User Support (Potential):** **Gemini API** - To potentially power an in-app chatbot providing user assistance and answering FAQs about the verification process.
* **Cloud Platform:** **Google Cloud Platform (GCP)** - To host backend services, Vertex AI models, and manage APIs.

## Setup & Installation (Planned)

Instructions for building and running the application will be added here once functional code is available.

## Team

* CircuitBreakers
Members:
1. Neyasa Gupta
2. Devansh Mittal
