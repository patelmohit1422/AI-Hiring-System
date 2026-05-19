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
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/fcecd3ab-9229-4b1d-8a7c-ec17387fb6b5" />
<img width="2000" height="1018" alt="image" src="https://github.com/user-attachments/assets/eab2b9e1-6b24-4ecf-8a80-24dac5b36fbf" />
<img width="2000" height="1018" alt="image" src="https://github.com/user-attachments/assets/8d8d81de-c7d9-4cb8-b809-df74d4d55e9b" />


### Auth Page (Login / Signup)
<img width="2000" height="1031" alt="image" src="https://github.com/user-attachments/assets/e77a0d46-5adf-42fe-9b41-7720ce4a095e" />

### Admin Dashboard
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/c1ca8549-9a29-4220-918d-2ac314343851" />

### Recruiter Dashboard
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/a4f8bc79-67dc-4dcf-9c08-d6ecaf130648" />

### Candidate Dashboard
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/e12ed6cd-7185-40f1-a1b2-fb3088de3872" />

### Interview Page
<img width="2000" height="1021" alt="image" src="https://github.com/user-attachments/assets/e281a4e6-bc99-4d96-bbc6-bb3953faf7dd" />
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/a7dafe22-3aab-4821-966e-0e2ba04ac2ae" />

### Results Page
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/1665cce9-e96c-45d9-a3bc-5ad2ac9e4ee5" />


## Application Progress
<img width="2000" height="1019" alt="image" src="https://github.com/user-attachments/assets/0f29fc76-b58c-45d7-90b5-45d2db20cf48" />


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
