## Merit Plus Education

Merit Plus Education is a role-based educational platform that allows visitors to make real-time inquiries and enables students, teaching assistants (TAs), and administrators to manage academic workflows through a structured web system.

Live Website: https://meritpluseducation.com

## Purpose

The purpose of Merit Plus Education is to centralize student support and academic management by providing:

Real-time inquiry support for visitors

Structured homework submission and grading workflows

Role-based academic reporting and student management

## User Roles & Capabilities

Visitor

Interact with support in real time for inquiries

No authentication required

Student

Secure login

Submit homework assignments

View homework grades, feedback, and scores

View academic reports created by TA or admin

Manage a personal to-do list

View homework assigned by their TA or admin

Teaching Assistant (TA)

Secure login

Create student accounts

Create homework assignments

Assign homework to students assigned by an admin

Grade homework with feedback and scores

Create academic reports for students assigned to them

Administrator

Full system access

Create and manage TA and student accounts

Assign students to TAs

Assign homework to students

Grade homework with feedback and scores

Create academic reports for any student

Oversee overall system operations

## Key Features

- Role-based UI and access control (Visitor, Student, TA, Admin)
- Real-time live chat for visitor inquiries using WebSocket
- Homework creation, assignment, submission, grading, and feedback
- Student performance reports with scores and comments
- Email notifications for:
  - Next-day appointment reminders (scheduled)
  - Homework assignment notifications
- Secure authentication and authorization using JWT
- Responsive UI for desktop and mobile devices

## Tech Stack

Frontend

React

Ant Design

HTML5 / CSS3

## Backend

Spring Boot

MySQL

WebSocket (real-time inquiry chat)

RESTful APIs

## Infrastructure

AWS EC2

Docker

Nginx

Cloudflare

Let's Encrypt (SSL)

## Architecture Overview

- The frontend communicates with backend services via RESTful APIs
- Authentication is handled using JWT (JSON Web Token)
- Role-based authorization is enforced using JWT claims
- Real-time visitor inquiries are handled through WebSocket connections
- Spring Boot manages business logic, authentication, and authorization
- MySQL is used for persistent data storage (users, homework, reports)
- Email notifications are sent automatically when homework is assigned to a student
- Scheduled Appointment reminder emails are sent one day in advance
- Notification logic is handled by backend services to ensure reliability
- Nginx acts as a reverse proxy and SSL terminator
- The application is containerized using Docker
- Cloudflare provides Web Application Firewall (WAF) and DDoS mitigation
- Rate limiting and bot protection are handled at the edge

## Security

- HTTPS enforced across the platform
- JWT (JSON Web Token) based authentication
- Role-based access control (RBAC) enforced via JWT claims
- Secure REST API authorization using JWT validation
- Cloudflare WAF and DDoS protection at the edge
- WebSocket connections secured using authenticated JWT sessions
- Sensitive credentials managed using environment variables
- No sensitive data exposed on the client side




🔒 Source code is private. Available upon request.
