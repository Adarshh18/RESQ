<div align="center">

```
██████╗ ███████╗███████╗ ██████╗
██╔══██╗██╔════╝██╔════╝██╔═══██╗
██████╔╝█████╗  ███████╗██║   ██║
██╔══██╗██╔══╝  ╚════██║██║▄▄ ██║
██║  ██║███████╗███████║╚██████╔╝
╚═╝  ╚═╝╚══════╝╚══════╝ ╚══▀▀═╝
```

### **R**espond · **E**vacuate · **S**upport · **Q**uickly

*A real-time disaster response and evacuation platform for civilians and volunteers across India*

---

![Static Frontend](https://img.shields.io/badge/Type-Static%20Frontend-e8291c?style=flat-square)
![Leaflet.js](https://img.shields.io/badge/Maps-Leaflet.js-ff6b2b?style=flat-square)
![Geolocation API](https://img.shields.io/badge/API-Geolocation-f5a623?style=flat-square)
![Chatbot](https://img.shields.io/badge/QChat-REST%20API-00d4ff?style=flat-square)
![Responsive](https://img.shields.io/badge/Design-Responsive-00d278?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![No Install](https://img.shields.io/badge/Setup-Zero%20Dependencies-blueviolet?style=flat-square)

</div>

---

## Overview

During disasters, civilians face a critical gap — no reliable way to signal for help, locate safe zones, or connect with rescue volunteers. **RESQ** bridges that gap.

It is a **zero-install, open-in-browser** platform that works on any device, combining:

- GPS-based SOS alerting
- An interactive evacuation map pre-loaded with hospitals and shelters across all Indian state capitals
- An AI-powered disaster chatbot
- A volunteer coordination dashboard

> "Reduce chaos, misinformation, and isolation during disasters — with speed, clarity, and trust."

---

## At a Glance

| Metric | Value |
|--------|-------|
| State Capitals Mapped | 36+ |
| Core Modules | 5 |
| Dependencies to Install | 0 |
| Build Step Required | None |
| Target Region | India |

---

## Key Features

### 🆘 One-Click SOS Dispatch
Captures GPS coordinates via the browser Geolocation API and pins the user on the map instantly. On activation, reveals **WhatsApp**, **email**, and **emergency call** action buttons.

### 🗺️ Interactive Quell Zone Map
Leaflet.js map pre-loaded with **2–5 safe zone markers per state capital** across all 36 Indian capitals — hospitals, community shelters, and relief centers — all visible on page load.

### 🔀 Turn-by-Turn Routing
Leaflet Routing Machine draws highlighted yellow routes from the user's current GPS position to any searched location or clicked Quell Zone marker.

### 💬 QChat Disaster Chatbot
Sends user queries to a deployed REST backend and renders responses live. Supports platform navigation actions — users can be redirected to the SOS page or homepage directly from chat responses.

### 📡 Live Location Tracking
Polls the Geolocation API every **5 seconds** to continuously update the user's marker and map view during an active emergency session.

### 🙋 Volunteer Dashboard
Post-login dashboard with task tracker, event calendar, leaderboard, achievement badges, and a **Chart.js doughnut** breakdown of service hours by activity category.

### 🏥 Health Profile on Registration
Two-step signup: standard credentials followed by an optional health form capturing **allergies**, **chronic conditions**, and **medications** — relevant for triage during rescue operations.

### 💸 Donation Portal
Direct **UPI** and **PayPal** donation links on the Services page to fund emergency supplies and relief operations.

### 📞 Emergency Contact Modal
Homepage modal displaying all India emergency numbers at a glance.

| Service | Number |
|---------|--------|
| National Emergency | 112 |
| Police | 100 |
| Fire Services | 101 |
| Ambulance | 108 |
| NDRF Hotline | +91-9711077372 |

---

## System Workflow

```
┌─────────────┐     ┌──────────────────┐     ┌──────────────────────┐
│   Homepage  │────▶│   SOS Hub        │────▶│  GPS Capture         │
│  index.html │     │   sos.html       │     │  Geolocation API     │
└─────────────┘     └──────────────────┘     └──────────┬───────────┘
                                                         │
                    ┌──────────────────┐     ┌──────────▼───────────┐
                    │  Share Location  │◀────│  Map Pin + Routing   │
                    │  WhatsApp/Email  │     │  Leaflet.js + OSRM   │
                    └──────────────────┘     └──────────────────────┘

┌─────────────┐     ┌──────────────────┐     ┌──────────────────────┐
│   QChat     │────▶│  REST Backend    │────▶│  JSON Response       │
│ Qchat.html  │     │  Render Hosted   │     │  { "response": "" }  │
└─────────────┘     └──────────────────┘     └──────────────────────┘

┌─────────────┐     ┌──────────────────┐     ┌──────────────────────┐
│  Services   │────▶│  Volunteer Reg.  │────▶│  Dashboard           │
│ service.html│     │  Health Profile  │     │  volunteer.html      │
└─────────────┘     └──────────────────┘     └──────────────────────┘
```

**Step-by-step flow:**

1. **Homepage** — User views disaster alert cards and accesses the emergency contact modal (112, NDRF, etc.)
2. **SOS Trigger** — Pressing SOS plays a siren, captures GPS, drops a map pin, and reveals sharing options
3. **Quell Zones** — All 36 state capital safe zones pre-load on the map; clicking any opens a directions popup
4. **Search & Route** — Nominatim geocodes any location; Leaflet Routing Machine draws the route
5. **QChat** — User message → GET request to Render API → response rendered in chat window
6. **Volunteer Flow** — Register → complete health profile → log in → access full dashboard

---

## Tech Stack

### Frontend
| Technology | Purpose |
|------------|---------|
| HTML5 / CSS3 | Structure and styling |
| Vanilla JavaScript (ES6+) | All interactivity and logic |
| Google Fonts — Poppins | Typography |
| Font Awesome 6 | Icons throughout the platform |
| Boxicons 2.1.4 | Icons on login/register page |

### Mapping & Routing
| Technology | Purpose |
|------------|---------|
| Leaflet.js | Interactive map rendering |
| Leaflet Routing Machine | Turn-by-turn route display |
| OpenStreetMap Tiles | Base map layer |
| Nominatim API | Location geocoding and search |

### Data & Visualization
| Technology | Purpose |
|------------|---------|
| Chart.js | Doughnut chart on volunteer dashboard |

### APIs & Integrations
| Integration | Purpose |
|-------------|---------|
| Browser Geolocation API | GPS coordinate capture |
| WhatsApp URL Scheme (`wa.me`) | Emergency location sharing |
| `mailto:` URI | Email-based SOS sharing |
| UPI Deep Link | Donation gateway |
| PayPal Donate URL | International donations |

### Backend
| Component | Detail |
|-----------|--------|
| REST API | Deployed on Render |
| Endpoint | `GET /get?msg=<query>` |
| Response | `{ "response": "string" }` |

---

## Project Structure

```
RESQ-main/
├── index.html          # Homepage — alert cards, emergency contact modal
├── sos.html            # SOS Hub — map, Quell Zones, routing, live tracking
├── Qchat.html          # QChat — chatbot UI + REST API integration
├── service.html        # Services — mission, donations, volunteer registration
├── volunteer.html      # Volunteer dashboard — tasks, events, Chart.js, badges
├── ppj.html            # Login / Register + health profile step
├── exp.html            # About / Explore page
│
├── css/
│   ├── index.css       # Homepage styles
│   ├── ppj.css         # Login/register styles
│   └── volunteer.css   # Dashboard styles
│
├── js/
│   ├── index.js        # Homepage interactions
│   └── ppj.js          # Login/register toggle logic
│
└── images/
    ├── RESQ.jpg        # Platform logo
    ├── chatbotbg.jpg   # QChat background
    ├── explore.jpg     # Explore page background
    └── icon.jpg        # Volunteer dashboard user avatar
```

> **Notable:** `sos.html` is the most complex module at ~695 lines, containing all Quell Zone data for every Indian state capital, SOS trigger logic, routing, live tracking, and location sharing.

---

## Installation & Setup

### Prerequisites
- Any modern browser (Chrome, Firefox, Edge, Safari)
- A local HTTP server — choose any option below
- Git

### Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/RESQ.git
cd RESQ

# 2a. Serve with Python 3
python -m http.server 8080

# 2b. OR serve with Node.js
npm install -g http-server
http-server -p 8080

# 3. Open in browser
open http://localhost:8080
```

> **VS Code users:** Right-click `index.html` → *Open with Live Server*

### Configuration Notes

**Chatbot Backend**
The QChat module connects to a pre-deployed API. To use your own backend, update the fetch URL in `Qchat.html`:
```javascript
// Replace this:
const response = await fetch(`https://resq-ziw9.onrender.com/get?msg=${encodeURIComponent(message)}`);

// With your own endpoint:
const response = await fetch(`https://your-backend-url/get?msg=${encodeURIComponent(message)}`);
```
Expected response shape: `{ "response": "<string>" }`

**Geolocation**
Requires HTTPS in production. Works over HTTP locally with a browser permission prompt.

**Donation Links**
Replace placeholder credentials in `service.html` before deploying:
- UPI: `donate@upi` → your UPI ID
- PayPal: `your-paypal-email` → your PayPal email

**Routing**
Uses the default OSRM demo server. For production, configure a self-hosted OSRM instance to avoid rate limits.

---

## Usage

### For Civilians

1. Open the app and navigate to the **SOS** page
2. Allow location access when prompted
3. Click **Send SOS** to capture your position and reveal sharing options
4. Use **Share via WhatsApp** or **Share via Email** to send your GPS link to a contact
5. Browse **Quell Zone markers** on the map → click → **Get Directions** for a route to safety
6. Use the **Search bar** to route to any location by name

### For Volunteers

1. Go to **Services** → click **Become a Volunteer**
2. Complete the registration form with personal and health details
3. On return visits, click **Already a Volunteer?** → log in → access the dashboard
4. Dashboard provides task status, event RSVPs, leaderboard rankings, and downloadable reports

### For New Users

1. Click **Sign In** in the navigation bar
2. Select **Register** → fill in credentials → submit
3. Complete the optional health information form (allergies, chronic conditions, medications)

---

## Screenshots / Demo

> Add screenshots by placing images in the `images/` folder and updating the paths below.

| Module | Preview |
|--------|---------|
| Homepage | `![Homepage](images/screenshot-home.png)` |
| SOS Hub | `![SOS Hub](images/screenshot-sos.png)` |
| QChat | `![QChat](images/screenshot-chat.png)` |
| Services | `![Services](images/screenshot-services.png)` |
| Volunteer Dashboard | `![Dashboard](images/screenshot-dashboard.png)` |

---

## Future Enhancements

| # | Feature | Description |
|---|---------|-------------|
| 01 | **Persistent Backend & Database** | Replace client-only forms with Firebase or PostgreSQL to persist accounts, health profiles, and volunteer records |
| 02 | **Live Weather Integration** | Connect the SOS Hub weather panel to OpenWeatherMap API using captured GPS coordinates |
| 03 | **Admin Operations Dashboard** | Coordinator panel for NDRF/SDMA operators to monitor active SOS pins and assign volunteers in real time |
| 04 | **Web Push Notifications** | Deliver real-time disaster alerts via the Web Push API based on the user's stored region |
| 05 | **Offline Support via Service Workers** | Cache critical pages (SOS, emergency contacts) for access when network connectivity fails during disasters |
| 06 | **Role-Based Access Control** | Differentiate civilian, volunteer, and admin roles with protected routes and permission-based features |
| 07 | **Multilingual Interface** | Localization for Hindi, Tamil, Telugu, and Bengali to improve accessibility during emergencies |
| 08 | **Verified Donation Tracking** | Integrate Razorpay or Stripe with a transparent fund allocation dashboard visible to donors |

---

## License

```
MIT License

Copyright (c) 2025 RESQ

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES, OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

---

<div align="center">

**RESQ** · Respond · Evacuate · Support · Quickly

*© 2025 RESQ — All Rights Reserved*

</div>
