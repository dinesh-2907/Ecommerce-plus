# 🛡️ E-Shop Guardian AI

> **AI-Powered Trust & Intelligence Platform for Modern E-Commerce**

E-Shop Guardian AI is an AI-first SaaS platform designed to help e-commerce marketplaces build trust, reduce operational losses, improve seller credibility, simplify warranty management, and provide intelligent business insights through AI-powered workflows.

Unlike traditional e-commerce platforms, E-Shop Guardian AI is **not another online shopping website**. It is an intelligent platform that integrates with existing marketplaces such as **Amazon, Flipkart, Meesho, Shopify, Myntra, and Ajio** to enhance trust and operational efficiency for buyers, sellers, and marketplace administrators.

---

## 📌 Problem Statement

Modern e-commerce platforms face several operational and trust-related challenges that affect both businesses and customers.

Some of the major problems include:
- Customers forget product warranty information and struggle to claim warranties.
- Sellers incur significant losses due to product returns and fraudulent return requests.
- Duplicate or unverified sellers reduce customer trust.
- Near-expiry inventory often remains unsold, resulting in revenue loss.
- Marketplace administrators lack centralized intelligence to monitor trust, inventory, warranties, and operational risks.

These problems collectively reduce customer confidence, increase operational costs, and impact marketplace profitability.

---

## 💡 Our Solution

E-Shop Guardian AI provides an integrated Trust & Intelligence Platform that connects buyers, sellers, and administrators into a single ecosystem.

The platform focuses on:
- **Warranty Management**: Automated digital warranty generation and tracking.
- **Return Intelligence**: Fraud risk scoring and dispute management.
- **Seller Trust**: Verification status, seller metrics, and compliance ratings.
- **Inventory Intelligence**: Expiry tracking and markdown dynamic forecasting.
- **Live Order Fulfillment**: Real-time order dispatch and buyer notification pipeline.

The architecture is built on a production-ready Supabase backend designed to seamlessly support future AI agents.

---

## 🚀 Key Features

### 👤 Customer Portal (`/customer`)
- **Secure Authentication**: Real Supabase Auth login & sign-up.
- **AI Marketplace**: Browse active seller products with real-time stock and prices.
- **Seamless Purchase Flow**: Single-click order placement with automatic digital warranty generation.
- **Digital Warranty Center**: Track active cover, days remaining, serial numbers, and file claims.
- **Return Center**: File return requests with automated risk score calculation and status tracking.
- **Order History**: Track order lifecycle (`Processing`, `Shipped`, `Delivered`, `Cancelled`).
- **Real-Time Notifications**: Live updates for order status, warranty claims, and platform alerts.
- **User Settings**: Update name, phone, address, date of birth, gender, and avatar profile picture.

---

### 🏪 Seller Portal (`/seller`)
- **Seller Dashboard**: Revenue summaries, SKU tracking, and sales analytics.
- **Products Catalog**: Add, edit, and manage marketplace product listings with image URLs and batch expiry dates.
- **Live Customer Order Fulfillment (`/seller/orders`)**: Real-time feed of orders placed by customers. Dispatch (`Processing` → `Shipped`) and mark items as `Delivered` live without page refreshes.
- **Inventory Health & Expiry Intel**: Monitor stock velocity, set markdown discount overrides for expiring inventory, and forecast revenue recovery.
- **Seller Trust Index**: Monitor marketplace compliance score, defect rates, and resolve return dispute cases.
- **Company Settings**: Update shop name, business details, and seller profile information.

---

### 🛡️ Admin Panel (`/admin`)
- **Platform Executive Dashboard**: Top-level overview of GMV, total active users, verified sellers, and return defect rates.
- **Users Directory**: Manage platform customers and sellers, update verification status (`Active`, `Suspended`, `Pending Verification`), and adjust trust scores.
- **AI Insights Engine**: Real-time fraud pattern detection, size-swap anomaly logs, and system risk recommendations.
- **Admin Settings**: System configuration and profile management.

---

## 🤖 Planned & Implemented AI Modules

Although the current version focuses on delivering a production-ready Supabase backend and complete marketplace workflow, the platform includes built-in AI risk scoring rule engines and is architected for LLM agent integration via OpenRouter / Gemini.

### 🛡️ Warranty Guardian Agent (Planned)
- Explain warranty coverage in plain language
- Automated warranty expiry reminders
- AI claim verification and instant document understanding

### 🔍 Return Intelligence Agent (Implemented Engine + Planned LLM)
- Analyze customer return request patterns
- Predict return fraud risk scores dynamically (Low / Medium / High Risk)
- Recommend auto-approval or manual vendor inspection to reduce return fraud

### 🏷️ Smart Dynamic Pricing Agent (Implemented Engine + Planned LLM)
- Analyze batch expiry dates automatically
- Recommend dynamic markdowns for near-expiry products
- Minimize inventory waste and maximize revenue recovery

