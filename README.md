Project Title
Chronic Disease Prediction and Management System (Type 2 Diabetes Focus)

 Overview of the Project

This system is a Machine Learning (ML)-driven application designed to address the challenges of chronic disease management, specifically focusing on the early risk prediction and proactive management of Type 2 Diabetes. The primary goal is to provide a functioning prototype that leverages ML to calculate an individual's risk score based on key health metrics. The system serves two main user types:
Patients: Receive a personalized risk assessment and actionable lifestyle recommendations.
Healthcare Providers (Doctors): Utilize a secure dashboard for data management (CRUD) to monitor and manage their high-risk patient population effectively.

 Features

Risk Assessment: Accepts patient health metrics (e.g., Glucose, BMI, Age, Blood Pressure) and processes them through a trained Random Forest Classifier to output a numerical risk probability (e.g., 85% risk).
Personalized Recommendation Engine: Automatically generates tailored advice (dietary suggestions, exercise plans, suggested follow-up frequency) based on the calculated risk score.
Provider Data Management (CRUD): A secure dashboard enabling healthcare providers to Create new patient records, Read patient health data and risk scores, Update existing records, and Delete outdated information.
Secure Authentication: Implements secure login and data handling to comply with the Security (NFR) requirement for sensitive patient information.
Intuitive Patient Interface: A straightforward web form for easy data input, addressing the Usability (NFR) requirement.

Steps to Install & Run the Project
1. Prerequisites
Ensure you have Python 3.8+ and pip installed on your system.

2. Clone the Repository

git clone https://github.com/YourUsername/My-Project.git
cd My-Project

3. Set Up Virtual Environment

It's recommended to use a virtual environment to manage dependencies.


4. Install Dependencies
Install all necessary Python packages:
pip install -r requirements.txt

The requirements.txt file should contain packages like Flask, pandas, scikit-learn, etc.)

5. Initialize the Database
Run the setup script to create the necessary database tables (Patient, HealthData, etc.) and, optionally, load initial sample data.
python initialize_db.py

6. Run the Application
Start the Flask development server:
python app.py

Instructions for Testing

Testing ensures all Functional Requirements (FRs) and Non-Functional Requirements (NFRs) are met.
1. Model Prediction Test (Risk Assessment)
Action: Navigate to the Patient Input form (/predict).
Input: Enter a set of metrics known to represent a high-risk patient (e.g., high Glucose, high BMI, older age).
Expected Result: The system should return a high-risk probability score (e.g., >70\%) and display corresponding aggressive recommendations (e.g., "Immediate consultation with a specialist").
Action: Repeat with metrics for a low-risk patient.
Expected Result: A low-risk probability score (e.g., <30\%) with general, preventative recommendations.
2. CRUD Operations Test (Provider Dashboard)
Action: Log in as a Healthcare Provider/Doctor (access /provider-dashboard).
Test 1 (Create/Read): Add a new patient via the dashboard form.
Verify: The new patient record immediately appears in the patient list view.
Test 2 (Update): Select an existing patient, change their contact information, and submit.
Verify: The updated information is correctly reflected in the database and the dashboard view.
Test 3 (Delete): Select a test patient and use the delete function.
Verify: The patient record is permanently removed from the list.
3. Security and Performance Tests (NFRs)
Security: Attempt to access the /provider-dashboard URL directly without logging in.
Verify: The system redirects you to the login page or displays an "Access Denied" message.
Performance: Record the time taken for the prediction (from submitting the patient form to displaying the result).
Verify: The ML prediction is returned quickly, meeting the target of within 5 seconds.