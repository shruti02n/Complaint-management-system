Students Complaint Management System
A Flask-based web application for managing and tracking student complaints in an educational environment. This system allows students to submit complaints, and admins to view, assign, and update their statuses. It integrates with Azure services for file storage, database, monitoring, and logic apps for email notifications.

🔗 GitHub Repo: Complaint management system

🚀 Features
📝 Student complaint submission form

🖼 File uploads stored securely in Azure Blob Storage

🗂 Complaint data saved in Azure SQL Database

📬 Email notifications via Azure Logic Apps

📊 Admin dashboard to view, assign, and update complaints

🔐 Application Insights logging for monitoring and diagnostics

🛠 Tech Stack
Layer	Technology
Backend	Python, Flask
Storage	Azure Blob Storage
Database	Azure SQL Database
Email Alert	Azure Logic App
Monitoring	Azure Application Insights
Authentication	(Handled via Flask sessions / keys)

📁 Folder Structure
bash

Complaint management system/
├── templates/
│   ├── submit_complaint.html
│   ├── student_dashboard.html
│   └── admin_dashboard.html
├── app.py
├── .env
└── requirements.txt
⚙ Setup Instructions
1. Clone the repository
bash

git clone https://github.com/shruti02n/Complaint-management-system
cd Capstone-project
2. Set up a virtual environment
bash

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
3. Install dependencies
bash

pip install -r requirements.txt
4. Configure Environment Variables
Create a .env file in the project root with the following variables:

env

AZURE_STORAGE_CONNECTION_STRING=your_blob_storage_conn_string
AZURE_SQL_CONN_STRING=your_sql_conn_string
LOGIC_APP_WEBHOOK_URL=your_logic_app_webhook_url
APPINSIGHTS_CONNECTION_STRING=your_app_insights_conn_string
5. Run the Application
bash

python app.py
Visit http://localhost:5000 in your browser.

✅ Functional Routes
Endpoint	Method	Description
/submit	GET/POST	Submit a new complaint
/dashboard	GET	View student dashboard
/admin	GET	View admin dashboard
/get_complaints	GET	Fetch all complaints (JSON)
/assign_complaint	POST	Assign a complaint to staff
/update_status	POST	Update complaint status

🧪 Sample SQL Table Schema
sql

CREATE TABLE Complaints (
    id INT PRIMARY KEY IDENTITY(1,1),
    student_name VARCHAR(255),
    email VARCHAR(255),
    title VARCHAR(255),
    description TEXT,
    type VARCHAR(100),
    file_url VARCHAR(MAX),
    status VARCHAR(100),
    assigned_to VARCHAR(255),
    created_at DATETIME DEFAULT GETDATE()
);
📈 Monitoring
All logs are sent to Azure Application Insights using opencensus.
