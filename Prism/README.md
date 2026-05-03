# 🌟 Prism - Next-Gen Shopify AI Assistant & Automation Platform

Prism is an advanced, AI-powered Shopify application designed to radically simplify store management, automate tedious tasks, provide deep analytical intelligence, and interactively guide merchants through the Shopify Admin via a companion Chrome extension. 

Built with the modern web stack, Prism seamlessly integrates into the Shopify App Bridge ecosystem.

---

## 🏗️ Architecture & Technology Stack

Prism is composed of three interconnected systems:

1. **Frontend (Dashboard)**
   - **Framework:** React 18, TypeScript, Vite
   - **UI Library:** Shopify Polaris (for a native Shopify look-and-feel)
   - **State & Context:** React Context API (`DashboardContext`, `I18nContext`)
   - **Features:** Multi-level dashboard architecture, responsive design, data visualization via custom SVG components (Scatter charts, Health Gauges).

2. **Backend (API & AI Engine)**
   - **Framework:** Node.js (Express)
   - **Shopify Integration:** Shopify Admin API (OAuth 2.0 flow, Session persistence)
   - **AI Orchestration:** Google Gemini Pro & Vision APIs (`gemini.js`). Used for:
     - Generating product listings from images.
     - Formulating full-length SEO-optimized blog posts.
     - Generating store legal policies dynamically.
     - Analyzing and scoring store content (GEO Audit).
     - Synthesizing interactive Shopify Admin tutorials.

3. **Chrome Extension (Visual Guidance)**
   - **Role:** Content-script injected into the active browser page.
   - **Communication:** Secure `postMessage` bridge between the Shopify App iframe (`window.parent.postMessage`) and the extension.
   - **Functionality:** Listens for AI-generated UI steps, locates DOM elements in the Shopify Admin, and visually highlights them to guide the merchant step-by-step.

---

## 🚀 Core Features & "Levels"

The application dashboard is categorized into distinct capabilities, accessible via the top navigation tabs:

### 1️⃣ Level 1: Core Automation
Designed for rapid store setup and essential tasks.
- **Add Product:** Upload a product photo; the AI vision model automatically generates an optimized title, description, and pricing structure.
- **Write Blog:** Select a topic and the AI generates a complete, publish-ready blog article.
- **Setup Rules:** Answer a few questions about your business, and the AI drafts custom delivery and return policies.
- **Manage Orders:** View unfulfilled orders and process them with a single click.
- **Accessibility:** Integrated Web Speech API for audible UI feedback (Voice Hints) and localized content.

### 2️⃣ Level 2: Operations Management (Orders)
- Deep-dive into order fulfillment.
- Clean list and detail views of customer orders, shipping addresses, financial status, and line items.
- One-click fulfillment actions integrated directly with the Shopify API.

### 3️⃣ Level 3: GEO Audit (Generative Engine Optimization)
- A specialized AI auditing engine that analyzes your store across multiple dimensions: Technical SEO, On-page SEO, Content Quality, and Images.
- **Scoring System:** Outputs an overall "Health Score" alongside detailed "Layer Scores."
- **Action Plan:** Provides a prioritized, multi-tier execution plan (Critical, High, Medium, Low severity) to improve store performance.

### 4️⃣ Level 4: Product Intelligence (Cluster Dashboard)
- **ML Clustering:** Visualizes products on a Scatter Chart based on Visibility/Attraction vs. Buyer Confidence.
- **Clusters:** Groups products into actionable categories (e.g., *High Performer*, *Trust Issue*, *Low Engagement*).
- **Interactive Simulation:** Merchants can use dynamic sliders (Title Quality, Reviews, Rating) to simulate how improving specific product metrics could shift a product into a more profitable cluster.

### 🧭 Shopify Navigation Guide (Chat & Visualize)
- A chat-like interface where merchants can ask questions like *"How do I delete a product?"*
- The AI breaks down the answer into actionable steps.
- Clicking **"Visualize on Screen"** triggers the Chrome extension to physically guide the user through the Shopify Admin menu using highlighting overlays.

---

## 🌍 Internationalization (i18n)

Prism is built for a diverse merchant base with deep multi-language support.
- **Languages Supported:** English (`en`), Hindi (`hi`), Kannada (`kn`).
- **Implementation:** Custom `I18nProvider` mapping static text via `translations.ts`.
- **UI:** A persistent language selector `<Select>` dropdown is available on the Level 1 dashboard, propagating language changes globally without page reloads.

---

## ⚙️ Development & Setup

### Prerequisites
- Node.js (v18+)
- A Shopify Partner Account & Development Store
- Ngrok (or similar tunneling service) for local App Bridge development
- Google Gemini API Key

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/omkar-prabhu-github/priss.git
   cd prism
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure Environment Variables:**
   Create a `.env.local` file in the root directory:
   ```env
   SHOPIFY_API_KEY=your_shopify_api_key
   SHOPIFY_API_SECRET=your_shopify_api_secret
   SHOPIFY_APP_URL=https://your-ngrok-url.ngrok-free.dev
   GEMINI_API_KEY=your_gemini_api_key
   ```

4. **Run the Development Server:**
   ```bash
   npm run dev
   ```
   *This starts the Vite frontend. Make sure your Express backend is also running concurrently (usually via a separate start script or concurrent setup).*

### Running the Chrome Extension
1. Open Chrome and navigate to `chrome://extensions/`
2. Enable **Developer mode**.
3. Click **Load unpacked** and select the `prism/extension` directory.

---

## 🛡️ Security & Cross-Origin Context

Due to Shopify App Bridge rendering the application within an `iframe` inside the Shopify Admin (`admin.shopify.com`), certain browser security policies apply.
- Cross-origin frame communication is handled strictly via secure `window.postMessage`.
- UI elements that rely on native browser window bounds (like some React Portals) have been optimized to native HTML equivalents (e.g., replacing `Popover` with native `<Select>`) to prevent React DevTools `SecurityError` crashes.

---

## 🤝 Contributing
Commits should be descriptive and follow conventional commit standards. Ensure `npm run lint` and `npm run build` pass successfully before pushing.

---
*Built with ❤️ for Shopify Merchants.*
