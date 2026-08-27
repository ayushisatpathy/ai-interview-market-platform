# 🎯 Prept — AI-Powered Interview Platform

> **Practice smarter. Interview better. Hire with confidence.**

Prept is a full-stack AI-powered interview platform designed to make technical interview preparation more realistic, interactive, and accessible.

The platform supports two user experiences:

* 👨‍💻 **Candidates** — practice interviews, explore opportunities, and improve through AI-powered preparation.
* 🧑‍💼 **Interviewers** — create interviewer profiles, manage their interview experience, and connect with candidates.

The project was built as a production-style full-stack application with authentication, role-based access, AI integration, database persistence, security middleware, server-side actions, and cloud deployment.

### 🚀 Live Demo

**[Live Demo — Prept](YOUR_VERCEL_DEPLOYMENT_URL)**

---

## ✨ Why I Built This

Traditional interview preparation often relies on static question lists and doesn't replicate the pressure or unpredictability of a real interview.

Prept was built around a simple idea:

> **Interview preparation should feel more like an actual interview and less like memorizing questions.**

The platform brings together AI-powered interview preparation, candidate workflows, interviewer workflows, authentication, secure backend operations, and a modern user experience in one application.

---

# 🚀 Key Features

## 🤖 AI-Powered Interview Preparation

* AI-generated interview questions
* Role-oriented interview preparation
* Dynamic question generation
* AI-assisted interview workflows
* Designed to make practice sessions closer to real interview scenarios

## 👤 Role-Based User Experience

Users select how they want to use the platform during onboarding.

### Interviewee

Candidates can:

* Enter the interview preparation flow
* Explore available opportunities
* Practice interviews
* Use the platform as an interview preparation tool

### Interviewer

Interviewers can create a professional profile containing:

* Current job title
* Company
* Years of experience
* Areas of expertise
* Professional bio

This information can be used to build a more structured interviewer experience.

---

## 🔐 Authentication & Authorization

Authentication is implemented using **Clerk**.

The application includes:

* Secure authentication
* Protected routes
* User session management
* Role-based access
* Onboarding state handling
* Client-side role-based navigation

The application distinguishes between:

```text
UNASSIGNED
    ↓
ONBOARDING
    ↓
INTERVIEWEE / INTERVIEWER
```

This allows the application to provide different experiences based on the user's role.

---

## 🛡️ Application Security

Security is handled using **Arcjet** alongside Clerk.

The application uses:

* Shield protection
* Bot detection
* Protected application routes
* Authentication-aware request handling
* Trusted webhook handling

Security checks are integrated into the application's request layer rather than being treated as an afterthought.

---

## 🗄️ Database & Backend

The project uses **Prisma ORM** for database access.

Backend functionality is implemented using **Next.js Server Actions**, allowing server-side business logic and database operations to live alongside the application.

Examples include:

* User onboarding
* Role updates
* Interviewer profile creation
* Dashboard data
* AI question generation
* Database-backed application workflows

Example architecture:

```text
Client
  │
  ▼
Next.js UI
  │
  ▼
Server Actions
  │
  ├── Authentication
  │
  ├── Business Logic
  │
  ├── AI Services
  │
  └── Prisma ORM
          │
          ▼
       Database
```

---

# 🧠 AI Integration

The platform integrates Google's Gemini models for AI-powered functionality.

AI is used to support interview-related functionality such as question generation and intelligent interview preparation.

The AI layer is designed so that model-powered functionality remains separated from the UI and can be evolved independently.

This makes it easier to:

* Change models
* Improve prompts
* Add evaluation logic
* Introduce structured AI responses
* Expand interview intelligence

---

# 💻 Tech Stack

