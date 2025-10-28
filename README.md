# 🎓 University Timetable Dashboard

This is a full-stack web application built with **Python** and **Flask** designed to manage and display university timetables in a clean, searchable, and centralized way.

It was built to solve the common university problem of having schedules for different programs (like B.Tech, BBA, etc.) spread across multiple, hard-to-read documents. This app provides two main interfaces:

1.  **A Public Dashboard** for students to instantly find their class schedules, search for subjects, and find free rooms.
2.  **A Private Admin Panel** for staff to easily upload and manage all timetables from a single, password-protected page.

## ✨ Key Features

### **User (Student) Dashboard**
* **Dynamic Filters:** Select your **Program**, **Section**, and **Day** to view a full day's schedule.
* **Time Slot Filter:** Select a specific time slot to see what class you have *and* which rooms are free across the entire university.
* **Universal Search:** A search bar to find any subject (e.g., "PCS-302") across all programs and sections.
* **Free Room Finder:** When you select a time, the app cross-references all schedules and shows a list of all rooms that are **not** occupied.

### **Administrator Panel (`/admin`)**
* **Secure Login:** The admin panel is protected by a password.
* **Program Management Dashboard:** View a list of all programs currently in the database and when their timetables were last updated.
* **Add New Program:** Upload a `.docx` timetable for a program that isn't in the database yet.
* **Update Existing Program:** Select an existing program from a dropdown and upload a new `.docx` file to overwrite its old schedule and update the "last updated" timestamp.
* **Database Driven:** All data is parsed and stored in a persistent **SQLite** database, making the app fast and scalable.

## 🛠️ Tech Stack

* **Backend:**
    * **Python 3**
    * **Flask:** The core web framework.
    * **Flask-SQLAlchemy:** The ORM used to manage the database with Python classes.
    * **Flask Blueprints:** Used to organize the code into modular "features" (admin, search, etc.).
* **Frontend:**
    * HTML5
    * CSS3 / Bootstrap 5
    * JavaScript (for fetching data from the API routes without reloading the page).
* **Database:**
    * **SQLite:** A lightweight, file-based database perfect for this project.
* **Key Libraries:**
    * `python-docx`: For parsing the uploaded `.docx` timetable files.

## 🚀 How to Run This Project

1.  **Clone the repository:**
    ```bash
    git clone [your-repo-url]
    cd [your-repo-name]
    ```

2.  **Create a virtual environment:**
    ```bash
    # On Windows
    python -m venv venv
    .\venv\Scripts\activate

    # On macOS/Linux
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Install the required libraries:**
    ```bash
    pip install Flask Flask-SQLAlchemy python-docx
    ```

4.  **Run the application:**
    ```bash
    python app.py
    ```
    This will create the `university.db` file and start the web server.

5.  **Access the app in your browser:**
    * **Student Dashboard:** `http://127.0.0.1:5000/`
    * **Admin Panel:** `http://127.0.0.1:5000/admin` (Password: `admin123`)
