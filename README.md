# EduManagePro

EduManagePro is a comprehensive full-stack web application for educational management, designed to streamline classroom operations for both teachers and students. The platform provides secure authentication, attendance tracking, assignment management, schedule coordination, and student-teacher communication through study requests.

## Features

### For Teachers
- **Profile Management:** Create and manage teacher profiles with department, qualification, experience, and subjects taught
- **Schedule Management:** Create and manage class schedules with day, time, and subject information
- **Attendance Tracking:** Take attendance for scheduled classes and track student presence
- **Assignment Distribution:** Upload and distribute assignments to students with descriptions
- **Study Requests:** Review and manage study requests from students (accept/reject)
- **Student Overview:** View enrolled students and their information

### For Students
- **Profile Management:** Create and manage student profiles with grade, guardian information, and enrolled subjects
- **Course Enrollment:** Browse and enroll in courses taught by teachers
- **Attendance Records:** View personal attendance history across all classes
- **Assignment Submissions:** Access and submit assignments uploaded by teachers
- **Study Requests:** Send study requests to teachers for course enrollment
- **Teacher Directory:** Browse available teachers and their subjects

### General Features
- **Secure Authentication:** JWT-based authentication with bcrypt password hashing
- **Role-Based Access:** Separate dashboards and functionalities for teachers and students
- **File Upload:** Support for assignment and profile picture uploads using Multer
- **Email Notifications:** Nodemailer integration for email communications
- **Responsive UI:** Modern, mobile-friendly interface built with React and TailwindCSS
- **Protected Routes:** Client-side route protection ensuring secure access

## Tech Stack

### Frontend
- **Framework:** React 19.1.0
- **Build Tool:** Vite 7.0.0
- **Routing:** React Router DOM 7.6.3
- **Styling:** TailwindCSS 3.4.17
- **UI Components:** Lucide React (icons), React Icons
- **HTTP Client:** Axios 1.10.0
- **Notifications:** React Toastify 11.0.5
- **Animations:** Animate.css 4.1.1

### Backend
- **Runtime:** Node.js
- **Framework:** Express 5.1.0
- **Database:** MongoDB (via Mongoose 8.16.1)
- **Authentication:** JWT (jsonwebtoken 9.0.2) + bcrypt 6.0.0
- **File Upload:** Multer 2.0.2
- **Email:** Nodemailer 7.0.4
- **Environment Variables:** dotenv 17.0.1
- **CORS:** cors 2.8.5
- **Dev Tool:** Nodemon 3.1.10

## Getting Started

### Prerequisites

- **Node.js** (v18+ recommended)
- **npm** or **yarn**
- **MongoDB** (local installation or MongoDB Atlas)

### Installation

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd EduManagePro
   ```

2. **Backend Setup:**
   ```bash
   cd Backend
   npm install
   ```

3. **Configure Environment Variables:**
   Create a `.env` file in the `Backend` directory:
   ```env
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/edumanagepro
   JWT_SECRET=your_jwt_secret_key
   ```

4. **Start MongoDB:**
   Ensure MongoDB is running locally or update the connection string in `Backend/Db/config.js`

5. **Run Backend Server:**
   ```bash
   npm run dev
   ```
   Backend will run on `http://localhost:5000`

6. **Frontend Setup:**
   Open a new terminal:
   ```bash
   cd Frontend
   npm install
   ```

7. **Run Frontend Development Server:**
   ```bash
   npm run dev
   ```
   Frontend will run on `http://localhost:5173`

8. **Access the Application:**
   Open your browser and visit [http://localhost:5173](http://localhost:5173)

## Project Structure

```
EduManagePro/
├── Backend/
│   ├── Controllers/
│   │   ├── StudentAuthController.js
│   │   ├── TeacherAuthController.js
│   │   └── DashboardController.js
│   ├── Models/
│   │   ├── Student.js
│   │   ├── Teacher.js
│   │   ├── TeacherSchedule.js
│   │   ├── StudentAttendance.js
│   │   ├── ClassAssignment.js
│   │   ├── StudentAssignment.js
│   │   └── StudyRequest.js
│   ├── Routes/
│   │   ├── StudentAuthenticationRoute.js
│   │   ├── TeacherAuthenticationRoute.js
│   │   ├── TeacherScheduleRoute.js
│   │   └── StudentDashboardRoute.js
│   ├── Middleware/
│   ├── Multer/
│   ├── Nodemailer/
│   ├── Db/
│   │   └── config.js
│   ├── Public/
│   ├── app.js
│   └── package.json
├── Frontend/
│   ├── src/
│   │   ├── Pages/
│   │   │   ├── Home.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── StudentLogin.jsx
│   │   │   ├── TeacherRegister.jsx
│   │   │   ├── StudentRegister.jsx
│   │   │   └── Dashboard/
│   │   │       ├── Student/
│   │   │       │   ├── Student.jsx
│   │   │       │   ├── Profile.jsx
│   │   │       │   ├── Courses.jsx
│   │   │       │   ├── Schedule.jsx
│   │   │       │   └── Teachers.jsx
│   │   │       └── Teacher/
│   │   │           ├── Teacher.jsx
│   │   │           ├── TeacherProfile.jsx
│   │   │           ├── TeacherSchedule.jsx
│   │   │           ├── MyStudents.jsx
│   │   │           └── StudyRequest.jsx
│   │   ├── Components/
│   │   ├── assets/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── public/
│   ├── index.html
│   ├── vite.config.js
│   ├── tailwind.config.js
│   └── package.json
└── README.md
```

## API Endpoints

### Student Routes
- `POST /api/student/register` - Student registration
- `POST /api/student/login` - Student login
- `GET /api/showStudentData` - Get student profile
- `PUT /api/updateStudentData` - Update student profile
- `GET /api/showTeachersData` - Get all teachers
- `POST /api/studyrequest` - Send study request to teacher
- `GET /api/attendance` - Get student attendance records

### Teacher Routes
- `POST /api/teacher/register` - Teacher registration
- `POST /api/teacher/login` - Teacher login
- `GET /api/showTeacherData` - Get teacher profile
- `PUT /api/updateTeacherData` - Update teacher profile
- `POST /api/addSchedule` - Create class schedule
- `GET /api/showSchedule` - Get teacher schedules
- `GET /api/requests` - Get study requests

## Usage

### For Teachers
1. Register as a teacher with your credentials
2. Complete your profile with department, qualification, and subjects
3. Create class schedules for your subjects
4. Take attendance for your scheduled classes
5. Upload assignments for students
6. Review and manage study requests from students

### For Students
1. Register as a student with your credentials
2. Complete your profile with grade and guardian information
3. Browse available teachers and send study requests
4. View your class schedules once enrolled
5. Check your attendance records
6. Access and submit assignments

## Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

## License

This project is open source and available under the [MIT License](LICENSE).

