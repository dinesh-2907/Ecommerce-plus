🛡️ E-Shop Guardian AI

AI-Powered Trust & Intelligence Platform for E-Commerce

E-Shop Guardian AI is a smart e-commerce management platform designed to improve trust, reduce return fraud, manage product warranties, monitor sellers, and provide useful business insights.

The platform connects customers, sellers, and administrators in one system with real-time order management, warranty tracking, return intelligence, inventory monitoring, and seller trust management.

🚀 Features
👤 Customer

Secure login and registration

Browse available products

View product details and prices

Place orders

Track order status

View order history

Digital warranty management

Track warranty expiry

Submit warranty claims

Request product returns

Return risk analysis

Real-time notifications

Manage profile and account settings

🏪 Seller

Seller dashboard

Add, edit, and manage products

Manage product stock

Manage product expiry dates

View customer orders

Update order status

Dispatch and deliver orders

Monitor sales and revenue

Track inventory health

Manage discounts for products nearing expiry

View seller trust score

Manage seller profile

🛡️ Admin

Platform dashboard

Monitor users

Manage customers and sellers

Verify seller accounts

Manage seller status

Monitor trust scores

View return and fraud risk information

Monitor platform activity

View system insights

🤖 AI Features

The platform includes rule-based intelligence and is designed for future AI/LLM integration.

Return Intelligence

Analyze return requests

Calculate return risk scores

Identify potentially suspicious returns

Classify returns as Low, Medium, or High Risk

Provide recommendations for return processing

Smart Pricing

Monitor product expiry dates

Identify products nearing expiry

Recommend discounts

Help reduce inventory waste

Improve potential revenue recovery

Seller Trust

Monitor seller performance

Calculate seller trust scores

Track complaints and defects

Identify sellers requiring additional verification

Warranty Guardian

Planned AI capabilities include:

Explain warranty coverage

Send warranty expiry reminders

Analyze warranty documents

Assist with warranty claims

🏗️ Architecture
                E-Shop Guardian AI

                       React
                        │
                        ▼
                  React Router
                        │
                        ▼
                    Supabase
        ┌───────────────┼───────────────┐
        │               │               │
   Authentication   PostgreSQL       Storage
        │               │               │
        └───────────────┼───────────────┘
                        │
                     Realtime
                        │
                        ▼
                  AI Intelligence

🛠️ Technology Stack
Frontend

React

TypeScript

Vite

Tailwind CSS

React Router

Framer Motion

Lucide Icons

Recharts

Backend

Supabase

PostgreSQL

Supabase Authentication

Supabase Storage

Supabase Realtime

Row Level Security (RLS)

👥 User Roles
Role	Main Access
Customer	Products, orders, returns, warranties, profile
Seller	Products, inventory, orders, sales, seller trust
Admin	Users, sellers, analytics, trust and risk monitoring
🗄️ Main Database Tables
Profiles

Stores customer, seller, and admin profile information.

Seller Profiles

Stores seller business details, verification status, and trust score.

Products

Stores product information such as:

Product name

Description

Price

Category

Brand

Stock

Image

Expiry date

Status

Orders

Stores customer purchases and order status.

Warranties

Stores digital warranty information including:

Product

Purchase date

Warranty duration

Expiry date

Serial number

Warranty status

Return Requests

Stores return requests and risk analysis.

Notifications

Stores real-time notifications for users.

🔒 Security

The platform uses:

Supabase Authentication

PostgreSQL Row Level Security

Role-based access

Protected routes

Secure database policies

SECURITY DEFINER helper functions

Customers, sellers, and administrators only have access to the data and features permitted for their roles.

💻 Getting Started
1. Clone the Repository
git clone https://github.com/dinesh-2907/Ecommerce-plus.git
cd Ecommerce-plus

2. Install Dependencies
npm install

3. Configure Environment Variables

Create a .env.local file:

VITE_SUPABASE_URL=YOUR_SUPABASE_PROJECT_URL
VITE_SUPABASE_ANON_KEY=YOUR_SUPABASE_ANON_KEY


Replace the values with your Supabase project credentials.

4. Setup Database

Run the SQL schema from:

supabase/schema.sql


in the Supabase SQL Editor.

5. Start the Project
npm run dev

6. Build for Production
npm run build

📁 Project Structure
Ecommerce-plus/
│
├── src/
│   ├── components/
│   ├── pages/
│   ├── layouts/
│   ├── services/
│   └── ...
│
├── supabase/
│   └── schema.sql
│
├── public/
├── package.json
└── README.md

🎯 Project Goal

E-Shop Guardian AI aims to make e-commerce platforms more secure, transparent, and efficient by combining traditional marketplace functionality with intelligent automation.

The main goals are:

Reduce return fraud

Improve seller trust

Simplify warranty management

Reduce inventory waste

Improve order management

Provide useful business insights

Create a better experience for customers and sellers

