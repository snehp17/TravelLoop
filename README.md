# 🌍 TravelLoop

> **Smart travel planning, built for explorers.**  
> Plan trips, manage itineraries, track expenses, and collaborate with friends — all in one place.

---

## ✨ Features

- 🗺️ **Trip Planner** — Create and manage multi-stop trips with full itinerary builder
- 💰 **Budget Tracker** — Track expenses per trip with analytics and category breakdowns
- 🤝 **Collaboration** — Invite friends to trips, share notes, and plan together in real-time
- 🔍 **City Search** — Explore cities, attractions, and activities powered by a curated database
- 📝 **Trip Notes** — Collaborative note-taking per trip and per stop
- 🎒 **Packing Checklist** — Smart packing lists shared across trip members
- 🤖 **AI Optimizer** — AI-powered trip optimization suggestions
- 📊 **Budget Analytics** — Visual charts and spending breakdowns

---

## 🛠️ Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| React 18 + Vite | UI framework & build tool |
| React Router v6 | Client-side routing |
| Tailwind CSS | Utility-first styling |
| Framer Motion | Animations & transitions |
| Recharts | Budget analytics charts |
| Lucide React | Icon library |
| @hello-pangea/dnd | Drag-and-drop itinerary |

### Backend
| Technology | Purpose |
|---|---|
| Node.js + Express | REST API server |
| Prisma ORM | Database access layer |
| PostgreSQL | Relational database |
| JWT | Authentication tokens |
| bcryptjs | Password hashing |
| Multer | File/image uploads |

---

## 📁 Project Structure

```
traveloop/
├── frontend/               # React + Vite frontend
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/          # Page-level components
│   │   ├── layouts/        # Layout wrappers
│   │   ├── routes/         # App routing
│   │   └── styles/         # Global CSS
│   ├── index.html
│   └── vite.config.js
│
├── backend/                # Node.js + Express backend
│   ├── controllers/        # Route logic
│   ├── routes/             # API route definitions
│   ├── middleware/         # Auth & upload middleware
│   ├── prisma/
│   │   ├── schema.prisma   # Database schema
│   │   ├── seed.js         # Seed data (cities, attractions)
│   │   └── migrations/     # DB migration history
│   └── index.js            # Server entry point
│
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- [Node.js](https://nodejs.org/) (v18 or higher)
- [npm](https://www.npmjs.com/) (v9 or higher)
- [PostgreSQL](https://www.postgresql.org/) (v14 or higher)

---

## ⚙️ Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/snehp17/TravelLoop.git
cd TravelLoop
```

---

### 2. Backend Setup

#### Navigate to the backend directory

```bash
cd backend
```

#### Install dependencies

```bash
npm install
```

#### Create environment file

Create a `.env` file in the `backend/` directory:

```env
DATABASE_URL="postgresql://your_username:your_password@localhost:5432/traveloop"
JWT_SECRET="your_super_secret_jwt_key_here"
PORT=3001
```

> **Replace** `your_username`, `your_password` with your PostgreSQL credentials.

#### Run database migrations

```bash
npx prisma migrate dev
```

#### Generate Prisma client

```bash
npx prisma generate
```

#### (Optional) Seed the database with cities & attractions

```bash
npm run prisma -- seed
# or directly:
node prisma/seed.js
```

#### Start the backend server

```bash
# Development (with auto-reload)
npm run dev

# Production
npm start
```

The backend will run at: **http://localhost:3001**

---

### 3. Frontend Setup

Open a **new terminal** and navigate to the frontend directory:

```bash
cd frontend
```

#### Install dependencies

```bash
npm install
```

#### Create environment file

Create a `.env` file in the `frontend/` directory:

```env
VITE_API_URL=http://localhost:3001
```

#### Start the frontend dev server

```bash
npm run dev
```

The frontend will run at: **http://localhost:5173**

---

## 🏃 Running the Full App

You need **two terminals** running simultaneously:

| Terminal | Directory | Command |
|---|---|---|
| Terminal 1 (Backend) | `traveloop/backend/` | `npm run dev` |
| Terminal 2 (Frontend) | `traveloop/frontend/` | `npm run dev` |

Then open your browser and go to 👉 **http://localhost:5173**

---

## 🗄️ Database

TravelLoop uses **PostgreSQL** with **Prisma ORM**.

### Key Models
- `User` — Registered users
- `Trip` — Travel trips (owned by a user)
- `TripMember` — Collaborative trip memberships
- `TripStop` — Individual stops within a trip
- `TripActivity` — Activities planned per stop
- `TripNote` — Notes per trip or stop
- `PackingItem` — Packing checklist items
- `Expense` — Trip expense tracking
- `City` / `Attraction` / `CityActivity` — Curated destination data

### View the database (optional)

```bash
cd backend
npx prisma studio
```

This opens Prisma Studio at **http://localhost:5555** — a visual DB browser.

---

## 📡 API Overview

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/auth/register` | Register a new user |
| POST | `/api/auth/login` | Login and get JWT token |
| GET | `/api/trips` | Get all trips for logged-in user |
| POST | `/api/trips` | Create a new trip |
| GET | `/api/trips/:id` | Get a specific trip |
| PUT | `/api/trips/:id` | Update a trip |
| DELETE | `/api/trips/:id` | Delete a trip |
| GET | `/api/search` | Search cities & destinations |
| GET | `/api/expenses` | Get expenses for a trip |
| POST | `/api/expenses` | Add a new expense |
| GET | `/health` | Server health check |

---

## 🔧 Useful Commands

```bash
# Backend
npm run dev           # Start backend with hot-reload
npx prisma studio     # Open visual database browser
npx prisma migrate dev # Run new migrations
npx prisma generate   # Regenerate Prisma client

# Frontend
npm run dev           # Start frontend dev server
npm run build         # Build for production
npm run preview       # Preview production build
```

---

## 📄 License

This project was built for the **Odoo × Parul University Hackathon 2026**.

---

<div align="center">
  Made with ❤️ by the TravelLoop Team
</div>
