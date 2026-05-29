# 🌊 OceanGuardian — Disaster Management Platform

**Integrated platform for crowdsourced ocean hazard reporting and social media analytics.**

![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-4-646CFF?logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3-38BDF8?logo=tailwindcss&logoColor=white)
![Leaflet](https://img.shields.io/badge/Leaflet-1.9-199900?logo=leaflet&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📑 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Application Routes](#application-routes)
- [Demo](#demo)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [License](#license)

---

## 📖 Overview

**OceanGuardian** is a web-based disaster management platform that enables citizens, volunteers, officials, and analysts to:

- **Report** ocean hazards in real time with geotagged data and media attachments
- **Visualize** coastal risk on an interactive map dashboard
- **Analyze** social media discussions and sentiment around disaster events

The system supports Indian coastal authorities — including [INCOIS](https://incois.gov.in) — in achieving effective situational awareness for hazards such as tsunamis, storm surges, high waves, and abnormal tides.

> 🚨 **Emergency contacts built into the platform:**
> - National emergency helpline: **108**
> - INCOIS Control Room: **040-23895000**

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 📍 **Crowdsourced Hazard Reporting** | Citizens submit geotagged reports with photos or videos; works offline and syncs when back online |
| 🔐 **Role-Based Access Control** | Secure login for citizens, volunteers, officials, and analysts with protected routes |
| 🗺️ **Live Interactive Dashboard** | Map-based dashboard showing incident hotspots, real-time data, and latest hazard reports |
| 📊 **Social Media Sentiment Analysis** | Displays hazard discussions and NLP-based sentiment from social media platforms |
| 🌦️ **Hazard Prediction** | Meteorological data integration for short-term hazard forecasting |
| 📁 **Media Upload & Secure Processing** | Supports image, video, and document uploads with validation and secure storage |
| 📱 **Progressive Web App (PWA)** | App-like experience on desktop and mobile devices |
| 📧 **Automatic Email Notifications** | Email alerts triggered by high-severity hazard events |
| 🤖 **AI / LLM Integration** | Content analytics, false-signal detection, and AI-assisted imagery |
| ⚡ **Real-Time Data Sync** | Instant updates and notifications pushed across all connected users |
| 🏗️ **Scalable Infrastructure** | Auto-scaling, CDN delivery, SSL/HTTPS, deployed on Base44 |

---

## 🛠️ Technology Stack

### Frontend

| Library / Tool | Purpose |
|----------------|---------|
| **React 18** | Main UI framework (JSX) |
| **React Router DOM 6** | Client-side routing and navigation |
| **Tailwind CSS 3** | Utility-first CSS styling |
| **Radix UI / Shadcn/ui** | Accessible, composable component primitives |
| **Lucide React** | SVG icon library |
| **React Leaflet / Leaflet** | Interactive map components |
| **Recharts** | Chart and data visualization |
| **date-fns** | Lightweight date utilities |
| **React Markdown** | Markdown content rendering |

### Backend & Data

| Component | Description |
|-----------|-------------|
| **Entity System** | JSON Schema-based data models (`HazardReport`, `SocialMediaAnalytics`, `User`, `SafeZone`) |
| **Built-in Database** | Real-time CRUD operations with data validation |
| **Authentication** | Email/password login with protected route guards; Google OAuth support |
| **File Storage** | Private file storage with signed URL generation and media handling |
| **User Management** | Role-based profiles and account verification |

### Infrastructure

| Component | Description |
|-----------|-------------|
| **Vite 4** | Fast dev server and production bundler |
| **Automatic Scaling** | Handles traffic spikes on demand |
| **CDN & SSL/HTTPS** | Fast and secure content delivery |
| **PWA Support** | Offline-first caching strategy |

---

## 📁 Project Structure

```
OceanGuardian_disaster_management/
├── disaster_management/          # Legacy / reference implementation
│   ├── Components/
│   │   └── dashboard/
│   ├── Entities/
│   ├── Pages/
│   └── Layout.js
├── src/                          # Active Vite + React application
│   ├── components/
│   │   ├── dashboard/
│   │   │   ├── EmergencyAlerts.jsx
│   │   │   ├── InteractiveMap.jsx
│   │   │   ├── RecentReports.jsx
│   │   │   ├── SentimentAnalysis.jsx
│   │   │   └── StatsOverview.jsx
│   │   ├── ui/                   # Reusable UI primitives (Button, Card, …)
│   │   └── ProtectedRoute.jsx
│   ├── contexts/
│   │   └── AuthContext.jsx       # Authentication state & helpers
│   ├── entities/
│   │   ├── User.js
│   │   └── all.js                # Barrel export for all entities
│   ├── pages/
│   │   ├── Dashboard.jsx         # Main monitoring dashboard
│   │   ├── Login.jsx             # Sign-in page
│   │   ├── ReportHazard.jsx      # Hazard submission form
│   │   ├── Signup.jsx            # New-user registration
│   │   └── UserProfile.jsx       # User profile & settings
│   ├── utils/
│   ├── App.jsx                   # Route definitions
│   ├── Layout.jsx                # Shared app shell / navigation
│   ├── index.css
│   └── main.jsx
├── index.html
├── package.json
├── postcss.config.js
├── tailwind.config.js
└── vite.config.js
```

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) **v18+** (LTS recommended)
- npm **v9+** (bundled with Node.js)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/rjb-meerkat-hx/OceanGuardian_disaster_management.git
cd OceanGuardian_disaster_management

# 2. Install dependencies
npm install

# 3. Start the development server
npm run dev
```


### Build for Production

```bash
npm run build      # Outputs to /dist
npm run preview    # Preview the production build locally
```

### Demo Credentials

Use the following credentials to explore the application without registering:

| Field | Value |
|-------|-------|
| Email | `demo@incois.gov.in` |
| Password | `demo123` |

---

## 🗺️ Application Routes

| Route | Access | Description |
|-------|--------|-------------|
| `/login` | Public | Sign in to an existing account |
| `/signup` | Public | Create a new account |
| `/` | Protected | Main dashboard with live map and statistics |
| `/report` | Protected | Submit a new ocean hazard report |
| `/UserProfile` | Protected | View and edit your user profile |

> Protected routes require authentication. Unauthenticated users are redirected to `/login`.

---

## 🎬 Demo

**▶ Watch the demo video:** [Google Drive](https://drive.google.com/file/d/1fPGm1u4kKRx2aPmb-sdlVXZkX4ow7a52/view?usp=sharing)

---

## 📸 Screenshots

<img width="1871" height="876" alt="Dashboard overview" src="https://github.com/user-attachments/assets/8975ca02-1519-41b7-9a08-fa449f741f21" />

<img width="1875" height="874" alt="Emergency alerts panel" src="https://github.com/user-attachments/assets/b65a890d-a0e8-4a6c-826d-c14bc7296af2" />

<img width="1870" height="879" alt="Interactive hazard map" src="https://github.com/user-attachments/assets/2b30e163-f819-4f26-ae75-6f4c95522454" />

<img width="1855" height="885" alt="Report hazard form" src="https://github.com/user-attachments/assets/2c873d29-026d-4ea1-8405-78c99ff21626" />

<img width="1849" height="873" alt="Sentiment analysis widget" src="https://github.com/user-attachments/assets/dd36f9ee-542a-45f0-a19c-01ad716e3a8c" />

<img width="1852" height="877" alt="Stats overview" src="https://github.com/user-attachments/assets/7df87eab-4f9a-432e-8ab9-9183663f645d" />

<img width="1846" height="879" alt="Recent reports panel" src="https://github.com/user-attachments/assets/3e73b367-a735-47ba-bf92-d3af9ed9b7f4" />

<img width="1872" height="886" alt="User profile page" src="https://github.com/user-attachments/assets/bc455974-51d0-41ef-9ff2-8cb7d28dc561" />

---

## 🤝 Contributing

Contributions are welcome! To get started:

1. **Fork** this repository
2. **Create** a feature branch: `git checkout -b feature/your-feature-name`
3. **Commit** your changes: `git commit -m "feat: add your feature"`
4. **Push** to your fork: `git push origin feature/your-feature-name`
5. **Open** a Pull Request against the `main` branch

Please make sure your code follows the existing code style and that the app builds without errors (`npm run build`) before submitting.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
