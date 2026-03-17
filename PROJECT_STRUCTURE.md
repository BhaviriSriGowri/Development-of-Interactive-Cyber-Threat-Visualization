# Project Structure

This document provides an overview of the file structure for the **Cyber Threat Intelligence Monitoring System**.

## 📂 Root Directory
```
threat-monitor-dist/
├── backend/                  # Node.js/Express Backend
├── frontend/                 # React/Vite Frontend
├── start-app.bat             # Windows startup script
├── RUNNING_THE_PROJECT.md    # Guide for local setup
├── DEPLOYMENT.md             # Guide for cloud deployment
└── PROJECT_STRUCTURE.md      # This file
```

---

## 🔙 Backend (`/backend`)
Handles data collection, processing, and the REST API.

```
backend/
├── jobs/
│   └── scheduler.js          # Background job for periodic data fetching
├── models/
│   ├── IOC.js                # Database model for Indicators of Compromise
│   └── Threat.js             # Database model for Threat Intelligence data
├── routes/
│   └── api.js                # Definition of REST API endpoints
├── services/
│   ├── abuseIpdbService.js   # Wrapper for AbuseIPDB API
│   ├── ipinfoService.js      # Wrapper for IPinfo API
│   ├── otxService.js         # Wrapper for AlienVault OTX API
│   └── dataProcessor.js      # Core logic for normalizing and aggregated data
├── server.js                 # Entry point, Express app setup, database sync
├── database.sqlite           # SQLite database file (created on runtime)
├── .env                      # Environment variables (API keys)
└── package.json              # Backend dependencies
```

---

## 🖥️ Frontend (`/frontend`)
The user interface built with React, Vite, and TailwindCSS.

```
frontend/
├── src/
│   ├── components/           # Reusable UI components
│   │   └── MetricCard.jsx    # Card component for stats (Total IPs, etc.)
│   ├── pages/                # Main application views
│   │   ├── Overview.jsx      # Dashboard homepage with charts
│   │   ├── ThreatTrends.jsx  # Visualization of threats over time
│   │   ├── ThreatMapHelper.jsx # Geographic map visualization
│   │   ├── IOCs.jsx          # Database view of Indicators of Compromise
│   │   └── IpChecker.jsx     # Tool to manually check IP reputation
│   ├── App.jsx               # Main component with Routing setup
│   ├── api.js                # Axios instance configuration
│   ├── index.css             # Global styles and Tailwind directives
│   └── main.jsx              # React DOM entry point
├── public/                   # Static assets
├── index.html                # HTML entry point
├── tailwind.config.js        # Tailwind CSS configuration (Theme, Colors)
├── vite.config.js            # Vite configuration
└── package.json              # Frontend dependencies
```
