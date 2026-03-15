🏥 AI-Enhanced Hospital Triage System
A full-stack Flask application that streamlines emergency department triage using intelligent priority classification, real-time patient queue management, and a role-based interface for patients, admins, and doctors.

🚀 Features
🔷 Patient Registration
Patients can register via a clean and responsive web form.
Default vitals (SBP, DBP, Temp, HR, RR, O2) are auto-filled for convenience.
Real-time MRN-based auto-fill of patient demographics if a matching record exists.
Flash warnings and validation for incomplete/invalid entries (e.g., invalid MRN).
🤖 AI-Powered Triage Prediction
On submission, the system:
Processes vital signs and chief complaint text.
Feeds the input to a trained AdaBoost classifier.
Assigns a severity category: Critical 🔴, Moderate 🟡, or Low 🟢.
Patients are then placed in a MongoDB-based queue, prioritized by:
Date
Time block (Morning → Late Night)
Severity
🧑‍⚕️ Doctor Dashboard
Displays one patient at a time, with:
MRN
Name
Predicted Severity
Doctors can:
Enter prescribed medicines and ordered tests.
Submit completed visits, which are stored in a visits collection.
Shows number of patients remaining in queue.
Supports real-time Socket.IO notifications when severity is updated by an admin.
🛠 Admin Dashboard
View and manage triaged patients by:
Date
Time block (Morning, Afternoon, Evening, Late Night)
Severity group
Editable severity via dropdown; changes are immediately persisted and broadcasted to doctor screen.
Includes:
Pagination between appointment dates.
Severity summary by weekday using a Chart.js bar graph.
Interactive weekday selection showing patient volume.
📊 Patient Visit History
Users can search by MRN to see:
All previous visits.
Complaints, test orders, and medicines prescribed.
Uses Bootstrap collapsible cards for better readability.