### ⭐ Seller Trust Agent (Implemented Engine + Planned LLM)
- Evaluate seller performance and defect trends
- Calculate dynamic compliance and trust scores (0-100 index)
- Automatically flag fraudulent or high-complaint merchant accounts

---

## 🏗️ Platform Architecture

```text
                    E-Shop Guardian AI

                      React 19 + Vite
                             │
                             ▼
                     React Router DOM v7
                             │
                             ▼
                      Supabase Backend
       ┌──────────────┬──────────────┬──────────────┐
       │              │              │              │
Authentication   PostgreSQL DB   Storage Buckets  Realtime Channels
       │              │              │              │
       └──────────────┴──────────────┴──────────────┘
                             │
                      Future Integration
                             │
                     OpenRouter / Gemini
                             │
                    AI Intelligence Layer
```

---

## 👥 User Roles & Access

| Role | Access Scope | Key Capabilities |
| :--- | :--- | :--- |
| **Customer** | `/customer/*` | Browse marketplace, purchase items, view orders, manage warranties, request returns |
| **Seller** | `/seller/*` | Product CRUD, live order processing, inventory expiry markdowns, seller trust index |
| **Admin** | `/admin/*` | Global analytics, user verification management, seller monitoring, AI fraud logs |

---

## ⚙️ Technology Stack

### Frontend
- **Framework**: React 19, Vite, TypeScript
- **Styling**: Tailwind CSS v4, Vanilla CSS Design System Tokens
- **Icons & UI**: Lucide Icons, Framer Motion
- **Charts**: Recharts
- **Routing**: React Router DOM

### Backend & Infrastructure
- **Authentication**: Supabase Auth (Email & Password with metadata role assignment)
- **Database**: Supabase PostgreSQL with Row Level Security (RLS) & `SECURITY DEFINER` helper functions
- **Realtime**: Supabase Realtime Channels (`products`, `orders`, `notifications`)
- **Storage**: Supabase Storage Buckets (`product-images`, `avatars`, `invoices`)

---

## 🗄️ Database Schema

- **`profiles`**: User profiles (`id`, `email`, `full_name`, `role`, `avatar_url`, `phone`, `city`, `state`, `address`, `dob`, `gender`)
- **`seller_profiles`**: Merchant shop details (`profile_id`, `shop_name`, `gst_number`, `verification_status`, `seller_trust_score`)
- **`products`**: Product listings (`seller_id`, `name`, `description`, `category`, `price`, `brand`, `image_url`, `stock`, `rating`, `expiry_date`, `status`)
- **`orders`**: Customer purchases (`buyer_id`, `product_id`, `seller_id`, `quantity`, `total_amount`, `order_date`, `order_status`, `warranty_status`, `return_status`)
- **`warranties`**: Digital warranties (`order_id`, `product_id`, `buyer_id`, `product_name`, `brand`, `invoice_no`, `purchase_date`, `duration_months`, `expiry_date`, `status`, `serial_no`, `days_remaining`, `timeline`)
- **`return_requests`**: Return filings (`order_id`, `buyer_id`, `customer_name`, `product_name`, `product_price`, `reason`, `request_date`, `status`, `risk_score`, `risk_level`, `ai_confidence`, `ai_recommendation`, `timeline`)
- **`notifications`**: System notifications (`user_id`, `title`, `description`, `type`, `is_read`, `role`)

---

## 🔒 Security & RLS

- **Role-Based Routing**: Protected layouts for `/customer`, `/seller`, `/admin`.
- **Row Level Security (RLS)**: PostgreSQL policies with `SECURITY DEFINER` functions (`is_admin()`, `is_seller()`) to avoid infinite recursion loops.
- **Foreign Key Disambiguation**: Explicit constraint embedding (`orders!seller_id`) for multi-relationship PostgREST joins.

---

## 💻 Local Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/sivaasp5228/E-Shop-Guardian-AI.git
cd E-Shop-Guardian-AI
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Setup Environment Variables
Create a `.env.local` file in the root directory:
```env
VITE_SUPABASE_URL=YOUR_SUPABASE_PROJECT_URL
VITE_SUPABASE_ANON_KEY=YOUR_SUPABASE_ANON_KEY
```

### 4. Database Initialization
Run the complete SQL schema provided in [`supabase/schema.sql`](supabase/schema.sql) in your Supabase SQL Editor.

### 5. Run Development Server
```bash
npm run dev
```

### 6. Build for Production
```bash
npm run build
```

---

## 🏆 Hackathon Details

- **Event**: Idea2Impact Offline Hackathon 2026
- **Theme**: AI for Industry & Public Impact
- **Project**: E-Shop Guardian AI

---

## 👨‍💻 Team

Built with ❤️ for the **Idea2Impact Hackathon 2026**.
