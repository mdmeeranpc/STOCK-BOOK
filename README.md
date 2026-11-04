# 🌱 AGRI TECH 3.0

> **Smart Farming. Better Decisions. Stronger Future.**

AGRI TECH is a modern, full-stack, mobile-friendly application engineered to make agricultural science, plant diagnostics, and home gardening accessible, intuitive, and delightful for everyone—from first-time balcony plant parents to multi-acre commercial farmers.

---

## 🌟 Key Capabilities & Sections

### 1. Dual-Core Mode Architecture
- **Home Gardening Mode (🪴):** Built for indoor plants, balcony containers, terrace gardens, and backyard raised beds. Includes pot size selectors, care reminders, soil mix formulas, and beginner-friendly guides.
- **Smart Farming Mode (🚜):** Built for commercial growers. Features soil NPK fertilizer analysis, precision irrigation advisories, agricultural weather intelligence, and live APMC Mandi commodity auctions.
- **Seamless Switching:** Toggle between modes with a single click from the top navigation bar or personalized onboarding survey.

### 2. Complete Authentication & Profile Security
- **Registration:** Email validation, phone (optional), real-time password strength meter, duplicate account prevention, secure bcrypt password hashing.
- **Login & Persistence:** JWT-based session management, "Remember Me" extended tokens, and automatic re-authentication upon browser reopening.
- **Password Recovery:** Time-limited, single-use cryptographically secure reset tokens, simulated and SMTP-ready email dispatch, and immediate token invalidation upon password reset.
- **User Profile:** Manage personal information, location, language preferences, farming interests, and complete account deletion with full cascade data wipe.

### 3. Automatic Data Saving & Offline Support (PWA)
- **Zero Data Loss:** All user data (plants, watering logs, fertilizer schedules, care reminders, growth journal entries, AI diagnoses, and chat history) is permanently stored in the backend database.
- **Auto-Save Indicators:** Visual real-time feedback with "Saving..." and "All changes saved" timestamps.
- **Progressive Web App (PWA):** Installable on Android, iOS, and desktop browsers with custom service worker asset caching and offline status detection.

### 4. Interactive AI Plant Doctor
- **Foliar Disease Diagnosis:** Upload photos directly from phone camera or file system, select crop type, and describe symptoms.
- **Comprehensive Reports:** Problem identification, visible symptom breakdown, confidence score, eco-friendly organic remedies, chemical alternatives, preventative measures, and sunlight/soil adjustments.
- **Powered by Google Gemini Generative Vision API** with a built-in agronomic knowledge base fallback.

### 5. Multilingual AI Assistant with Voice & Read Aloud
- **5 Native Languages:** English, Kannada (ಕನ್ನಡ), Hindi (हिंदी), Tamil (தமிழ்), and Telugu (తెలుగు).
- **Voice-Enabled:** Hands-free voice dictation via Web Speech Recognition API and spoken responses via Speech Synthesis (TTS).
- **Practical Mentorship:** Answers questions about organic pest remedies, neem sprays, compost ratios, and crop schedules.

### 6. Live Meteorological & Mandi Market Intelligence
- **Weather Forecasting:** Live temperature, apparent feels-like, humidity, wind speed, rainfall probability, spray condition suitability, and fungal blight advisories via Open-Meteo.
- **APMC Mandi Commodity Prices:** Real daily prices across Indian markets (e-NAM verified) with Min, Max, Modal prices, daily change percentages, and 6-day trend visualization.

### 7. Learning Centre & Plant Library
- **10+ Masterclass Guides:** Growing tomatoes, chillies, coriander from split seeds, mint from cuttings, organic compost in 30 days, potting mix formulas, and balcony setup.
- **Botanical Encyclopedia:** Searchable database with soil pH ranges, germination days, harvest timelines, companion plants, and common pitfalls.

### 8. Personal Gardening Journal & Community
- **Milestone Timeline:** Track seedling growth, height measurements, flowering, and harvest dates with photos and progress notes.
- **Gardener Exchange:** Share organic recipes, give likes, and exchange tips with fellow gardeners.

---

## 🛠️ Technology Stack

