# Job Portal & Recruitment Management System

A backend-based Job Portal & Recruitment Management System that manages the complete recruitment lifecycle between companies, recruiters, candidates, and administrators. Built with **Node.js**, **Express.js**, and **MongoDB (Mongoose)**, using **JWT authentication** and **bcrypt** password hashing.

---

## Team Details

| S.No | Student Name | Roll No. | Department | Section |
|------|---------------------------|----------|------------|-----------|
| 1 | Jacques Paul | 2462527 | CSE | 5BTCSIOT |
| 2 | Sai Arjun N | 2462528 | CSE | 5BTCSIOT |
| 3 | Prarthana Puthan Purayil | 2462526 | CSE | 5BTCSIOT |
| 4 | Poojaa | 2462525 | CSE | 5BTCSIOT |

**Course:** Advanced JavaScript Backend Frameworks (Node.js & Express JS)
**Semester:** 5th Semester
**Institution:** Christ (Deemed to be University)

---

## Module List

1. User Registration & Authentication
2. Company Profile Management
3. Job Posting Management
4. Job Search & Filtering
5. Candidate Profile & Resume Metadata
6. Job Application Submission
7. Applicant Pipeline Workflow (Applied → Shortlisted → Interview → Offered → Rejected/Hired)
8. Interview Scheduling Records
9. Recruiter Applicant Dashboard
10. Saved Jobs & Job Alerts
11. Offer Management
12. Admin Reports & Hiring Funnel Analytics
13. Role-Based Access Control (Candidate, Recruiter, Admin)

---

## Tech Stack

- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB with Mongoose ODM
- **Authentication:** JWT (JSON Web Tokens)
- **Security:** bcrypt password hashing
- **Testing:** Postman
- **Version Control:** Git & GitHub

---

## Project Structure

project-root/
│
├── config/
│ └── db.js
│
├── models/
│ ├── User.js
│ ├── Company.js
│ ├── JobPosting.js
│ ├── CandidateProfile.js
│ ├── Application.js
│ └── Interview.js
│
├── routes/
│ ├── authRoutes.js
│ ├── jobRoutes.js
│ ├── applicationRoutes.js
│ └── adminRoutes.js
│
├── controllers/
│ ├── authController.js
│ ├── jobController.js
│ ├── applicationController.js
│ └── adminController.js
│
├── middleware/
│ ├── auth.js
│ ├── validate.js
│ └── errorHandler.js
│
├── utils/
│ └── tokenGenerator.js
│
├── .env.example
├── server.js
├── package.json
└── README.md


---

## Setup & Installation

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- [MongoDB](https://www.mongodb.com/) (local instance or a MongoDB Atlas cluster)
- [Postman](https://www.postman.com/) (for API testing)
- Git

### Steps

1. **Clone the repository**
```bash
   git clone <repository-url>
   cd <repository-folder>
```

2. **Install dependencies**
```bash
   npm install
```

3. **Configure environment variables**

   Copy the example environment file and fill in your own values:
```bash
   cp .env.example .env
```

   `.env` should contain:
