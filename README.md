# RESQ — Real-Time Disaster Response and Evacuation Platform

## Project Overview

RESQ is a browser-based disaster management and emergency response platform designed to assist civilians and volunteers during natural disasters and crisis events. The system addresses a critical real-world problem: during emergencies such as floods, earthquakes, and fires, affected individuals often lack immediate access to reliable information, evacuation routes, emergency contacts, and coordinated volunteer support.

RESQ solves this by consolidating four core capabilities into a single, accessible web interface:

1. A one-click SOS alert system with real-time GPS location capture and multi-channel sharing.
2. An interactive map displaying pre-configured safe zones (Quell Zones) at hospitals, shelters, and community centers across all Indian state capitals, with turn-by-turn routing to the nearest safe location.
3. A rule-based chatbot (QChat) backed by a hosted REST API, capable of answering disaster-related queries and navigating users to platform features.
4. A volunteer management module with registration, a login flow, and a post-login dashboard that tracks hours, tasks, badges, and upcoming events.

The platform is targeted at users in India and references Indian emergency services (NDRF, state disaster management authorities) with Quell Zone data covering all 28 states and 8 Union Territories.

---

## Key Features

- **One-Click SOS Dispatch:** Triggers the browser Geolocation API to capture the user's exact coordinates and pins them on the interactive map. On activation, users can share their location via WhatsApp, email, or simulate a call to emergency services (112).
- **Interactive Leaflet Map with Quell Zones:** Displays markers for 2–5 pre-defined safe zones per Indian state capital, including hospitals, community shelters, and relief centers. Each marker includes a popup with the facility name and a "Get Directions" button.
- **Turn-by-Turn Routing:** Integrates Leaflet Routing Machine with the OpenStreetMap Nominatim geocoding API to render yellow-highlighted routes from the user's current position to any searched location or selected Quell Zone.
- **Live Location Tracking:** Polls the Geolocation API at 5-second intervals to continuously update the user's pin on the map.
- **QChat Disaster Chatbot:** A chat interface that sends user messages to a deployed REST backend (`https://resq-ziw9.onrender.com`) and renders responses inline. The chatbot supports platform navigation actions, redirecting users to the SOS page or homepage based on intent.
- **User Registration with Health Profile:** The sign-in page includes a two-step flow: standard account registration followed by an optional health information form capturing allergies, chronic diseases, and medications—information relevant for triage during rescue operations.
- **Volunteer Registration and Dashboard:** Volunteers can register with full personal and health details, log in, and access a dashboard showing task status, upcoming training events, a leaderboard, badges for service milestones, and a Chart.js doughnut visualization of hours by activity category.
- **Donation Portal:** Links to UPI and PayPal donation endpoints to fund relief operations.
- **Emergency Contact Modal:** Homepage displays India-specific emergency numbers (112, 100, 101, 108, NDRF) in a modal triggered on demand.
- **Responsive Design:** All pages include responsive CSS breakpoints for mobile and tablet viewports.

---

## System Architecture and Workflow

### 1. Landing Page (`index.html`)

The user arrives at the homepage, which displays a navigation bar, latest disaster alert cards, and an emergency contact modal. From here, users can navigate to any module: SOS, QChat, Services, or Sign In.

### 2. SOS Flow (`sos.html`)

When the user clicks **Send SOS**, the platform:
- Plays an audio alert tone.
- Calls `navigator.geolocation.getCurrentPosition()` to retrieve the device's GPS coordinates.
- Drops a custom SOS marker on the Leaflet map and centers the view on the user's location.
- Reveals contact action buttons: share to WhatsApp (constructs a Google Maps link embedded in a pre-filled WhatsApp URL), share via Email (constructs a `mailto:` URI), or trigger a simulated emergency call.

The user can also type any location into the search bar. The platform queries the Nominatim API, places a marker at the result, and draws a route from the user's current position using Leaflet Routing Machine.

Quell Zone markers (hospitals, shelters) are pre-loaded for all Indian state capitals on page load. Clicking a zone popup and selecting **Get Directions** triggers routing from the user's current position to that specific zone.

### 3. QChat (`Qchat.html`)

The user types a query into the chat input. The frontend sends a GET request to the deployed backend:

```
GET https://resq-ziw9.onrender.com/get?msg=<encoded_message>
```

The backend returns a JSON response (`{ "response": "..." }`) which is rendered into the chat window. If the response contains anchor tags with a `data-action` attribute, clicking them triggers client-side navigation to the SOS page or homepage.

