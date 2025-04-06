# VerifyMe - User Flow

## 1. Introduction

This document describes the primary user flow for the VerifyMe mobile application during the pre-election identity verification process. This flow allows registered voters to verify their identity one day before the election to expedite their experience at the polling booth.

## 2. Pre-Verification Flow (Happy Path)

1.  **Launch Application:**
    * **User Action:** Opens the VerifyMe app installed on their smartphone.
    * **System Response:** Displays the **Home page** featuring the "VerifyMe!!" title, a brief tagline ("Start the process..."), and a "Start" button.

2.  **Initiate Verification:**
    * **User Action:** Taps the "Start" button.
    * **System Response:** Navigates to the **DV (Document Verification)** screen. Displays the title "Document Verification", instruction ("Choose a document to verify"), a list of selectable government ID types (e.g., Voter card, Aadhar card, PAN card, Driving Licence), and a "Submit" button.

3.  **Select Document Type:**
    * **User Action:** Selects their desired ID type from the list (e.g., taps on "Aadhar card"). *[Assumes radio button selection logic]*.
    * **System Response:** Highlights the selected document type.
    * **User Action:** Taps the "Submit" button.

4.  **Scan Government ID Document:**
    * **System Response:** Navigates to the **DV 2 (Document Scan)** screen. Displays the instruction ("Scan the selected document") and activates the phone's back camera, potentially showing guiding markers (e.g., corner brackets or an outline).
    * **User Action:** Positions their selected physical ID card within the camera view according to the guides.
    * **System Response:** Automatically detects the document or user taps a capture button (*[Specific capture mechanism TBD]*). The system captures the image.
    * **System Response:** Briefly shows a processing indicator while securely uploading the image to the backend for analysis (OCR).
    * **System Response (on success):** Receives confirmation from the backend that the document was processed successfully. Navigates to the next step.

5.  **Perform Face Verification:**
    * **System Response:** Navigates to the **FV (Face Verification)** screen. Displays the title "Face Verification", instruction ("Position your face within the circle"), and activates the phone's front camera, showing a guiding outline (e.g., a circle or oval).
    * **User Action:** Positions their face within the on-screen guide, potentially holding still or performing a small action if required for liveness detection.
    * **System Response:** Captures necessary facial data (including for liveness check).
    * **System Response:** Shows a processing indicator while securely uploading the data to the backend for analysis (liveness check, facial comparison).
    * **System Response (on success):** Receives confirmation from the backend that the face verification and liveness check were successful. Navigates to the final step.

6.  **View Verification Confirmation:**
    * **System Response:** Displays the **Verified** screen. Shows a prominent "Verified Successfully" message, a success icon (checkmark), and informational text explaining that the user can now join the pre-verified line on election day and reminding them to find their booth. Includes the tagline "Every vote counts!".
    * **User Action:** Reads the confirmation. The pre-verification process is complete. The user can now close the app.

## 3. Error Handling & Alternative Flows (Conceptual)

* **Scan Failures:** If the document scan (Step 4) or face scan (Step 5) fails due to poor image quality, poor lighting, face not detected, or liveness check failure:
    * **System Response:** Displays a clear error message explaining the issue (e.g., "Image too blurry, please retake", "Liveness check failed, please try again"). Provides an option for the user to **Retry** the scan step.
* **Backend Verification Failures:** If the backend processing fails (e.g., extracted ID data doesn't match records, face doesn't match ID photo):
    * **System Response:** Displays a clear error message indicating verification failed and potentially provides guidance (e.g., "Verification failed. Please ensure you are using the correct ID or visit the polling booth for assistance on election day."). The flow may end here or offer limited retries.

## 4. Post-Verification Outcome

* Upon successful completion of the flow, the user's status is marked as "Verified" within the system, allowing them expedited processing at the polling booth on election day.
