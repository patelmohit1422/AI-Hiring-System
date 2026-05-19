# AI Smart Interview & Hiring System

An AI-powered hiring platform built as a semester project. It helps recruiters post jobs, screen candidates using AI, conduct automated interviews, and make data-driven hiring decisions.

---

## Problem Statement

Hiring is slow and biased. Recruiters spend hours reading resumes and conducting interviews manually. There's no standard way to compare candidates fairly. This project tries to solve that by using AI to automate resume screening, generate interview questions, and score candidates based on their skills and responses.

---

## Features

- AI-generated interview questions based on job description and resume
- Resume scoring — matches candidate skills against job requirements
- Role-based dashboards for Admin, Recruiter, and Candidate
- Side-by-side candidate comparison for recruiters
- Configurable scoring weights (resume vs interview)
- Dark mode and light mode support
- Fully responsive — works on mobile, tablet, and desktop
- Secure authentication with Supabase Auth

---

## User Roles

### Admin
- Manage all users in the system
- Configure scoring rules and weights
- View platform-wide analytics
- Add new users manually

### Recruiter
- Post and manage job listings
- Review candidate applications
- Compare shortlisted candidates side by side
- Make hiring decisions (accept / reject)

### Candidate
- Browse and apply to open jobs
- Take AI-powered interviews
- View scores and feedback
- Track application progress

---

## Tech Stack

| Layer       | Technology                        |
|-------------|-----------------------------------|
| Frontend    | React 18, TypeScript, Vite        |
| Styling     | Tailwind CSS, shadcn/ui           |
| Backend     | Supabase (Auth, Database, Edge Functions) |
| AI          | OpenAI API (via Edge Functions)    |
| Animations  | Framer Motion                     |
| Charts      | Recharts                          |
| Routing     | React Router v6                   |

---

## Database Tables

| Table             | Purpose                                      |
|-------------------|----------------------------------------------|
| `profiles`        | Stores user profile info (name, email, etc.) |
| `user_roles`      | Maps users to roles (admin, recruiter, candidate) |
| `jobs`            | Job listings posted by recruiters            |
| `applications`    | Tracks which candidate applied to which job  |
| `interviews`      | Stores interview questions and candidate answers |
| `scores`          | Resume score, interview score, total score   |
| `system_settings` | Platform-level config like scoring weights   |

---

## Screenshots


### Landing Page
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/0ec17d03-6778-4d02-bf34-083932feb00e" />
<img width="2000" height="1018" alt="image" src="https://github.com/user-attachments/assets/123e37b6-c206-4571-a070-e4eb67a60c1a" />
<img width="2000" height="1018" alt="image" src="https://github.com/user-attachments/assets/18d9ea1d-e0b7-4bbc-b2c8-c5a80cefdf18" />


### Auth Page (Login / Signup)
<img width="2000" height="1031" alt="image" src="https://github.com/user-attachments/assets/d87feed3-759b-4082-a1af-b83540c9ba23" />


### Admin Dashboard
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/a372dc28-787f-41d2-a059-c1ff9755392c" />


### Recruiter Dashboard
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/8bb13885-9520-4a0b-b46a-592e583716ff" />


### Candidate Dashboard
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/b3608f2d-baa8-42db-b111-fb858e205b08" />


### Interview Page
<img width="2000" height="1021" alt="image" src="https://github.com/user-attachments/assets/bd39bf64-a498-46a8-8b42-df08b622a0eb" />
<img width="1280" height="652" alt="image" src="https://github.com/user-attachments/assets/bf3c26e9-029e-46b5-b9ee-2025589c9035" />


### Results Page
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/ee100f35-744c-4d1b-8d02-1579ad3a20f7" />


## Application Progress
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/e7464ff2-b98c-43b9-805a-904476eb093f" />


---

## Installation & Setup

### Prerequisites
- Node.js (v18 or above)
- npm or bun
- A Supabase project (free tier works)

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/ai-smart-interview-system.git
   cd ai-smart-interview-system
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Create a `.env` file** in the root directory and add your Supabase credentials:
   ```
   VITE_SUPABASE_URL=https://your-project.supabase.co
   VITE_SUPABASE_ANON_KEY=your-anon-key-here
   ```

4. **Set up the database**
   - Go to your Supabase dashboard
   - Run the SQL migrations from the `supabase/migrations/` folder
   - This will create all the required tables and policies

5. **Deploy edge functions** (optional, for AI features)
   ```bash
   supabase functions deploy generate-questions
   supabase functions deploy calculate-scores
   supabase functions deploy admin-add-user
   ```

---

## How to Run

```bash
# start the dev server
npm run dev
```

The app will open at `http://localhost:5173`

To build for production:
```bash
npm run build
```

---

## Folder Structure

```
├── public/                  # static assets
├── src/
│   ├── components/          # reusable UI components
│   │   └── ui/              # shadcn/ui base components
│   ├── hooks/               # custom React hooks (auth, toast, etc.)
│   ├── integrations/        # Supabase client setup and types
│   ├── lib/                 # utility functions
│   ├── pages/
│   │   ├── admin/           # admin panel pages
│   │   ├── recruiter/       # recruiter panel pages
│   │   └── candidate/       # candidate panel pages
│   ├── App.tsx              # main app with routing
│   ├── main.tsx             # entry point
│   └── index.css            # global styles and design tokens
├── supabase/
│   ├── functions/           # edge functions (AI scoring, auth, etc.)
│   └── migrations/          # database schema migrations
├── index.html
├── tailwind.config.ts
├── vite.config.ts
└── README.md
```

---

## Future Improvements

- Video-based interviews with webcam recording
- Better AI scoring with more detailed feedback
- Email notifications for application status updates
- Improved resume parsing (extract skills automatically from PDF)
- Analytics dashboard with more charts and filters
- Multi-language support
- Export candidate reports as PDF
- Integration with calendar for scheduling interviews

---

## Author

- **Name:** Jyani Mohit
- **University:** Ganpat University 
- **Program:** BCA
- **Semester:** 6
- **GitHub:** https://github.com/patelmohit1422
- **Email:** jayanimohit@gmail.com

---

> This project was built as part of a semester project. It is meant for learning purposes and demonstrates how AI can be used in the hiring process.