| Category                                 | Technology                          |
| ---------------------------------------- | ----------------------------------- |
| **Framework**                            | Next.js                             |
| **Frontend**                             | React                               |
| **Language**                             | JavaScript / JSX                    |
| **Styling**                              | Tailwind CSS                        |
| **UI Components**                        | shadcn/ui-style reusable components |
| **Authentication**                       | Clerk                               |
| **Authorization**                        | Role-based access control           |
| **Backend**                              | Next.js Server Actions              |
| **ORM**                                  | Prisma                              |
| **Database**                             | PostgreSQL-compatible database      |
| **AI**                                   | Google Gemini                       |
| **Security**                             | Arcjet                              |
| **Real-time / Interview Infrastructure** | Stream                              |
| **Deployment**                           | Vercel                              |
| **Version Control**                      | Git + GitHub                        |

---

# 🏗️ Architecture

Prept follows a full-stack Next.js architecture where the frontend, backend logic, authentication and database layer are integrated into a single application.

```text
                    ┌─────────────────────┐
                    │       Browser       │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │     Next.js App     │
                    │   App Router + UI   │
                    └──────────┬──────────┘
                               │
              ┌────────────────┼────────────────┐
              │                │                │
              ▼                ▼                ▼
        ┌───────────┐    ┌────────────┐   ┌────────────┐
        │   Clerk   │    │  Server    │   │  Arcjet    │
        │   Auth    │    │  Actions   │   │  Security  │
        └───────────┘    └─────┬──────┘   └────────────┘
                               │
                    ┌──────────┼──────────┐
                    │                     │
                    ▼                     ▼
              ┌───────────┐        ┌────────────┐
              │  Prisma   │        │   Gemini   │
              │    ORM    │        │     AI     │
              └─────┬─────┘        └────────────┘
                    │
                    ▼
              ┌───────────┐
              │ Database  │
              └───────────┘

                         + Stream
                    Real-time services
```

---

# 📁 Project Structure

```text
ai-interview-market-platform/
│
├── app/
│   ├── (main)/
│   │   └── onboarding/
│   │       └── page.jsx
│   │
│   ├── layout.js
│   └── page.jsx
│
├── actions/
│   ├── aiQuestions.jsx
│   ├── dashboard.js
│   └── onboarding.js
│
├── components/
│   ├── RoleRedirect.jsx
│   ├── UpgradeModal.jsx
│   └── ui/
│
├── hooks/
│   └── use-fetch.js
│
├── lib/
│   ├── data.js
│   └── ...
│
├── prisma/
│   ├── schema.prisma
│   └── seed.js
│
├── public/
│
├── proxy.js
│
├── package.json
└── README.md
```

---

# 🔄 Core User Flow

## Candidate Flow

```text
Landing Page
     ↓
Authentication
     ↓
Onboarding
     ↓
Choose Interviewee
     ↓
Choose / Start Practice
     ↓
AI Interview Experience
     ↓
Performance / Interview Workflow
```

## Interviewer Flow

```text
Landing Page
     ↓
Authentication
     ↓
Onboarding
     ↓
Choose Interviewer
     ↓
Enter Professional Information
     ↓
Create Interviewer Profile
     ↓
Dashboard
```

---

# 🧩 Engineering Highlights

### 1. Server Actions

Instead of creating unnecessary API endpoints for every mutation, the project uses Next.js Server Actions for server-side operations.

For example:

```javascript
"use server";

export const completeOnboarding = async (data) => {
  // Authentication
  // Validation
  // Database update
};
```

This keeps server-side business logic close to the feature it belongs to.

---

### 2. Role-Based Routing

The application uses a dedicated role-aware redirect layer to control access based on the user's current role.

This prevents users from unintentionally accessing areas intended for another role while still allowing onboarding to be completed before role-specific routing begins.

---

### 3. Protected Application Layer

Authentication and security are handled before requests reach protected application functionality.

```text
Request
   ↓
Clerk
   ↓
Arcjet
   ↓
Role Validation
   ↓
Application
```

---

### 4. Reusable UI

The interface is built using reusable components rather than duplicating UI logic throughout the application.

Examples include:

* Buttons
* Inputs
* Textareas
* Labels
* Modals
* Titles
* Section labels
* Role selection components

