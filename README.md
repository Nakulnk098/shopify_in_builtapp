# 🌟 Prism - Next-Gen Shopify AI Assistant & Automation Platform

Prism is an advanced AI-powered Shopify application built to simplify store management, automate repetitive tasks, provide smart analytics, and guide merchants interactively through the Shopify Admin using a Chrome extension.

Built with a modern web stack, Prism integrates seamlessly into the Shopify App Bridge ecosystem.

---

## 🏗️ Architecture & Technology Stack

Prism consists of three interconnected systems:

### 🎨 Frontend (Dashboard)

* React 18
* TypeScript
* Vite
* Shopify Polaris UI

**Features**

* Multi-level dashboard architecture
* Responsive design
* Data visualization with custom charts
* Context-based state management

### ⚙️ Backend (API & AI Engine)

* Node.js
* Express.js
* Shopify Admin API
* OAuth 2.0 Authentication

**AI Integrations**

* Google Gemini Pro
* Google Gemini Vision

**Used for**

* Product generation from images
* SEO blog writing
* Legal policy generation
* Store content auditing
* Shopify tutorials generation

### 🧩 Chrome Extension (Visual Guidance)

Provides real-time step-by-step guidance inside Shopify Admin.

**How it works**

* Receives AI-generated UI steps
* Detects page elements
* Highlights buttons/menus visually
* Helps merchants navigate faster

---

# 🚀 Core Features

## 1️⃣ Level 1: Core Automation

* Add Product using image upload + AI generation
* Write Blogs instantly with AI
* Generate delivery/return policies
* Manage unfulfilled orders
* Voice hints using Web Speech API

---

## 2️⃣ Level 2: Order Management

* Customer order details
* Shipping addresses
* Financial status
* One-click fulfillment actions

---

## 3️⃣ Level 3: GEO Audit (Generative Engine Optimization)

AI-powered store analysis across:

* Technical SEO
* On-page SEO
* Content Quality
* Product Images

**Outputs**

* Overall Health Score
* Layer Scores
* Priority Action Plan

---

## 4️⃣ Level 4: Product Intelligence

Machine Learning clustering dashboard.

**Features**

* Scatter chart visualization

* Product clusters:

  * High Performer
  * Trust Issue
  * Low Engagement

* Live simulation sliders:

  * Title Quality
  * Reviews
  * Rating

---

## 🧭 Shopify Navigation Guide

Users can ask:

> “How do I delete a product?”

Prism converts answers into actionable steps.

Click **Visualize on Screen** to launch Chrome extension guidance.

---

## 🌍 Multi-language Support

Supported Languages:

* English
* Hindi
* Kannada

Language changes update instantly across dashboard.

---

# ⚙️ Setup

## Prerequisites

* Node.js v18+
* Shopify Partner Account
* Dev Store
* Ngrok
* Gemini API Key

## Installation

```bash
git clone <your-repo-url>
cd prism
npm install
```

## Environment Variables

```env
SHOPIFY_API_KEY=
SHOPIFY_API_SECRET=
SHOPIFY_APP_URL=
GEMINI_API_KEY=
```

## Run

```bash
npm run dev
```

---

# 🔌 Chrome Extension Setup

1. Open Chrome
2. Visit `chrome://extensions/`
3. Enable Developer Mode
4. Click Load Unpacked
5. Select extension folder

---

# 🛡️ Security

* Secure `postMessage()` communication
* Cross-origin iframe optimized
* Shopify App Bridge compatible

---

# 🤝 Contributing

Contributions, ideas, and improvements are welcome.

---

# ⭐ Built for Hackathons, AI Commerce & Future Shopify Sellers
