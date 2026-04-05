## Merit Plus Education

Merit Plus Education is a role-based educational platform that allows visitors to make real-time inquiries and enables students, teaching assistants (TAs), and administrators to manage academic workflows through a structured web system.

Live Website: https://meritpluseducation.com

## Purpose

Centralize student support and academic management by providing:

- Real-time inquiry support for visitors
- Structured homework submission and grading workflows
- Role-based academic reporting and student management
- Assessment, objective, and career planning tools

## User Roles & Capabilities

**Visitor**

- Interact with support in real time via live chat
- No authentication required

**Student**

- Secure login
- Submit and view homework assignments, grades, and feedback
- Take timed online assessments
- View academic and behavioral reports
- Manage personal objectives and weekly plans
- View student events and to-do items
- Complete behavioral, career, and student behavior assessments
- Explore schools and career wage data
- Chat with an AI learning assistant

**Teaching Assistant (TA)**

- Secure login
- Create student accounts
- Create, assign, and grade homework
- Create academic reports for assigned students
- View assessment results and behavioral profiles
- Manage objectives and contracts for assigned students

**Administrator**

- Full system access
- Create and manage TA and student accounts
- Assign students to TAs
- Assign and grade homework
- Create academic reports for any student
- Manage assessments, announcements, contracts, and weekly plans
- View platform-wide stats and click tracking reports
- Accept live chat requests from visitors

## Key Features

- Role-based UI and access control (Visitor, Student, TA, Admin)
- Real-time live chat for visitor inquiries using WebSocket (STOMP)
- Homework creation, assignment, submission, grading, and feedback
- Timed online assessments with auto-grading support
- Behavioral, career, and student behavior profile assessments
- Student performance reports with scores and comments
- Objective tracking with start/end dates
- Weekly planner for students (staff can review and annotate)
- Contract management with signed document upload (AWS S3)
- School explorer with U.S. College Scorecard data
- Career wage data sourced from the Bureau of Labor Statistics API
- Platform-wide overview stats and per-student/instructor stats
- Announcement system with activate/deactivate controls
- SMS notifications with student consent tracking
- Button click tracking with scheduled email reports to admin
- Email notifications for next-day event reminders and homework assignments
- AI learning assistant with streaming responses, voice input (Web Speech API), and built-in TTS readout
- Bilingual UI (English / Chinese) via i18n
- Secure authentication and authorization using JWT
- Responsive UI for desktop and mobile devices

## Tech Stack

**Frontend**

- React
- Ant Design
- Redux
- React Router
- i18n (en / zh)
- SCSS
- dayjs
- STOMP.js (WebSocket live chat)

**Backend**

- Spring Boot
- Spring Data JDBC
- MySQL
- WebSocket / STOMP (real-time chat)
- RESTful APIs

**Infrastructure**

- AWS EC2
- AWS S3 (signed document storage)
- Docker
- Nginx
- Cloudflare (WAF, DDoS mitigation, rate limiting)
- Let's Encrypt (SSL)

**External Integrations**

- U.S. College Scorecard API — school tuition/admissions data
- Bureau of Labor Statistics (BLS) API — career wage data
- SMTP email — event reminders, inquiry notifications, click reports
- SMS — student notifications with consent tracking

## Architecture Overview

- Frontend communicates with the backend via RESTful APIs
- Authentication is handled using JWT (stored in Authorization header)
- Role-based authorization is enforced via JWT claims and backend interceptors
- Real-time visitor chat is handled through STOMP over WebSocket connections
- Spring Boot manages business logic, authentication, and authorization
- MySQL is used for persistent data storage (users, homework, reports, assessments, etc.)
- Soft-delete pattern (`is_deleted`) is used across most tables
- Scheduled backend jobs handle: daily event reminder emails, button click reports every 2 days, and weekly cleanup of excess profile assessment records
- Contract signed documents are stored in AWS S3
- Nginx acts as a reverse proxy and SSL terminator
- The application is containerized using Docker
- Cloudflare provides WAF and DDoS mitigation at the edge

## Security

- HTTPS enforced across the platform
- JWT-based authentication and authorization
- Role-based access control (RBAC) enforced via JWT claims on every endpoint
- WebSocket connections secured using authenticated JWT sessions
- Cloudflare WAF and DDoS protection at the edge
- Sensitive credentials managed via environment variables
- No sensitive data exposed on the client side

---

🔒 Source code is private. Available upon request.
