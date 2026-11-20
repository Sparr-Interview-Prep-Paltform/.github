# Sparr: AI-Powered Interview Preparation Platform

An intelligent interview preparation platform that helps job seekers evaluate their qualifications, identify skill gaps, prepare for technical interviews, and improve their interview performance through AI-powered analysis and personalized feedback.

---

## Table of Contents

- [Introduction](#introduction)
- [The Problem](#the-problem)
- [Key Features](#key-features)
- [How It Works](#how-it-works)
- [System Architecture](#system-architecture)
- [Technology Stack](#technology-stack)
- [Project Components](#project-components)
- [Main Workflow](#main-workflow)
- [Getting Started](#getting-started)
- [Environment Configuration](#environment-configuration)
- [Background Processing](#background-processing)
- [Testing](#testing)
- [Security](#security)
- [Deployment](#deployment)
- [Future Work](#future-work)
- [Team](#team)

---

## Introduction

The AI-Powered Interview Preparation Platform is a web application designed to help candidates prepare for job interviews based on their actual skills, qualifications, and target job opportunities.

Unlike traditional interview preparation tools that provide generic questions and answers, this platform analyzes a candidate's resume against a specific job description, identifies missing and matching skills, and generates a personalized learning roadmap.

Candidates can then participate in AI-powered mock interviews, receive evaluations for their answers, and obtain a comprehensive final report highlighting their strengths and areas for improvement.

The platform consists of three main components:

1. **Frontend:** A React-based web application providing the user interface.
2. **Backend:** A Laravel REST API responsible for authentication, business logic, data management, and workflow orchestration.
3. **AI Service:** A Python-based service responsible for resume and job-description analysis, interview question generation, answer evaluation, and report generation.

## The Problem

Job seekers often struggle to understand whether their qualifications match a job opportunity and how to prepare effectively for its interview.

Common challenges include:

- Not knowing which skills are missing from their resumes.
- Difficulty identifying the most important requirements of a job description.
- Spending time preparing for irrelevant interview questions.
- Having no objective way to evaluate interview performance.
- Receiving generic feedback that does not address individual weaknesses.

This platform addresses these challenges by connecting resume analysis, job requirements, personalized learning, and simulated interviews into one integrated workflow.

## Key Features

### 1. Authentication and User Management

- Secure user registration and authentication.
- Token-based API authentication.
- User-specific resource management.
- Authorization and ownership verification.

### 2. Resume Management

- Upload and manage resumes.
- Extract relevant information and technical skills using AI.
- Store extracted skills for subsequent analysis.
- Track resume parsing status and failures.

### 3. Job Description Management

- Create and manage multiple job descriptions.
- Extract required skills and their importance using AI.
- Track job description parsing status.
- Associate job descriptions with candidate resumes.

### 4. Skill Gap Analysis

- Compare extracted resume skills against job requirements.
- Identify matching and missing skills.
- Calculate an overall skill match percentage.
- Consider skill importance and candidate confidence.
- Store analysis results for future reference.

### 5. Personalized Learning Roadmap

- Generate a learning roadmap based on identified skill gaps.
- Prioritize missing skills according to job requirements.
- Provide a structured preparation path.
- Store roadmap results for later retrieval.

### 6. AI-Powered Mock Interviews

- Generate technical interview questions based on the candidate's resume, job description, and skill analysis.
- Create interview sessions containing ten initial questions.
- Support multiple interview sessions for the same job opportunity.
- Track interview progress and question-answer relationships.

### 7. Answer Evaluation

- Submit answers to interview questions.
- Evaluate answers asynchronously through the Python AI service.
- Provide individual scores and feedback.
- Generate improved answer suggestions.
- Track evaluation status and failures.

### 8. Final Interview Reports

- Calculate an overall interview score based on evaluated answers.
- Generate comprehensive AI-powered interview reports.
- Provide an interview summary.
- Identify improvement areas.
- Evaluate performance across different dimensions.
- Highlight discrepancies between expected and demonstrated knowledge.
- Preserve evaluation results independently of report generation status.

### 9. AI Failure Handling and Retry Mechanisms

- Centralized AI error classification.
- Automatic retries for recoverable failures.
- Manual retry endpoints for failed AI operations.
- Execution tracking to prevent stale jobs from overwriting newer results.
- Separate status tracking for AI-dependent operations.

---

## How It Works

The platform follows a structured preparation process:
<img width="1408" height="768" alt="Gemini_Generated_Image_oxo29roxo29roxo2" src="https://github.com/user-attachments/assets/f22af4e9-ceee-487f-ac26-7e7e2fb60b11" />


1. The candidate uploads a resume.
2. The AI service extracts the candidate's skills.
3. The candidate submits a job description.
4. The AI service extracts the job requirements and their importance.
5. The backend compares both skill sets and generates a gap analysis.
6. A personalized learning roadmap is generated.
7. The candidate starts a mock interview.
8. The AI service generates interview questions.
9. The candidate answers the questions one by one.
10. Each answer is evaluated independently.
11. Once all answers have been evaluated, the backend prepares the final report.
12. The AI service generates the final report, which is saved and made available to the candidate.

## System Architecture

The application follows a separated frontend, backend, and AI-service architecture.

<img width="1024" height="935" alt="image" src="https://github.com/user-attachments/assets/88a0462c-c7fe-4405-b167-6b39ac559051" />


### Frontend

The React application communicates with the Laravel API and provides the user interface for all platform features.

### Backend

The Laravel application acts as the central application layer. It handles:

- Authentication and authorization.
- Database operations.
- Business logic and workflow management.
- Request validation and API responses.
- Background job dispatching.
- AI-service communication.
- Failure handling and retry mechanisms.

### AI Service

The Python application provides AI-related functionality through HTTP endpoints.

It is responsible for:

- Resume parsing.
- Job description parsing.
- Skill analysis and roadmap generation.
- Interview question generation.
- Interview answer evaluation.
- Final report generation.

The backend remains responsible for application state and workflow coordination, while the Python service handles AI processing.

---

## Technology Stack

| Component | Technologies |
|---|---|
| Frontend | React, JavaScript |
| Backend | PHP, Laravel 13 |
| Database | MySQL |
| Authentication | Laravel Sanctum |
| AI Service | Python |
| Backend-AI Communication | HTTP / REST |
| Background Processing | Laravel Queues |
| Containerization | Docker, Docker Compose |
| API Testing | PHPUnit, Postman |
| Version Control | Git, GitHub |

---

## Project Components

The system is divided into three independently maintained components.

### 1. Frontend Repository

**Technology:** React

Responsible for the user-facing application.

Main responsibilities:

- User authentication interfaces.
- Resume and job description management.
- Skill gap analysis visualization.
- Learning roadmap presentation.
- Mock interview experience.
- Answer submission and feedback.
- Final report visualization.

Repository: `[Frontend Repository URL]`

### 2. Backend Repository

**Technology:** Laravel 13, PHP, MySQL

Responsible for the REST API and application logic.

Main responsibilities:

- Authentication and authorization.
- Resource management.
- Database relationships and persistence.
- API validation and response formatting.
- Business services and workflow orchestration.
- Background jobs and queue management.
- AI-service integration.
- Retry mechanisms and failure tracking.

Repository: [Backend Repository URL](https://github.com/Sparr-Interview-Prep-Paltform/gsg-interview-prep-api)

### 3. AI Service Repository

**Technology:** Python

Responsible for AI-powered processing.

Main responsibilities:

- Resume information and skill extraction.
- Job description analysis.
- Skill gap and learning roadmap generation.
- Interview question generation.
- Individual answer evaluation.
- Final interview report generation.

Repository: [AI Service Repository URL](https://github.com/Sparr-Interview-Prep-Paltform/ai-service)

---

## Main Workflow

### Resume and Job Description Processing

<img width="1024" height="572" alt="image" src="https://github.com/user-attachments/assets/1140aadb-64d0-4a70-b4bc-1f4bc3f41979" />


### Skill Gap Analysis and Roadmap

<img width="1024" height="765" alt="image" src="https://github.com/user-attachments/assets/4dddd2b0-7569-4003-ae0c-cd3033666c53" />


### Interview and Evaluation

<img width="825" height="1024" alt="image" src="https://github.com/user-attachments/assets/7f577318-8817-4281-8ca8-5e9f30dc2979" />


### Interview and Report Statuses

Interview completion and report completion are separate stages.

An interview becomes `COMPLETED` when the candidate has submitted all ten answers. Answer evaluation can continue asynchronously after that.

The final report is prepared only after all answers have been evaluated successfully.

This separation allows the system to track interview progress independently from AI evaluation and report generation.

---

## Getting Started

The following instructions describe the general local development setup. Refer to each component's repository for its exact dependencies, commands, and configuration.

### Prerequisites

Install the following tools:

- Git
- Docker
- Docker Compose
- Node.js and npm
- Python 

### 1. Clone the Repositories

```bash
git clone [FRONTEND_REPOSITORY_URL]
git clone https://github.com/Sparr-Interview-Prep-Paltform/gsg-interview-prep-api
git clone https://github.com/Sparr-Interview-Prep-Paltform/ai-service
```

### 2. Configure the Backend

Navigate to the backend repository:

```bash
cd gsg-interview-prep-api
```

Create the environment file:

```bash
cp .env.example .env
```

Configure the database, queue, application URL, and Python AI service connection.

Build and start the Docker containers:

```bash
docker compose up -d --build
```

Install dependencies and generate the application key if these are not already handled by the project's Docker setup:

```bash
composer install
php artisan key:generate
```

Run database migrations:

```bash
php artisan migrate
```

Start a queue worker if it is not already running as a Docker service:

```bash
php artisan queue:work
```

### 3. Configure the AI Service

Navigate to the AI-service repository:

```bash
cd [AI_SERVICE_DIRECTORY]
```

Follow its installation instructions, install Python dependencies, configure its environment variables, and start the application.

The AI service must be reachable from the Laravel backend.

### 4. Configure the Frontend

Navigate to the frontend repository:

```bash
cd [FRONTEND_DIRECTORY]
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

---

## Environment Configuration

Each component should maintain its own environment configuration.

### Backend

The Laravel environment should include configuration for:

- Application environment and URL.
- MySQL connection.
- Queue connection.
- Cache and session drivers.
- Python AI service URLs.
- Authentication and CORS settings.
- File storage.

### AI Service

The Python service should configure:

- Application host and port.
- AI model or provider credentials.
- Model configuration.

---

## Background Processing

The backend uses Laravel queues to handle operations that should not block normal API requests.

Examples include:

- Resume parsing.
- Job description parsing.
- Learning roadmap generation.
- Interview question generation.
- Answer evaluation.
- Final report generation.
- AI interview cleanup.

This approach keeps request-response cycles responsive and allows expensive AI operations to execute asynchronously.

AI-dependent operations maintain their own execution status and error information.

Automatic retries are used for recoverable failures, while manual retry endpoints allow users to restart eligible failed operations.

---

## Testing

The backend uses PHPUnit for automated testing.

Postman can also be used for manual API testing and integration verification.

Important testing areas include:

- Authentication and authorization.
- Resource ownership and access control.
- Resume and job description parsing.
- Skill gap analysis and roadmap generation.
- Interview creation and question generation.
- Answer submission and evaluation.
- Final report generation.
- AI-service failures and retry behavior.
- Duplicate requests and concurrent operations.
- API validation and error responses.

---

## Security

Security is an important part of the platform architecture.

Key considerations include:

- Token-based authentication using Laravel Sanctum.
- Authorization and resource ownership checks.
- Input validation and controlled API responses.
- Protection against unauthorized resource access.
- Secure handling of uploaded resumes.
- Environment-based secret management.
- Restricted access to internal AI-service endpoints.
- HTTPS for production communication.
- Database access restricted to trusted services.
- Protection against stale background jobs overwriting newer execution results.

---

## Deployment

The whole system is deployed on AWS server: [Demo](https://sparr-ai.mooo.com/)

---

## Future Work

Potential improvements and extensions include:

### Platform Improvements

- Support for additional resume formats.
- More detailed candidate profiles.
- Interview history and performance comparisons.
- Advanced filtering and search.
- More interview types and difficulty levels.
- Improved learning roadmap personalization.

### AI Improvements

- More advanced resume analysis.
- Adaptive interview difficulty based on candidate performance.
- More detailed feedback and evaluation criteria.
- Improved answer evaluation consistency.
- Personalized learning recommendations based on interview results.
- Support for additional programming languages and technical domains.

### Infrastructure and Performance

- Horizontal scaling of backend and AI services.
- Dedicated and scalable queue infrastructure.
- Improved caching strategies.
- Object storage for uploaded files.
- Centralized logging and monitoring.
- Automated deployment pipelines.
- More comprehensive automated integration and feature tests.
- Improved AI-service resource management and cleanup.

---

## Team

Developed as part of the Gaza Sky Geeks Market Ready Developer Program.

The project team consists of:

- 2 Backend Developers
- 1 Frontend Developer
- 1 AI Developer

The project follows a collaborative development approach, with responsibilities distributed across frontend development, backend engineering, and AI integration.

---

## Acknowledgements

Special thanks to Gaza Sky Geeks and the Market Ready Developer Program for providing the learning environment and support throughout the development of this project.

---

**Note:** This project is under active development. Features, architecture, and setup instructions may evolve as development progresses.