| Layer | Technologies |
|---|---|
| **Frontend** | React 19, Vite, Tailwind CSS v4, Framer Motion, Lucide Icons, Canvas Confetti |
| **Backend** | Node.js (v24), Express.js (ESM), Multer (Image Uploads), Nodemailer |
| **Security & Auth** | JSON Web Tokens (JWT), Bcrypt.js, Crypto token generator |
| **Database** | Persistent file-backed JSON database engine (`agritech_db.json`) + MongoDB Atlas support via URI |
| **PWA & Offline** | Web App Manifest, Service Worker (`sw.js`), Cache API, IndexedDB ready |
| **Integrations** | Open-Meteo API, Google Gemini Generative AI SDK (`@google/generative-ai`), Web Speech API |

---

## 🚀 Quick Start & Installation

### Prerequisites
- Node.js (v18 or higher recommended)
- npm or pnpm

### 1. Clone & Install Dependencies

```bash
# Clone the repository
git clone <repo-url>
cd "AGRI TECH"

# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install
```

### 2. Configure Environment Variables

Create a `.env` file in the `backend/` directory (see `.env.example`):

```env
PORT=5000
NODE_ENV=development
JWT_SECRET=your-secure-jwt-secret-key-2026
FRONTEND_URL=http://localhost:5173

# Optional: Google Gemini API Key for live AI plant diagnostics & assistant
GEMINI_API_KEY=YOUR_GEMINI_API_KEY_HERE

# Optional: MongoDB Atlas URI (Uses zero-config persistent local storage if omitted)
# MONGODB_URI=mongodb+srv://<user>:<password>@cluster.mongodb.net/agritech

# Optional: SMTP Email configuration for live password reset emails
# SMTP_HOST=smtp.gmail.com
# SMTP_PORT=587
# SMTP_USER=your-email@gmail.com
# SMTP_PASS=your-app-password
```

### 3. Run the Application

Start the backend server:
```bash
# From backend directory
node server.js
# Or with auto-reload:
node --watch server.js
```

Start the frontend development server:
```bash
# From frontend directory
npm run dev
```

Open your browser at: **`http://localhost:5173`**

---

## 🧪 Automated End-to-End Testing

AGRI TECH includes an end-to-end automated test suite covering all critical authentication, database, reminder, AI, and weather endpoints:

```bash
node backend/tests/test_all.js
```

**Verification Results:**
- ✅ Health Endpoint Check
- ✅ User Registration & JWT Generation
- ✅ Duplicate Account Prevention
- ✅ User Login & Session Persistence
- ✅ Invalid Password Rejection
- ✅ Current Profile Fetch (`/auth/me`)
- ✅ Profile Update Persistence
- ✅ Add Plant with Auto-Reminders
- ✅ Quick Action: Water Plant
- ✅ Auto-generated Smart Care Reminders Verified
- ✅ Smart Reminder Completion
- ✅ Weather Intelligence & 7-Day Forecast
- ✅ Market Mandi Commodity Prices
- ✅ Smart Farming NPK Crop Recommendation
- ✅ AI Plant Doctor Diagnosis & Organic Remedy
- ✅ AI Assistant English Response
- ✅ AI Assistant Kannada (ಕನ್ನಡ) Response
- ✅ Forgot Password Token Generation & Email Dispatch
- ✅ Password Reset Execution with Token Invalidation
- ✅ Login with Newly Reset Password

**Result: 20 Tests Passed / 0 Failed (100% Pass Rate)**

---

## 📱 Progressive Web App (PWA) Installation

- **On Mobile (Chrome / Android):** Tap the browser menu `⋮` and select **"Add to Home Screen"** or **"Install App"**.
- **On Desktop (Chrome / Edge):** Click the install badge in the URL address bar to install AGRI TECH as a standalone desktop application.

---

## 🔒 Security Best Practices

1. **Passwords:** Hashed with bcrypt with salt rounds before being stored.
2. **Access Control:** User authorization middleware checks ensure users can only view, edit, or delete their own plants, reminders, and journals.
3. **Password Recovery:** Time-limited (1-hour) single-use tokens; invalid email queries return generic responses to prevent enumeration attacks.
4. **Environment Isolation:** Zero private API keys, secrets, or database URLs are exposed in frontend bundle code.

---

## 🌿 License

Built with pride for farmers and gardeners worldwide.  
**AGRI TECH — Smart Farming. Better Decisions. Stronger Future.**
"# agritech2526" 
