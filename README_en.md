<div align="center">

# ⚡ Smart Scrum Board

**Free real-time Scrum board — for teams and solo users**

[![React](https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=white)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![Vite](https://img.shields.io/badge/Vite-7-646CFF?logo=vite&logoColor=white)](https://vitejs.dev)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-3ECF8E?logo=supabase&logoColor=white)](https://supabase.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

> Manage tasks, track deadlines, and collaborate with your team in real time — free, with no limits.

**[🚀 Try It Online](https://scrum-board-demo--s6sarik.replit.app/demo/)** · **[📖 Documentation](#table-of-contents)** · **[🐛 Report a Bug](../../issues/new)**

</div>

---

## Table of Contents

1. [What the App Can Do](#what-the-app-can-do)
2. [Quick Start in 5 Minutes](#quick-start-in-5-minutes)
3. [Step-by-Step Installation](#step-by-step-installation)
4. [How to Use It](#how-to-use-it)
5. [Invite Friends to Your Board](#invite-friends-to-your-board)
6. [Deploy Your Own Version](#deploy-your-own-version)
7. [Project Structure](#project-structure)
8. [For Developers](#for-developers)
9. [Security](#security)
10. [License](#license)

---

## What the App Can Do

| Feature | Description |
|---|---|
| 🗂 **Task Board** | Kanban board with 4 columns and drag-and-drop |
| 📋 **Backlog** | List of tasks outside the sprint, with priority ranking |
| 📊 **Analytics** | Burndown chart, sprint velocity, category breakdown charts |
| 💬 **Discussions** | Real-time comments on every task |
| 🔔 **Deadline Alerts** | Browser notifications + sound, 24 hours before the due date |
| 👥 **Partners** | Colleague contacts with personal nicknames |
| 📚 **Learning** | Scrum knowledge base: roles, terms, practices |
| 🌍 **Languages** | Russian, English, Uzbek |
| 🌙 **Themes** | Light and dark theme |

---

## Quick Start in 5 Minutes

Want to just **try it out** without installing anything:

**[➡ Open the Online Version](https://scrum-board-demo--s6sarik.replit.app/demo/)** — a demo version, no registration required.

---

## Step-by-Step Installation

### What You'll Need

- A computer running Windows, macOS, or Linux
- [Node.js](https://nodejs.org/en/download) — download the LTS version (18 or higher)
- A [Supabase](https://supabase.com) account — free, no card required

> 💡 **Check your Node.js version:** open a terminal and run `node --version`. It should show `v18.x.x` or higher.

---

### Step 1 — Download the Project

**Option A — via git:**
```bash
git clone https://github.com/SardorTheBest/smart-scrum-board.git
cd smart-scrum-board
```

**Option B — ZIP archive:**
1. Click the green **Code** button → **Download ZIP**
2. Extract the archive
3. Open the folder in a terminal

---

### Step 2 — Create a Database (Supabase)

#### 2.1 Sign Up for Supabase

1. Go to [supabase.com](https://supabase.com) and click **Start your project**
2. Sign in with GitHub or create an account
3. Click **New project**
4. Fill in:
   - **Name** — any name, e.g. `scrum-board`
   - **Database Password** — pick a strong password and save it somewhere safe
   - **Region** — choose the region closest to you
5. Click **Create new project** and wait about a minute

#### 2.2 Get Your API Keys

1. In the left sidebar, click ⚙️ **Project Settings**
2. Open the **Data API** tab
3. Copy two values:

```
Project URL:    https://xxxxxxxxxxxxxxxxxx.supabase.co
                           ↑ this is your VITE_SUPABASE_URL

anon / public:  eyJhbGciOiJIUzI1NiIsInR5c...
                           ↑ this is your VITE_SUPABASE_ANON_KEY
```

> ⚠️ Only use the `anon` key. The `service_role` key is for server-side code only.

#### 2.3 Create the Database Tables

1. In the left sidebar, click **SQL Editor**
2. Click **New query**
3. Open the `supabase/schema.sql` file from the downloaded project, copy its full contents, paste it into the editor, and click **Run**
4. Repeat for `supabase/add-comments.sql`
5. Repeat for `supabase/add-partners.sql`

After each file, you should see the message `Success. No rows returned`.

#### 2.4 Disable Email Confirmation

1. In the left sidebar, click **Authentication**
2. Go to **Email**
3. Find the **Confirm email** toggle and **turn it off**

> This matters! Without it, users won't be able to log in right after signing up.

---

### Step 3 — Set Up Environment Variables

1. In the project folder, find the `.env.example` file
2. Make a copy of it named `.env`:

```bash
# macOS / Linux
cp .env.example .env

# Windows (Command Prompt)
copy .env.example .env
```

3. Open `.env` in any editor (Notepad, VS Code) and paste in your keys:

```env
VITE_SUPABASE_URL=https://xxxxxxxxxxxxxxxxxx.supabase.co
VITE_SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5c...
```

> 🔒 The `.env` file stays on your machine only — it's never uploaded to GitHub.

---

### Step 4 — Install Dependencies and Run

```bash
# Install the packages (one-time, takes ~1-2 minutes)
npm install

# Start the app
npm run dev
```

Open your browser and go to **http://localhost:5173**

🎉 Your app is up and running!

---

## How to Use It

### Sign Up and Log In

1. On the landing page, click **Sign Up**
2. Enter your email and a password (at least 6 characters)
3. Click **Sign Up** — you'll be taken straight into the app

### Creating Your First Board

1. In the left sidebar, click **+ New Board**
2. Enter a board name and sprint details (start date, end date, sprint name)
3. Click **Create**

### Adding a Task

1. Click the **+** button in any column on the board
2. Fill in:
   - **Title** — a short, clear description of what needs to be done
   - **Description** — additional details (optional)
   - **Category** — Feature, Bug, Design, etc.
   - **Priority** — Low, Medium, High, Critical
   - **Story Points** — a complexity estimate (1, 2, 3, 5, 8, 13)
   - **Deadline** — the due date
   - **Assignee** — who's responsible for the task
3. Click **Create Task**

### Moving Tasks

Just **drag a card** from one column to another with your mouse:
- 📥 **Sprint Backlog** — task is planned
- 🔄 **In Progress** — task is being worked on
- 👀 **Review** — awaiting review
- ✅ **Done** — completed

### Discussing a Task

1. **Click a task card** — a side panel will open
2. On the right, you'll see a comment thread
3. Type your message and press **Enter** or **Ctrl+Enter**
4. All board members see comments **in real time**

### Deadline Notifications

1. Click the 🔔 **bell icon** in the left sidebar
2. Click **Allow notifications** — your browser will ask you to confirm
3. Now you'll get a push notification plus a sound alert 24 hours before the deadline
4. You can toggle the sound on/off next to the bell icon

### Backlog

Go to the **Backlog** section (left sidebar):
- Click **+** to add a task to the backlog
- Use the ↑↓ arrows to reorder task priority
- Click **Move to Sprint** to pull a task into the current sprint

### Analytics

In the **Analytics** section, you'll find:
- **Burndown chart** — how story points burn down over the sprint
- **By column** — how many story points sit in each column
- **By category** — task distribution
- **Velocity** — sprint completion percentage

---

## Invite Friends to Your Board

### Method 1 — Via the Invite Button (In-App)

1. Open the board you want
2. Click the **Invite** button (the person-with-a-plus icon) at the top of the board
3. Enter your friend's or colleague's **email**
4. Click **Send Invitation**
5. Your friend will get a notification and be able to join your board

> Your friend needs to sign up on your version of the app first.

### Method 2 — Via Partners (Contact List)

1. In the left sidebar, click **Partners** (the people icon)
2. Click **Add Partner**
3. Enter the person's email
4. You can add a nickname — whatever you call them (e.g. "Alex the designer")
5. Now this person will show up in your list when assigning task owners

### What the Invited Person Sees

Once they accept the invitation, your colleague sees:
- The same board with the same tasks
- Comments updating for everyone in real time
- They can drag tasks around and add their own

---

## Deploy Your Own Version

### What "Deploying" Means

Running `npm run build` creates a `dist/` folder — a finished website made of HTML, CSS, and JavaScript files. That's the folder you upload to a hosting provider, and it becomes your live website.

```
npm run build  →  dist/ folder  →  upload to Vercel/Netlify  →  your site is live
```

### Vercel — Recommended (Free)

1. Push the project to GitHub (if you haven't already)
2. Sign up at [vercel.com](https://vercel.com)
3. Click **Add New Project** → select your repository
4. Vercel will detect Vite automatically
5. Go to **Environment Variables** and add:
   ```
   VITE_SUPABASE_URL        = https://your-project.supabase.co
   VITE_SUPABASE_ANON_KEY   = eyJhbGci...
   ```
6. Click **Deploy** — within a minute your site will be live at `your-project.vercel.app`

Every time you `git push` to main, Vercel will automatically redeploy the site.

### Netlify (Alternative)

```bash
npm run build
npx netlify deploy --prod --dir dist
```

---

## Project Structure

```
smart-scrum-board/
├── public/                  # Icons and static files
├── src/
│   ├── components/
│   │   ├── board/           # Board: cards, columns, drawer
│   │   ├── layout/          # Navigation, sidebar
│   │   └── ui/               # Base UI components (buttons, forms)
│   ├── contexts/            # Global state (Auth, App)
│   ├── lib/                 # Supabase client, notifications
│   ├── pages/                # Pages: board, backlog, analytics
│   ├── types/                # TypeScript types
│   └── i18n/                 # Translations (RU/EN/UZ)
├── supabase/
│   ├── schema.sql           # Core tables — run this first
│   ├── add-comments.sql     # Comments — run this second
│   └── add-partners.sql     # Partners — run this third
├── .env.example              # Variable template — copy to .env
├── .gitignore                # What NOT to upload to GitHub
├── vite.config.ts            # Vite configuration
├── tsconfig.json             # TypeScript configuration
├── vercel.json                # Vercel settings
├── netlify.toml               # Netlify settings
└── LICENSE                    # MIT license
```

---

## For Developers

### Commands

```bash
npm run dev        # Dev server with hot reload → localhost:5173
npm run build      # Production build → dist/ folder
npm run preview    # Preview the production build locally
npm run typecheck  # Type-check TypeScript without building
```

### Tech Stack

```
React 19 + TypeScript 5.9  — UI and typing
Vite 7                     — bundler (very fast)
Tailwind CSS v4            — styling
shadcn/ui                  — pre-built UI components
@hello-pangea/dnd          — drag-and-drop
Recharts                   — charts
wouter                     — routing
Supabase                   — DB + Auth + Realtime
```

### Want to Contribute?

1. Fork the repository
2. Create a branch: `git checkout -b feature/your-feature-name`
3. Make your changes and commit them
4. Open a Pull Request describing your changes

All PRs are welcome — bug fixes, new features, documentation improvements.

---

## Security

- 🔒 The `.env` file is listed in `.gitignore` — your keys will never end up in the repository
- 🛡 **Row Level Security (RLS)** is enabled on all tables — each user only sees their own data
- 🔑 The `anon` key is safe to expose in the browser — it's a public key, and protection is enforced via RLS
- ❌ The `service_role` key is never used on the client
- 🔐 User passwords are stored by Supabase Auth (bcrypt hashing)

**If you accidentally commit a key:**
Supabase → Settings → API → click **Regenerate** next to the anon key. The old key is invalidated immediately.

---

## License

This project is released under the [MIT](./LICENSE) license.

You're free to use, copy, modify, and distribute this project — including for commercial purposes — as long as you keep the copyright notice.

---

<div align="center">

If you found this project useful, give it a ⭐ on GitHub!
