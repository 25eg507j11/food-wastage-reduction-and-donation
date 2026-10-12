# 🌱 Food Wastage Reduction & Donation Platform

A full-stack web application designed to connect surplus food donors (hotels, restaurants, event organizers, caterers, households) with verified NGOs, charities, and community shelters to fight hunger and reduce environmental waste.

---

## 📁 Project Structure (Single-Page Backend & Single-Page Frontend)

As requested, the entire project is neatly structured with **1 page for backend** and **1 page for frontend**:

```text
food-wastage-platform/
│
├── server.js          <-- 🟢 BACKEND (Single file: REST API, MySQL Pool, DB Auto-Migration)
│
├── public/
│   └── index.html     <-- 🎨 FRONTEND (Single file: Responsive UI, Tabs, Forms, Modals & JS)
│
├── database.sql       <-- 🗄️ MySQL Schema & Sample Initial Data (Tables & Seed data)
├── .env               <-- ⚙️ Environment Configuration (Database credentials & Port)
├── package.json       <-- 📦 Node.js dependencies (express, mysql2, cors, dotenv)
└── README.md          <-- 📖 Setup & Documentation Guide
```

---

## 🚀 Quick Start Guide (Run in 2 Steps)

### Step 1: Start the Backend Server
Open your terminal in this directory and run:
```bash
node server.js
```

### Step 2: Open the Application in your Browser
Open your browser and navigate to:
```
http://localhost:5000
```
The platform is immediately functional!

---

## 🗄️ MySQL Database Connection Setup

The server connects to MySQL automatically using the credentials defined in [`.env`](file:///C:/Users/Sindhu/.gemini/antigravity/scratch/food-wastage-platform/.env).

### 1. Configure `.env`
Open `.env` and enter your MySQL password (if you set one during MySQL installation):
```env
PORT=5000
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=your_mysql_password_here
DB_NAME=food_waste_db
```

### 2. Automatic Database & Table Creation
When `node server.js` starts with valid MySQL credentials, it will:
1. Automatically create the database `food_waste_db` if it doesn't already exist.
2. Automatically create the `users`, `donations`, and `claims` tables.
3. Automatically seed sample demo listings and donor/NGO accounts.

> **Manual SQL Import (Optional):**
> You can also import the provided [`database.sql`](file:///C:/Users/Sindhu/.gemini/antigravity/scratch/food-wastage-platform/database.sql) file directly using MySQL Workbench, phpMyAdmin, or MySQL CLI:
> ```bash
> mysql -u root -p < database.sql
> ```

---

## 🌟 Key Features & Workflow

1. **Surplus Food Donation (Donor Role)**:
   - Hotels, caterers, and supermarkets can post surplus food with title, category, quantity, dietary type (Veg, Non-Veg, Vegan), freshness/expiry window, pickup location, and special instructions.
2. **Food Claim & Distribution (NGO Role)**:
   - NGOs and community shelters can browse live food feeds, search/filter by category and location, and claim available items with estimated pickup time.
3. **Live Logistics & Tracking**:
   - Status transitions from `Available` ➔ `Claimed` ➔ `Picked Up` ➔ `Completed`.
4. **Real-time Impact Analytics**:
   - Live metrics calculating **Meals Rescued**, **Food Saved (Kg)**, and **CO₂ Emissions Prevented**.
5. **Instant Demo Role Switcher**:
   - Switch between **The Royal Grand Hotel (Donor)**, **Hope & Hunger Relief (NGO)**, and **Admin** with one click in the header.