This makes the UI easier to maintain and extend.

---

### 5. Production Deployment

The application is deployed on **Vercel** with environment-based configuration for external services.

Production secrets are kept outside the repository using environment variables.

```text
.env
    ↓
NOT committed to Git
    ↓
Vercel Environment Variables
    ↓
Production Deployment
```

---

# 🔐 Environment Variables

Create a local `.env` / `.env.local` file and configure the required service credentials.

Typical configuration includes:

```env
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=

DATABASE_URL=

ARCJET_KEY=

GEMINI_API_KEY=

STREAM_API_KEY=
STREAM_SECRET_KEY=
```

> **Never commit `.env` files or API keys to GitHub.**

For production, configure these variables through the Vercel project settings.

---

# 🛠️ Getting Started

## Prerequisites

Make sure you have:

* Node.js
* npm
* Git
* A configured database
* Clerk account
* Arcjet account
* Gemini API access
* Stream credentials if using Stream functionality

---

## 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd ai-interview-market-platform
```

## 2. Install dependencies

```bash
npm install
```

## 3. Configure environment variables

Create:

```text
.env.local
```

and add the required credentials.

## 4. Generate Prisma Client

```bash
npx prisma generate
```

## 5. Run database migrations

```bash
npx prisma migrate dev
```

## 6. Start the development server

```bash
npm run dev
```

Open:

```text
http://localhost:3000
```

---

# 🚀 Deployment

The application is deployed using Vercel.

Deployment flow:

```text
Git Push
   ↓
GitHub
   ↓
Vercel
   ↓
Next.js Build
   ↓
Production Deployment
```

Environment variables are configured separately in Vercel rather than being committed to the repository.

---

# 📈 Future Improvements

The architecture is designed to support additional functionality such as:

* 📊 Detailed candidate performance analytics
* 🎯 Personalized interview difficulty
* 📄 Resume-based interview generation
* 🧠 More advanced AI evaluation
* 📈 Interview history and progress tracking
* 🎥 Enhanced real-time interview experiences
* 🔔 Notifications
* 💳 Expanded subscription functionality
* 👥 Interviewer-candidate matching
* 🏆 Personalized preparation roadmaps

---

# 🎓 What This Project Demonstrates

This project was built to demonstrate practical full-stack engineering rather than only frontend implementation.

### Frontend

* Next.js App Router
* React
* Component-driven architecture
* Responsive UI
* Tailwind CSS
* Reusable UI components
* Client-side state management

### Backend

* Next.js Server Actions
* Authentication-aware server logic
* Input validation
* Database operations
* Prisma ORM

### AI Engineering

* Gemini API integration
* AI-powered question generation
* AI-assisted interview workflows
* Separation of AI logic from UI

### Security

* Clerk authentication
* Role-based authorization
* Arcjet security
* Bot protection
* Protected routes
* Secure environment variables

### DevOps

* Git/GitHub workflow
* Environment-based configuration
* Vercel deployment
* Production debugging
* Cloud deployment

---

# 👩‍💻 Built By

**Ayushi Satpathy**

B.Tech Computer Science graduate focused on building full-stack applications and exploring AI-powered developer products.

Interested in:

* Full-Stack Development
* Software Engineering
* AI Engineering
* Backend Development
* Cloud & Deployment
* Developer Tools

---

## ⭐ Why This Project Matters

Prept is more than a UI project.

It combines:

**AI + Full-Stack Development + Authentication + Database Engineering + Security + Cloud Deployment + Product Design**

into a single production-style application.

The goal was to build something that demonstrates how modern web applications are actually put together — from user authentication and database operations to AI integration, security, deployment, and real-world user flows.

---

## 📬 Feedback & Collaboration

If you're a recruiter, engineer, or developer interested in the project, feel free to explore the codebase and the live application.

Feedback, ideas, and collaboration are always welcome.

---

**⭐ If you find the project interesting, consider giving the repository a star.**