### 4. Services and Volunteer Flow (`service.html` → `volunteer.html`)

The Services page presents the platform's mission, donation links, and two volunteer pathways. New volunteers fill out a registration modal (name, email, phone, address, age, health info). Returning volunteers log in via a credentials modal, which redirects them to the volunteer dashboard.

The volunteer dashboard (`volunteer.html`) displays:
- Task list with statuses (In Progress, Completed, Pending)
- Upcoming event calendar with RSVP buttons
- Volunteer leaderboard ranked by service hours
- Badges and achievement milestones
- A Chart.js doughnut chart breaking down hours by activity category
- Buttons to download reports and generate service certificates

### 5. User Registration (`ppj.html`)

New users register with a username, email, and password. On form submission, a secondary health information form appears for optional medical profile completion. The login flow accepts existing credentials and redirects to the homepage.

---

## Tech Stack

**Frontend**
- HTML5, CSS3, vanilla JavaScript (ES6+)
- Google Fonts (Poppins)
- Font Awesome 6 (icon library)
- Boxicons 2.1.4 (icon library, used on login page)

**Mapping and Routing**
- Leaflet.js (interactive map rendering)
- Leaflet Routing Machine (turn-by-turn route display)
- OpenStreetMap tile layer (map tiles)
- Nominatim API (geocoding and location search)

**Data Visualization**
- Chart.js (doughnut chart on volunteer dashboard)

**Backend / API**
- External REST API deployed on Render (`https://resq-ziw9.onrender.com`) — handles QChat message processing and response generation

**External Integrations**
- Browser Geolocation API (GPS coordinate capture)
- WhatsApp URL scheme (`wa.me`) for location sharing
- `mailto:` URI scheme for email-based SOS sharing
- UPI deep link and PayPal donation URL for contribution flow

---

## Project Structure

```
RESQ-main/
├── index.html          # Homepage with alert cards and emergency contact modal
├── sos.html            # SOS Hub — interactive map, Quell Zones, routing, live tracking
├── Qchat.html          # QChat — disaster management chatbot interface
├── service.html        # Services — mission, donations, volunteer registration and login
├── volunteer.html      # Volunteer dashboard — tasks, events, charts, badges
├── ppj.html            # User login and registration with health profile step
├── exp.html            # About/Explore page — platform overview and feature summary
├── css/
│   ├── index.css       # Styles for homepage
│   ├── ppj.css         # Styles for login/registration page
│   └── volunteer.css   # Styles for volunteer dashboard
├── js/
│   ├── index.js        # JavaScript for homepage interactions
│   └── ppj.js          # JavaScript for login/registration toggle behavior
└── images/
    ├── RESQ.jpg        # Platform logo
    ├── chatbotbg.jpg   # Background image for QChat page
    ├── explore.jpg     # Background image for Explore page
    └── icon.jpg        # User avatar icon for volunteer dashboard
```

**Key files by function:**

- `sos.html` — The most complex module. Contains all Leaflet map initialization, Quell Zone data for all Indian state capitals, SOS trigger logic, routing, live tracking, and location sharing logic (~695 lines).
- `Qchat.html` — Self-contained chatbot page. All styling and logic are inlined. Communicates with the Render-hosted backend.
- `volunteer.html` — Dashboard page. Imports Chart.js from CDN and renders a doughnut chart. Dashboard content is currently static/demonstrative.
- `service.html` — Services page with inline modal management for volunteer registration and login routing.
- `ppj.html` — Login/register page with a two-step registration flow including a health information collection step.

---

## Installation and Setup

### Prerequisites

- A modern web browser (Chrome, Firefox, Edge, or Safari)
- A local HTTP server (required for correct asset loading and Geolocation API access over HTTPS in production)
- Node.js (optional, for running a local development server via `http-server` or similar)
- Git

### Clone the Repository

```bash
git clone https://github.com/<your-username>/RESQ.git
cd RESQ
```

### Running Locally

The project is a static frontend application with no build step. It can be served with any static file server.

**Option 1: Using Python**

```bash
# Python 3
python -m http.server 8080
```

Open `http://localhost:8080` in your browser.

**Option 2: Using Node.js `http-server`**

```bash
npm install -g http-server
http-server -p 8080
```

Open `http://localhost:8080` in your browser.

**Option 3: Using VS Code Live Server extension**

Open the project folder in VS Code, right-click `index.html`, and select **Open with Live Server**.

