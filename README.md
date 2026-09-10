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

   PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRES_IN=1d


   > **Note:** `.env` is excluded from version control via `.gitignore`. Never commit real secrets.

4. **Start MongoDB**

   Ensure your local MongoDB instance is running, or that your MongoDB Atlas cluster is accessible and the `MONGO_URI` is correct.

5. **Run the server**

   Development mode (with auto-restart, if `nodemon` is configured):
```bash
   npm run dev
```

   Production mode:
```bash
   npm start
```

6. **Verify the server is running**

   The API should now be available at:

http://localhost:5000


7. **Test the APIs**

   Import the Postman collection (`postman_collection.json`, if included in the repo) into Postman, or manually hit the endpoints listed below using the base URL above.

---

## API Endpoints

### Authentication

| Method | Endpoint | Description |
|--------|----------|--------------|
| POST | `/api/auth/register` | Register a candidate or recruiter |
| POST | `/api/auth/login` | Authenticate a user and receive a JWT |

### Company

| Method | Endpoint | Description |
|--------|----------|--------------|
| POST | `/api/companies` | Create a company profile (Recruiter) |
| GET | `/api/companies/:id` | View company details |
| PUT | `/api/companies/:id` | Update company information (Recruiter) |

### Jobs

| Method | Endpoint | Description |
|--------|----------|--------------|
| POST | `/api/jobs` | Recruiter creates a job posting |
| GET | `/api/jobs` | View all job postings |
| GET | `/api/jobs/search` | Search and filter jobs (title, skills, location, experience, status) |
| PUT | `/api/jobs/:id` | Update a job posting (Recruiter) |
| DELETE | `/api/jobs/:id` | Delete/close a job posting (Recruiter) |

### Candidate Profile

| Method | Endpoint | Description |
|--------|----------|--------------|
| POST | `/api/candidates/profile` | Create/update candidate profile |
| GET | `/api/candidates/profile/:id` | View a candidate profile |

### Applications

| Method | Endpoint | Description |
|--------|----------|--------------|
| POST | `/api/applications` | Candidate applies for a job |
| GET | `/api/applications/:id` | View a specific application |
| GET | `/api/applications/job/:jobId` | Recruiter views applicants for a job |
| PUT | `/api/applications/:id/stage` | Update application pipeline stage |

### Interviews

| Method | Endpoint | Description |
|--------|----------|--------------|
| POST | `/api/interviews` | Schedule an interview |
| GET | `/api/interviews/:applicationId` | View interview details for an application |
| PUT | `/api/interviews/:id` | Update interview feedback/status |

### Saved Jobs & Alerts

| Method | Endpoint | Description |
|--------|----------|--------------|
| POST | `/api/saved-jobs` | Save a job posting |
| GET | `/api/saved-jobs/:candidateId` | View saved jobs for a candidate |
| POST | `/api/job-alerts` | Create a job alert |

### Offers

| Method | Endpoint | Description |
|--------|----------|--------------|
| POST | `/api/offers` | Record an offer for a candidate |
| PUT | `/api/offers/:id` | Update offer status (accepted/rejected) |

### Admin & Analytics

| Method | Endpoint | Description |
|--------|----------|--------------|
| GET | `/api/admin/reports/funnel` | View hiring funnel analytics |
| GET | `/api/admin/reports/jobs` | View job posting reports |

> Update this list to match the exact routes implemented in your final `routes/` files before submission.

---

## Authentication & Roles

Protected routes require a JWT in the request header:

Authorization: Bearer <token>


Roles supported: `Candidate`, `Recruiter`, `Admin` — enforced via role-based authorization middleware on each route.

---

## Error Handling

All errors are returned as consistent JSON via a centralized error-handling middleware:

```json
{
  "success": false,
  "message": "Error description"
}
```

Common status codes: `201`, `400`, `401`, `403`, `404`, `409`, `500`.

---

## License

This project was developed for academic purposes as part of CIA-3, Advanced JavaScript Backend Frameworks (Node.js & Express JS), 5th Semester, Christ (Deemed to be University).
