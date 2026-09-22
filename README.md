# HerRoute — Beyond the Fastest Route 🛡️✨

> **AI-Powered Context-Aware Safety Navigation Platform Designed for Women's Mobility**

HerRoute is a modern, privacy-focused safety routing engine and navigation platform that evaluates travel paths beyond mere distance or travel time. By analyzing street illumination, pedestrian footfall density, surveillance coverage, nearby 24/7 verified safe havens, and time-of-day contextual risk factors, HerRoute empowers women to make informed and secure travel decisions.

---

## 🌟 Key Features

* **🔍 Real Location Autocomplete & Geocoding**:
  * Debounced place search powered by OpenStreetMap (Photon & Nominatim) with support for Mapbox Geocoding and Google Places API.
  * Local proximity biasing for Chennai, Tamil Nadu, and India.
  * Rich categorization for Metro Stations, Railway Stations, Bus Stands, Universities/Colleges, Hospitals, and Commercial Hubs.
  * Strict validation ensuring real latitude/longitude coordinates are used for all routing decisions.

* **🛣️ Multi-Route Safety Engine**:
  * Real-time routing via Open Source Routing Machine (OSRM) and Mapbox Directions API.
  * Computes genuine polyline geometries, precise distances (km), travel times (min), and turn-by-turn maneuvers.
  * Generates multiple alternative corridors for direct safety comparisons.

* **💡 Contextual Risk & Safety Analysis**:
  * **Street Illumination Index**: Evaluates active LED streetlighting along primary vs secondary arteries.
  * **Pedestrian & Retail Footfall**: Scores active commercial storefronts and transit crowd density.
  * **Surveillance Grid**: Tracks municipal AI camera and CCTV coverage.
  * **24/7 Safe Haven Checkpoints**: Highlights nearby women helpdesks, police stations, trauma hubs, and monitored metro interchange zones.
  * **Time Shift Engine**: Dynamically shifts predictive risk ratings based on departure hours (Day vs Dusk vs Late Night).

* **🧭 Dedicated Live Turn-by-Turn Navigation HUD**:
  * Real GPS tracking via `navigator.geolocation.watchPosition` with graceful permission handling.
  * Turn maneuver guidance with upcoming step preview and distance countdowns.
  * Cross-track off-route detection (>75m deviation) with instant route recalculation.
  * **Test Drive Simulator**: Allows interactive trip simulations along any user-selected route.
  * **1-Tap Emergency SOS**: Instant coordinate broadcast to trusted guardians and women helplines (1091 / 112).

* **🎭 Separation of Real Navigation & Interactive Demo**:
  * **Real Navigation**: Operates on live user-selected locations, genuine GPS coordinates, and real routing data.
  * **Interactive Live Demo**: Standalone sandbox demonstrating contextual safety features and simulation workflows without affecting live routes.

---

## 🛠️ Technology Stack

* **Framework**: [Next.js 14 (App Router)](https://nextjs.org/)
* **Language**: [TypeScript](https://www.typescriptlang.org/)
* **Styling**: [Tailwind CSS](https://tailwindcss.com/) with custom Glassmorphism & Cyberpunk-Safe Aesthetic
* **Animations**: [Framer Motion](https://www.framer.com/motion/)
* **Icons**: [Lucide React](https://lucide.dev/)
* **Geocoding & Routing**: OpenStreetMap (Photon / Nominatim), OSRM, and Mapbox APIs

---

## 📁 Project Architecture

```text
HerRoute/
├── app/
│   ├── globals.css           # Custom glassmorphism, glowing gradients & animations
│   ├── layout.tsx            # Global metadata, SEO tags & typography
│   └── page.tsx              # Main homepage & route planning state container
├── components/
│   ├── ExploreDashboardModal.tsx # Route query dashboard with autocomplete & filters
│   ├── LocationAutocomplete.tsx  # Debounced place search dropdown with categorised icons
│   ├── RealNavigationModal.tsx   # Dedicated turn-by-turn navigation HUD & live map
│   ├── MapVisualization.tsx      # 3D isometric & 2D vector hero map visualization
│   ├── DemoModal.tsx             # Standalone sandbox demo simulator
│   ├── InteractiveRiskExplorer.tsx # Contextual risk factor deep-dive comparison
│   ├── Hero.tsx                  # Hero section with live statistics and mission tagline
│   ├── FeatureGrid.tsx           # 6 core pillar features
│   ├── HowItWorks.tsx            # 5-step interactive workflow timeline
│   ├── AboutMission.tsx          # Ethical AI & women's safety mission
│   ├── Navbar.tsx                # Glassmorphic header with navigation links
│   └── Footer.tsx                # Footer with disclaimer and contact channels
├── services/
│   ├── geocodingService.ts   # Real place autocomplete, debouncing & categorization
│   ├── routingService.ts     # Real coordinate routing, OSRM/Mapbox API integration
│   ├── safetyService.ts      # Illumination, CCTV, footfall & risk analysis
│   └── navigationService.ts  # Haversine distance, off-route detection & progress tracking
└── data/
    └── routesData.ts         # Types, interfaces, presets & fallback benchmarks
```

---

## 🚀 Getting Started

### Prerequisites

* Node.js 18.x or higher
* npm, yarn, or pnpm

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/herroute.git
cd herroute
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables (Optional)

HerRoute works immediately out-of-the-box using open-source geocoding (Photon / Nominatim) and OSRM routing. If you want to use Mapbox or Google Maps providers, create a `.env.local` file:

```env
# Optional Mapbox API Key
NEXT_PUBLIC_MAPBOX_TOKEN=your_mapbox_token_here

# Optional Google Maps API Key
NEXT_PUBLIC_GOOGLE_MAPS_KEY=your_google_maps_key_here
```

### 4. Run Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🧪 Acceptance Testing Workflow

1. **Origin Search**:
   * Click **Explore HerRoute**.
   * Type `St Thomas` in the Start Origin input.
   * Notice real autocomplete suggestions (e.g. *St Thomas Mount Metro Station*, *St Thomas Mount Railway Station*).
   * Click to select a location.
2. **Destination Search**:
   * Type `Easwari Engineering College` in the Destination input and select it from the suggestions.
3. **Route & Safety Evaluation**:
   * Click **Find Safe Route**.
   * Real routes are calculated with live distance, duration, and safety breakdown (Lighting, Footfall, CCTV).
4. **Live Turn-by-Turn Navigation**:
   * Click **Start Navigation** to launch the full-screen Real Navigation HUD.
   * View live maneuver steps, progress bars, telemetry stats, and off-route detection.
   * Test simulated driving using the **Test Drive Sim** button or track live GPS.
   * Test the **1-Tap SOS** button to view emergency coordinate dispatching.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
