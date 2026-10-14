# AsphaltSense 🛣️🤖
### Crowdsourced Pothole Detection, Smart Logistics & TinyFish AI Agent Platform
> *Turning Every Smartphone into an Automated Road-Mapping Sensor with Autonomous Contractor Warranty Audits*

**AsphaltSense** solves India's severe road damage and pothole crisis through **passive hardware telemetry** (Web `DeviceMotionEvent` API) embedded in gig-economy commercial delivery fleets (Zomato, Swiggy, Zepto, Blinkit, Delhivery) and citizen commuter devices, combined with the **TinyFish Web Agent API** (`agent.tinyfish.ai`) to autonomously cross-reference municipal road construction tenders and enforce contractor warranties.

---

## 🚀 Key Features

### 1. Passive Hardware Telemetry (Web DeviceMotionEvent API)
- **Zero Hardware Friction**: Uses native smartphone accelerometers and gyroscopes via the Web `DeviceMotionEvent` API.
- **Autonomous Shock Detection**: High-pass gravity filtration isolates vertical jerk anomalies ($> 2.8\text{G}$) with zero manual input required from drivers.
- **Live Seismograph**: Real-time 60fps waveform plotting instantaneous vertical $a_z$, lateral roll $a_x/a_y$, and vibration spikes.
- **Synthesized Web Audio Chimes**: Auditory and visual cues triggered on high-force impacts.

### 2. TinyFish AI Road Intelligence Agent (`agent.tinyfish.ai`)
- **Municipal Tender & Warranty Discovery**: When a pothole cluster is flagged, the TinyFish AI Agent autonomously crawls and parses municipal e-procurement portals (e.g. BBMP, MMRDA, Delhi PWD, NHAI).
- **Contractor Liability Enforcement**:
  - Automatically extracts original road package tender IDs, awarded contractor names, and mandatory 3-Year **Defect Liability Periods (DLP)**.
  - If a road is within its warranty window, flags: **`⚠️ CONTRACTOR LIABLE (Zero Public Expense)`**.
  - Generates legal notice drafts under Clause 14.2 of Municipal PWD Code, saving public crores from duplicate contractor billing!
- **Anti-Bot & Stealth Navigation**: Harnesses TinyFish cloud browser infrastructure with built-in CAPTCHA handling and rank-stable data extraction.

### 3. Multi-Driver Spatial Clustering & Confidence Engine
- **Spatial Aggregation Radius**: Groups pings within a 35m corridor using the Haversine formula.
- **Statistical Corroboration**:
  - `1 Ping`: Marked as an **Isolated Anomaly** (~20% confidence, e.g. single bump or speedbreaker).
  - `2–4 Pings`: Marked as a **Suspected Road Defect** (40–70% confidence).
  - `5–14 Pings`: Marked as a **Confirmed Pothole** (75–94% confidence).
  - `15+ Pings`: Auto-escalated to **Critical Structural Hazard** (95–99% confidence, triggers automated work order).

### 4. Interactive GIS Command Center
- High-contrast dark GIS map with CartoDB Dark Matter tiles.
- Color-coded severity markers (Critical $> 5.5\text{G}$, High $> 4.0\text{G}$, Medium $> 3.0\text{G}$, Low/Anomaly).
- Live simulated vehicle tracking showing active couriers moving along city arteries.
- Telemetry Deep-Dive Drawer: Inspect peak G-force, first/last detected dates, and delivery fleet contributions (e.g. 11 Zomato, 7 Swiggy, 4 Zepto).
- City Switcher with pre-seeded datasets for **Bengaluru, Mumbai, Delhi, and Hyderabad**.

### 5. Automated Municipal Authority (PWD/BBMP/NHAI) Action
- **Algorithmic Priority Score**:
  $$\text{Priority} = (\text{Peak G-Shock Factor}) \times (\text{Traffic Volume}) \times (\text{Logistics Impact})$$
- **Work Order Lifecycle**: `Pending Review` $\rightarrow$ `Contractor Dispatched` $\rightarrow$ `Repair In Progress` $\rightarrow$ `Repaired & Verified`.
- Contractor assignment, repair budget tracking in ₹ INR, and exportable Work Order CSV.

### 6. B2B Smart Logistics & Fleet ROI
- **3-Line SDK Integration (`@asphaltsense/telemetry-sdk`)**: Sample code for React Native, Vanilla JS `<script>`, Flutter, and Node.js.
- **Fleet ROI Calculator**: Interactively compute suspension repair savings, fuel waste reduction, and cargo spill prevention in ₹ INR.
- **Smart Pothole Avoidance Routing API**: Side-by-side comparison of shortest route vs. smooth bypass route.

### 7. Citizen Transparency & Ward Road Quality Index (RQI)
- Ward-by-ward RQI ranking (0 to 100).
- Closed-loop sensor audit verifying post-repair smooth pavement.

---

## 🛠️ Tech Stack

- **Frontend**: Next.js 14 (App Router), React 18, Tailwind CSS, Lucide Icons
- **AI Web Agent**: TinyFish API (`https://agent.tinyfish.ai/run`, `https://api.search.tinyfish.ai`)
- **Mapping Engine**: Leaflet GIS with CartoDB Dark Matter tiles
- **Telemetry Access**: Web `DeviceMotionEvent` API + HTML5 Geolocation API
- **Audio Feedback**: Web Audio API synthetic frequency ramp synthesizer
- **Backend & APIs**: Next.js API Routes (`/api/telemetry`, `/api/potholes`, `/api/tinyfish/agent`, `/api/work-orders`, `/api/analytics`, `/api/simulate`)
- **Language**: TypeScript

---

## ⚡ Quickstart

```bash
# 1. Install dependencies
npm install

# 2. (Optional) Set TinyFish API Key
# Set TINYFISH_API_KEY in .env.local or enter directly in UI
echo "TINYFISH_API_KEY=tf_live_your_key_here" > .env.local

# 3. Start production server
npm run build
npm start
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 📱 Routes & Pages

| Route | Description |
|---|---|
| `/` | **National Telemetry Command Center**: Interactive GIS map, metrics ticker, telemetry inspector & TinyFish AI agent audit |
| `/drive` | **Driver Telemetry & Simulator**: 60fps seismograph, mobile sensor, route drive simulator |
| `/pwd` | **Municipal Authority Action**: Priority queue, TinyFish contractor audit, work orders lifecycle |
| `/logistics` | **B2B Smart Logistics**: SDK integration sandbox, fleet ROI calculator, avoidance routing |
| `/transparency` | **Citizen Transparency**: Ward Road Quality Index (RQI) leaderboard, sensor repair audits |
