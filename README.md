# AI-Campus-Intelligence-System
Institutions face disconnected systems for student tracking, career guidance, complaint resolution, and accreditation work. A unified AI-powered platform can automate these processes, reduce manual effort, and provide timely support for students, faculty, and administrators.


Details about Project 


# AI Campus Intelligence System

## Overview
The **AI Campus Intelligence System** is a comprehensive, multi-faceted Django-based web application designed to enhance and automate campus administration, student life, and career progression. By integrating advanced artificial intelligence via the **Groq LLM API**, the platform offers intelligent, dynamic features across several major institutional domains—from automated accreditation management to personalized student career guidance.

## Key Features

### 1. AccrediBot: AI Accreditation Management System
*   **Automated Document Processing:** Upload NAAC/NBA accreditation documents in multiple formats (PDF, DOCX, Excel).
*   **Intelligent Classification:** Uses AI to read, classify, and match uploaded documents to their respective accreditation criteria and sub-criteria.
*   **Real-Time Progress Tracking:** An administrative dashboard that calculates and displays the current completion percentage for required criteria.

### 2. AI-Powered Career Development System
*   **Smart Resume Analysis:** Students upload their resumes which are parsed by AI to extract existing skills and experiences.
*   **Skill Gap Identification:** Compares the student's profile against industry expectations to pinpoint specific skill gaps.
*   **Personalized Recommendations:** Automatically generates actionable online course suggestions (e.g., from Coursera or Udemy) and provides legitimate, clickable links for relevant internships tailored to the student's desired role.

### 3. Smart Attendance & Risk Predictor
*   **Attendance Management:** An interface for teachers to mark and monitor student attendance.
*   **AI Risk Assessment:** Analyzes attendance patterns to predict the likelihood of a student falling short of the required baseline, categorizing them into risk levels (Safe, Warning, Critical) to enable early intervention.

### 4. AI-Powered Complaint Management
*   **Interactive Chatbot:** Students interact with an AI conversational agent to articulate their grievances and issues.
*   **Automated Routing & Priority:** The LLM categorizes the complaint and assigns a priority level (Low, Medium, High, Critical) prior to ticket creation, ensuring administrators can focus on urgent matters first.

## Tech Stack
*   **Backend:** Python, Django
*   **Database:** SQLite (default for development)
*   **AI Integration:** Groq API (Llama 3 models) for natural language processing, fuzzy-matching, and text generation.
*   **Frontend:** HTML5, CSS3, JavaScript, Django Templates

## Setup & Installation

Follow these steps to get the project running on your local machine:

**1. Clone the repository / Navigate to the folder:**
```bash
git clone <repository-url>
cd Hackthon
```

**2. Create a virtual environment:**
```bash
# On Windows
python -m venv venv
venv\Scripts\activate

# On macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

**3. Install dependencies:**
Install Django and required integrated libraries:
```bash
pip install django groq python-dotenv pdfplumber docx2txt openpyxl
```

**4. Environment Variables:**
Create a `.env` file in the project's root directory and configure your Groq API credentials:
```env
GROQ_API_KEY=your_groq_api_key_here
```

**5. Database Migrations:**
Initialize the database schemas:
```bash
python manage.py makemigrations
python manage.py migrate
```

**6. Populate Initial Data:**
The project includes setup scripts to help populate mock data and administrative accounts:
```bash
python setup_admin.py
python populate_attendance_data.py
```

**7. Run the Development Server:**
```bash
python manage.py runserver
```
Navigate to `http://127.0.0.1:8000/` in your browser.

## Project Structure
*   `core/`: Contains the primary database models (Students, Admins, Attendance, Complaints, Accreditation) and the core views/services that interact with the Groq API.
*   `career_system/`: Specific models and services driving the resume analysis and course recommendation engine.
*   `templates/`: HTML templates for the student and admin dashboards.
*   `static/`: CSS and JavaScript files for UI styling.