### Configuration Notes

- **QChat Backend:** The chatbot connects to a pre-deployed REST API at `https://resq-ziw9.onrender.com/get`. If you intend to run your own backend, update the fetch URL in `Qchat.html`:
  ```javascript
  const response = await fetch(`https://your-backend-url/get?msg=${encodeURIComponent(message)}`);
  ```
  The backend is expected to return a JSON object with the shape: `{ "response": "<string>" }`.

- **Geolocation:** Browser geolocation requires the page to be served over HTTPS in production environments. When running locally over HTTP, most browsers will still allow geolocation with a permission prompt.

- **Routing (Leaflet Routing Machine):** Routing uses the default OSRM demo server. For production deployments, configure a self-hosted OSRM instance or a commercial routing provider to avoid rate limits.

- **Donation Links:** The UPI and PayPal links in `service.html` use placeholder identifiers (`donate@upi`, `your-paypal-email`). Replace these with valid credentials before deployment.

---

## Usage

### For End Users (Civilians)

1. Open the application in a browser and navigate to the **SOS** page.
2. Allow location access when prompted.
3. Click **Send SOS** to capture your location, trigger an alert, and reveal sharing options.
4. Use **Share via WhatsApp** or **Share via Email** to send your GPS coordinates to a contact.
5. Browse **Quell Zone markers** on the map to find the nearest hospital or shelter. Click a marker and select **Get Directions** to get a route.
6. Use the **Search** bar to look up any location by name and receive routing from your current position.
7. Navigate to **QChat** to ask questions about disaster preparedness, safety procedures, or platform navigation.

### For Volunteers

1. Navigate to **Services** and click **Become a Volunteer**.
2. Complete the registration form with personal and health details and submit.
3. On subsequent visits, click **Already a Volunteer?**, enter your credentials, and access the volunteer dashboard.
4. The dashboard provides task status, upcoming event schedules, leaderboard rankings, and downloadable reports.

### For New Users (Account Registration)

1. Click **Sign In** in the navigation bar.
2. Select **Register**, complete the account form, and submit.
3. Fill in the optional health information form for medical profile storage.

---

## Screenshots / Demo

_Screenshots and a live demo link can be added here._

| Page | Description |
|------|-------------|
| Homepage | Alert cards, emergency contact modal |
| SOS Hub | Leaflet map with Quell Zones, routing, and SOS controls |
| QChat | Chatbot interface with disaster Q&A |
| Services | Donation links, volunteer registration |
| Volunteer Dashboard | Task tracker, leaderboard, Chart.js activity chart |
| Login / Register | Sliding login/register form with health profile step |

To add screenshots, place image files in the `images/` directory and reference them here:

```markdown
![SOS Hub](images/screenshot-sos.png)
![Volunteer Dashboard](images/screenshot-dashboard.png)
```

---

## Future Enhancements

- **Backend Integration for User Data:** Replace the current client-side-only registration and health form flows with a server-side database (e.g., Firebase, PostgreSQL via Node.js/Python) to persist user accounts, health profiles, and volunteer records.
- **Real-Time Weather Integration:** Connect the weather display panel in the SOS Hub to a live weather API (e.g., OpenWeatherMap) using the captured GPS coordinates, replacing the current simulated weather output.
- **Push Notifications for Disaster Alerts:** Implement a Web Push Notifications service to deliver real-time disaster alerts to registered users based on their stored location.
- **Admin Dashboard:** Build an operations panel for NDRF/SDMA coordinators to monitor active SOS alerts on a central map, assign volunteers, and update Quell Zone availability in real time.
- **Enhanced Chatbot with Conversational Context:** Upgrade the QChat backend to support multi-turn conversation history, and integrate a language model capable of answering nuanced disaster preparedness and first-aid queries.
- **Offline Support via Service Workers:** Add a service worker to cache critical pages (SOS, emergency contacts) for offline access during network outages common in disaster scenarios.
- **Role-Based Access Control:** Differentiate between civilian users, registered volunteers, and admin coordinators with route-protected views and permission-based feature access.
- **Multilingual Support:** Add localization for major Indian languages (Hindi, Tamil, Telugu, Bengali) to improve accessibility for non-English-speaking users during emergencies.
- **Verified Donation Tracking:** Integrate a payment gateway (Razorpay or Stripe) with a transparent fund allocation dashboard visible to donors.

---

## License

This project is licensed under the MIT License.

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
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
