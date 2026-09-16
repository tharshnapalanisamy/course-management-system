# course-management-system
Yes! You can use blue, purple, green, orange, and red colors like the hospital management website you shared. Replace your previous code with this colorful version.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Course Management System</title>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #eef2ff, #f0fdf4);
            color: #222;
        }

        header {
            background: linear-gradient(135deg, #4f46e5, #7c3aed);
            color: white;
            text-align: center;
            padding: 30px 15px;
            box-shadow: 0 4px 12px #999;
        }

        header h1 {
            margin-bottom: 8px;
        }

        .container {
            width: 92%;
            max-width: 1150px;
            margin: 30px auto;
        }

        .dashboard {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-bottom: 30px;
        }

        .card {
            color: white;
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 5px 15px #bbb;
        }

        .card h2 {
            font-size: 35px;
            margin-top: 12px;
        }

        .card:nth-child(1) {
            background: linear-gradient(135deg, #2563eb, #38bdf8);
        }

        .card:nth-child(2) {
            background: linear-gradient(135deg, #059669, #34d399);
        }

        .card:nth-child(3) {
            background: linear-gradient(135deg, #ea580c, #fbbf24);
        }

        .form-box,
        .table-box {
            background: white;
            padding: 28px;
            border-radius: 15px;
            box-shadow: 0 5px 15px #ccc;
            margin-bottom: 30px;
        }

        .form-box h2,
        .table-box h2 {
            color: #4f46e5;
            margin-bottom: 20px;
            border-left: 5px solid #7c3aed;
            padding-left: 10px;
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 18px;
        }

        label {
            font-weight: bold;
            color: #374151;
        }

        input,
        select {
            width: 100%;
            padding: 13px;
            margin-top: 7px;
            border: 2px solid #ddd;
            border-radius: 8px;
            outline: none;
            transition: 0.3s;
        }

        input:focus,
        select:focus {
            border-color: #6366f1;
            box-shadow: 0 0 5px #a5b4fc;
        }

        button {
            border: none;
            color: white;
            padding: 12px 22px;
            border-radius: 8px;
            cursor: pointer;
            margin-top: 20px;
            font-weight: bold;
            transition: 0.3s;
        }

        button:hover {
            transform: scale(1.05);
            opacity: 0.9;
        }

        #submitBtn {
            background: #4f46e5;
        }

        .clear-btn {
            background: #6b7280;
            margin-left: 10px;
        }

        .search {
            margin-bottom: 15px;
            border-color: #60a5fa;
        }

        .table-container {
            overflow-x: auto;
        }

        table {
            width: 100%;
            min-width: 850px;
            border-collapse: collapse;
        }

        th,
        td {
            padding: 13px;
            text-align: center;
            border-bottom: 1px solid #ddd;
        }

        th {
            background: #4f46e5;
            color: white;
        }

        tr:nth-child(even) {
            background: #f5f3ff;
        }

        tr:hover {
            background: #e0e7ff;
        }

        .active {
            color: #059669;
            font-weight: bold;
        }

        .inactive {
            color: #dc2626;
            font-weight: bold;
        }

        .edit-btn {
            background: #0284c7;
            margin: 2px;
        }

        .delete-btn {
            background: #dc2626;
            margin: 2px;
        }

        @media (max-width: 768px) {
            .dashboard,
            .form-grid {
                grid-template-columns: 1fr;
            }

            .container {
                width: 95%;
            }

            .form-box,
            .table-box {
                padding: 20px;
            }
        }
    </style>
</head>

<body>

    <header>
        <h1>📚 Course Management System</h1>
        <p>Manage Courses Easily and Efficiently</p>
    </header>

    <div class="container">

        <div class="dashboard">

            <div class="card">
                <p>Total Courses</p>
                <h2 id="totalCourses">0</h2>
            </div>

            <div class="card">
                <p>Active Courses</p>
                <h2 id="activeCourses">0</h2>
            </div>

            <div class="card">
                <p>Inactive Courses</p>
                <h2 id="inactiveCourses">0</h2>
            </div>

        </div>

        <div class="form-box">

            <h2 id="formTitle">Add New Course</h2>

            <form id="courseForm">

                <input type="hidden" id="courseId">

                <div class="form-grid">

                    <div>
                        <label>Course Name</label>
                        <input type="text" id="courseName"
                               placeholder="Enter course name" required>
                    </div>

                    <div>
                        <label>Course Code</label>
                        <input type="text" id="courseCode"
                               placeholder="Enter course code" required>
                    </div>

                    <div>
                        <label>Instructor Name</label>
                        <input type="text" id="instructor"
                               placeholder="Enter instructor name" required>
                    </div>

                    <div>
                        <label>Duration</label>
                        <input type="text" id="duration"
                               placeholder="Example: 6 Months" required>
                    </div>

                    <div>
                        <label>Credits</label>
                        <input type="number" id="credits"
                               placeholder="Enter credits" min="1" required>
                    </div>

                    <div>
                        <label>Status</label>
                        <select id="status" required>
                            <option value="">Select Status</option>
                            <option value="Active">Active</option>
                            <option value="Inactive">Inactive</option>
                        </select>
                    </div>

                </div>

                <button type="submit" id="submitBtn">
                    Add Course
                </button>

                <button type="button"
                        class="clear-btn"
                        onclick="clearForm()">
                    Clear
                </button>

            </form>
        </div>

        <div class="table-box">

            <h2>Course List</h2>

            <input type="text"
                   id="searchInput"
                   class="search"
                   placeholder="🔍 Search course..."
                   onkeyup="displayCourses()">

            <div class="table-container">

                <table>
                    <thead>
                        <tr>
                            <th>S.No</th>
                            <th>Course Name</th>
                            <th>Code</th>
                            <th>Instructor</th>
                            <th>Duration</th>
                            <th>Credits</th>
                            <th>Status</th>
                            <th>Action</th>
                        </tr>
                    </thead>

                    <tbody id="courseTable"></tbody>
                </table>

            </div>
        </div>

    </div>

    <script>
        let courses = JSON.parse(localStorage.getItem("courses")) || [];

        const courseForm = document.getElementById("courseForm");

        courseForm.addEventListener("submit", function(event) {
            event.preventDefault();

            const id = document.getElementById("courseId").value;

            const course = {
                id: id || Date.now(),
                name: document.getElementById("courseName").value,
                code: document.getElementById("courseCode").value,
                instructor: document.getElementById("instructor").value,
                duration: document.getElementById("duration").value,
                credits: document.getElementById("credits").value,
                status: document.getElementById("status").value
            };

            if (id) {
                courses = courses.map(function(item) {
                    return item.id == id ? course : item;
                });
            } else {
                courses.push(course);
            }

            saveCourses();
            clearForm();
            displayCourses();
        });

        function saveCourses() {
            localStorage.setItem("courses", JSON.stringify(courses));
        }

        function displayCourses() {
            const table = document.getElementById("courseTable");
            const searchText = document.getElementById("searchInput")
                .value.toLowerCase();

            table.innerHTML = "";

            const filteredCourses = courses.filter(function(course) {
                return course.name.toLowerCase().includes(searchText) ||
                       course.code.toLowerCase().includes(searchText) ||
                       course.instructor.toLowerCase().includes(searchText);
            });

            filteredCourses.forEach(function(course, index) {

                const row = document.createElement("tr");

                row.innerHTML = `
                    <td>${index + 1}</td>
                    <td>${course.name}</td>
                    <td>${course.code}</td>
                    <td>${course.instructor}</td>
                    <td>${course.duration}</td>
                    <td>${course.credits}</td>
                    <td class="${course.status === "Active" ? "active" : "inactive"}">
                        ${course.status}
                    </td>
                    <td>
                        <button class="edit-btn"
                                onclick="editCourse(${course.id})">
                            Edit
                        </button>

                        <button class="delete-btn"
                                onclick="deleteCourse(${course.id})">
                            Delete
                        </button>
                    </td>
                `;

                table.appendChild(row);
            });

            updateDashboard();
        }

        function updateDashboard() {
            document.getElementById("totalCourses").innerText =
                courses.length;

            document.getElementById("activeCourses").innerText =
                courses.filter(course => course.status === "Active").length;

            document.getElementById("inactiveCourses").innerText =
                courses.filter(course => course.status === "Inactive").length;
        }

        function editCourse(id) {
            const course = courses.find(function(item) {
                return item.id == id;
            });

            if (!course) return;

            document.getElementById("courseId").value = course.id;
            document.getElementById("courseName").value = course.name;
            document.getElementById("courseCode").value = course.code;
            document.getElementById("instructor").value = course.instructor;
            document.getElementById("duration").value = course.duration;
            document.getElementById("credits").value = course.credits;
            document.getElementById("status").value = course.status;

            document.getElementById("formTitle").innerText =
                "Update Course";

            document.getElementById("submitBtn").innerText =
                "Update Course";

            window.scrollTo({
                top: 0,
                behavior: "smooth"
            });
        }

        function deleteCourse(id) {
            if (confirm("Are you sure you want to delete this course?")) {

                courses = courses.filter(function(course) {
                    return course.id != id;
                });

                saveCourses();
                displayCourses();
            }
        }

        function clearForm() {
            courseForm.reset();

            document.getElementById("courseId").value = "";

            document.getElementById("formTitle").innerText =
                "Add New Course";

            document.getElementById("submitBtn").innerText =
                "Add Course";
        }

        displayCourses();
    </script>

</body>
</html>

This version includes:

Blue and purple header

Three colorful dashboard cards

Green active status

Red inactive status

Colored buttons

Table hover colors

Responsive design

Add, edit, delete, and search functions

https://sangeetha-sudo07.github.io/hospital--management--systems/                 use this as model

Use the website as the design model: left sidebar, colorful dashboard cards, clean white sections, and a modern hospital-style layout.

Below is a Course Management System with a similar dashboard design.

Save this as index.html.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Course Management Dashboard</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background: #f4f7fb;
            color: #333;
        }

        .layout {
            display: flex;
            min-height: 100vh;
        }

        /* Sidebar */
        .sidebar {
            width: 240px;
            background: linear-gradient(180deg, #173b73, #2563a6);
            color: white;
            padding: 25px 15px;
        }

        .sidebar h2 {
            text-align: center;
            margin-bottom: 35px;
            font-size: 22px;
        }

        .sidebar a {
            display: block;
            color: white;
            text-decoration: none;
            padding: 15px;
            margin: 10px 0;
            border-radius: 8px;
            transition: 0.3s;
        }

        .sidebar a:hover,
        .sidebar a.active {
            background: rgba(255, 255, 255, 0.2);
        }

        /* Main Content */
        .main {
            flex: 1;
            padding: 25px;
        }

        .topbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: white;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 3px 12px #ddd;
            margin-bottom: 25px;
        }

        .topbar h1 {
            color: #173b73;
        }

        .profile {
            background: #e0f2fe;
            color: #0369a1;
            padding: 10px 15px;
            border-radius: 20px;
            font-weight: bold;
        }

        /* Dashboard Cards */
        .cards {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-bottom: 25px;
        }

        .card {
            padding: 25px;
            color: white;
            border-radius: 14px;
            box-shadow: 0 4px 12px #ccc;
        }

        .card p {
            font-size: 16px;
        }

        .card h2 {
            font-size: 35px;
            margin-top: 12px;
        }

        .card.blue {
            background: linear-gradient(135deg, #2563eb, #60a5fa);
        }

        .card.green {
            background: linear-gradient(135deg, #059669, #34d399);
        }

        .card.orange {
            background: linear-gradient(135deg, #ea580c, #fbbf24);
        }

        /* Sections */
        .section {
            background: white;
            padding: 25px;
            border-radius: 14px;
            box-shadow: 0 3px 12px #ddd;
            margin-bottom: 25px;
        }

        .section h2 {
            color: #173b73;
            margin-bottom: 20px;
            border-left: 5px solid #2563eb;
            padding-left: 10px;
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 18px;
        }

        label {
            font-weight: bold;
            color: #444;
        }

        input,
        select {
            width: 100%;
            padding: 12px;
            margin-top: 7px;
            border: 1px solid #ccc;
            border-radius: 7px;
            outline: none;
        }

        input:focus,
        select:focus {
            border-color: #2563eb;
        }

        button {
            padding: 12px 22px;
            margin-top: 20px;
            border: none;
            border-radius: 7px;
            color: white;
            background: #2563eb;
            cursor: pointer;
            font-weight: bold;
        }

        button:hover {
            background: #173b73;
        }

        .clear-btn {
            background: #64748b;
            margin-left: 10px;
        }

        .search {
            margin-bottom: 15px;
            border: 2px solid #bfdbfe;
        }

        .table-container {
            overflow-x: auto;
        }

        table {
            width: 100%;
            min-width: 850px;
            border-collapse: collapse;
        }

        th,
        td {
            padding: 13px;
            border-bottom: 1px solid #ddd;
            text-align: center;
        }

        th {
            background: #173b73;
            color: white;
        }

        tr:nth-child(even) {
            background: #f8fafc;
        }

        tr:hover {
            background: #dbeafe;
        }

        .active-status {
            color: #059669;
            font-weight: bold;
        }

        .inactive-status {
            color: #dc2626;
            font-weight: bold;
        }

        .edit-btn {
            background: #0891b2;
            margin: 2px;
        }

        .delete-btn {
            background: #dc2626;
            margin: 2px;
        }

        /* Mobile View */
        @media (max-width: 900px) {
            .sidebar {
                width: 190px;
            }

            .cards {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 650px) {
            .layout {
                display: block;
            }

            .sidebar {
                width: 100%;
                text-align: center;
            }

            .sidebar a {
                display: inline-block;
                margin: 5px;
            }

            .main {
                padding: 15px;
            }

            .topbar {
                display: block;
            }

            .profile {
                display: inline-block;
                margin-top: 10px;
            }

            .form-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>

<body>

<div class="layout">

    <!-- Sidebar -->
    <aside class="sidebar">
        <h2>📚 Course Admin</h2>

        <a href="#" class="active">🏠 Dashboard</a>
        <a href="#courseForm">➕ Add Course</a>
        <a href="#courseList">📖 Course List</a>
        <a href="#" onclick="clearAllCourses()">🗑 Clear Courses</a>
    </aside>

    <!-- Main Content -->
    <main class="main">

        <div class="topbar">
            <div>
                <h1>Course Management</h1>
                <p>Welcome to your course dashboard</p>
            </div>

            <div class="profile">
                👤 Admin
            </div>
        </div>

        <!-- Dashboard Cards -->
        <div class="cards">

            <div class="card blue">
                <p>Total Courses</p>
                <h2 id="totalCourses">0</h2>
            </div>

            <div class="card green">
                <p>Active Courses</p>
                <h2 id="activeCourses">0</h2>
            </div>

            <div class="card orange">
                <p>Inactive Courses</p>
                <h2 id="inactiveCourses">0</h2>
            </div>

        </div>

        <!-- Add Course Form -->
        <section class="section" id="courseForm">

            <h2 id="formTitle">Add New Course</h2>

            <form id="courseFormElement">

                <input type="hidden" id="courseId">

                <div class="form-grid">

                    <div>
                        <label>Course Name</label>
                        <input type="text" id="courseName"
                               placeholder="Enter course name" required>
                    </div>

                    <div>
                        <label>Course Code</label>
                        <input type="text" id="courseCode"
                               placeholder="Enter course code" required>
                    </div>

                    <div>
                        <label>Instructor</label>
                        <input type="text" id="instructor"
                               placeholder="Enter instructor name" required>
                    </div>

                    <div>
                        <label>Duration</label>
                        <input type="text" id="duration"
                               placeholder="Example: 6 Months" required>
                    </div>

                    <div>
                        <label>Credits</label>
                        <input type="number" id="credits"
                               placeholder="Enter credits" min="1" required>
                    </div>

                    <div>
                        <label>Status</label>
                        <select id="status" required>
                            <option value="">Select Status</option>
                            <option value="Active">Active</option>
                            <option value="Inactive">Inactive</option>
                        </select>
                    </div>

                </div>

                <button type="submit" id="submitBtn">
                    Add Course
                </button>

                <button type="button"
                        class="clear-btn"
                        onclick="clearForm()">
                    Clear
                </button>

            </form>
        </section>

        <!-- Course List -->
        <section class="section" id="courseList">

            <h2>Course List</h2>

            <input type="text"
                   id="searchInput"
                   class="search"
                   placeholder="🔍 Search course..."
                   onkeyup="displayCourses()">

            <div class="table-container">

                <table>
                    <thead>
                        <tr>
                            <th>S.No</th>
                            <th>Course Name</th>
                            <th>Code</th>
                            <th>Instructor</th>
                            <th>Duration</th>
                            <th>Credits</th>
                            <th>Status</th>
                            <th>Action</th>
                        </tr>
                    </thead>

                    <tbody id="courseTable"></tbody>
                </table>

            </div>
        </section>

    </main>
</div>

<script>
    let courses = JSON.parse(localStorage.getItem("courses")) || [];

    const form = document.getElementById("courseFormElement");

    form.addEventListener("submit", function(event) {
        event.preventDefault();

        const id = document.getElementById("courseId").value;

        const course = {
            id: id || Date.now(),
            name: document.getElementById("courseName").value,
            code: document.getElementById("courseCode").value,
            instructor: document.getElementById("instructor").value,
            duration: document.getElementById("duration").value,
            credits: document.getElementById("credits").value,
            status: document.getElementById("status").value
        };

        if (id) {
            courses = courses.map(function(item) {
                return item.id == id ? course : item;
            });
        } else {
            courses.push(course);
        }

        saveCourses();
        clearForm();
        displayCourses();
    });

    function saveCourses() {
        localStorage.setItem("courses", JSON.stringify(courses));
    }

    function displayCourses() {
        const table = document.getElementById("courseTable");
        const search = document.getElementById("searchInput")
            .value.toLowerCase();

        table.innerHTML = "";

        const filteredCourses = courses.filter(function(course) {
            return course.name.toLowerCase().includes(search) ||
                   course.code.toLowerCase().includes(search) ||
                   course.instructor.toLowerCase().includes(search);
        });

        filteredCourses.forEach(function(course, index) {

            const row = document.createElement("tr");

            row.innerHTML = `
                <td>${index + 1}</td>
                <td>${course.name}</td>
                <td>${course.code}</td>
                <td>${course.instructor}</td>
                <td>${course.duration}</td>
                <td>${course.credits}</td>
                <td class="${course.status === "Active"
                    ? "active-status"
                    : "inactive-status"}">
                    ${course.status}
                </td>
                <td>
                    <button class="edit-btn"
                            onclick="editCourse(${course.id})">
                        Edit
                    </button>

                    <button class="delete-btn"
                            onclick="deleteCourse(${course.id})">
                        Delete
                    </button>
                </td>
            `;

            table.appendChild(row);
        });

        updateCards();
    }

    function updateCards() {
        document.getElementById("totalCourses").innerText =
            courses.length;

        document.getElementById("activeCourses").innerText =
            courses.filter(course => course.status === "Active").length;

        document.getElementById("inactiveCourses").innerText =
            courses.filter(course => course.status === "Inactive").length;
    }

    function editCourse(id) {
        const course = courses.find(function(item) {
            return item.id == id;
        });

        if (!course) return;

        document.getElementById("courseId").value = course.id;
        document.getElementById("courseName").value = course.name;
        document.getElementById("courseCode").value = course.code;
        document.getElementById("instructor").value = course.instructor;
        document.getElementById("duration").value = course.duration;
        document.getElementById("credits").value = course.credits;
        document.getElementById("status").value = course.status;

        document.getElementById("formTitle").innerText =
            "Update Course";

        document.getElementById("submitBtn").innerText =
            "Update Course";

        window.location.hash = "courseForm";
    }

    function deleteCourse(id) {
        if (confirm("Do you want to delete this course?")) {
            courses = courses.filter(function(course) {
                return course.id != id;
            });

            saveCourses();
            displayCourses();
        }
    }

    function clearForm() {
        form.reset();

        document.getElementById("courseId").value = "";

        document.getElementById("formTitle").innerText =
            "Add New Course";

        document.getElementById("submitBtn").innerText =
            "Add Course";
    }

    function clearAllCourses() {
        if (confirm("Delete all courses?")) {
            courses = [];
            saveCourses();
            displayCourses();
        }
    }

    displayCourses();
</script>

</body>
</html>

This follows the model with:

Left-side navigation bar

Top header

Admin profile section

Three colorful dashboard cards

White rounded content boxes

Blue hospital-style theme

Add, edit, delete, search functions

Mobile responsive design

readme content
Course Management System
Project Description

The Course Management System is a simple web-based application developed using HTML, CSS, and JavaScript. It helps users manage course details in an easy and organized way.

The system allows the administrator to add, view, edit, delete, and search courses. It also displays the total number of courses, active courses, and inactive courses using dashboard cards.

Features

Modern dashboard design

Sidebar navigation

Add new course details

View all available courses

Edit existing course details

Delete courses

Search courses

Display total courses

Display active courses

Display inactive courses

Responsive design for mobile and desktop

Data storage using browser localStorage

Technologies Used

HTML5 – To create the structure of the website

CSS3 – To design and style the dashboard

JavaScript – To add functionality and interactivity

LocalStorage – To save course details in the browser

Course Details

The application stores the following information:

Course Name

Course Code

Instructor Name

Duration

Credits

Course Status

Dashboard

The dashboard contains three cards:

Total Courses – Displays the total number of courses.

Active Courses – Displays the number of active courses.

Inactive Courses – Displays the number of inactive courses.

Project Structure
Course-Management-System/
│
├── index.html
└── README.md
How to Run the Project

Download or clone the project.

Open the project folder.

Open the index.html file in any web browser.

The Course Management System will be displayed.

Enter course details and click Add Course.

How to Use
Add Course

Enter the course name.

Enter the course code.

Enter the instructor name.

Enter the course duration.

Enter the credits.

Select the course status.

Click the Add Course button.

Edit Course

Click the Edit button in the course table.

Modify the required details.

Click Update Course.

Delete Course

Click the Delete button.

Confirm the deletion.

Search Course

Enter the course name, course code, or instructor name in the search box.

Advantages

Easy to use

Simple and attractive interface

Saves time in managing courses

Reduces manual record maintenance

Works without an external database

Can be used on different screen sizes

Limitations

Data is stored only in the browser.

It does not have a login system.

It does not use a server-side database.

Data may be lost if browser storage is cleared.

Future Enhancements

Add student registration

Add student login and admin login

Connect with a database

Add course enrollment

Add teacher management

Generate course reports

Add online course payment

Add course completion certificates

Conclusion

The Course Management System provides a simple and effective way to manage course information. It demonstrates the use of HTML, CSS, and JavaScript to create an interactive dashboard application. This project can be further improved by adding a backend database and user authentication.
