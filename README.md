# Finio — Finance Dashboard UI

A clean, interactive finance dashboard built for the Zorvyn Frontend Developer Intern assessment.

## 🚀 Setup & Running

No build step required. Just open the file in any modern browser:

```
open index.html
```

Or serve it locally:
```bash
npx serve .
# then visit http://localhost:3000
```

---

## 🧠 Approach & Decisions

### Tech Stack
- **React 18** (via CDN, no bundler needed) — chosen for component-based state management
- **Recharts** — for AreaChart, BarChart, and PieChart visualizations
- **Pure CSS** with CSS variables — no external UI library, full control over theming
- **Google Fonts (DM Serif Display + DM Sans)** — for a distinctive, professional aesthetic

### Design Direction
Dark-themed dashboard with a **refined financial aesthetic** — deep navy surfaces, neon-green accent (`#c8f04d`), and semantic colors for income (teal) and expenses (red). The goal was to feel like a real fintech product, not a generic dashboard.

---

## ✅ Core Features Implemented

### 1. Dashboard Overview
- **Summary cards**: Net Balance, Total Income, Total Expenses with MoM % change
- **Time-based visualization**: Balance Trend (Area chart over 5 months)
- **Categorical visualization**: Spending Breakdown (Pie chart + legend)
- **Income vs Expenses**: Bar chart showing monthly comparison

### 2. Transactions Section
- Full list with **Date, Amount, Category, Type** columns
- **Search** by description or category name
- **Filter buttons**: All / Income / Expense
- **Category filter** dropdown
- **Sort** by Date or Amount (ascending/descending)

### 3. Role-Based UI (RBAC — frontend simulated)
- **Role switcher** in sidebar (dropdown: Admin / Viewer)
- **Admin**: Can add new transactions + edit existing ones (Edit button visible, Add button visible)
- **Viewer**: Read-only mode — no Add/Edit buttons shown
- Role state is managed globally and affects UI across all tabs

### 4. Insights Section
- **Highest spending category** with color-coded display
- **Month-over-month expense change** percentage
- **Savings rate** calculation (% of income saved)
- **Category breakdown bars** showing relative spending
- **4 key observations** with actionable financial insights

### 5. State Management
- All state managed with React `useState` and `useMemo` hooks
- Global state: `transactions`, `role`, active tab, search query, filters, sort config
- `useMemo` used for derived stats, filtered list, and category breakdown — avoids unnecessary recalculation

### 6. UI/UX
- **Responsive**: Sidebar collapses to hamburger menu on mobile (<900px), cards reflow to single column on small screens
- **Empty state**: Shows a friendly message when no transactions match filters
- **Toast notifications**: Appear on add/edit/role switch actions
- **Graceful loading**: All data is mock static data — no async loading states needed

---

## ✨ Optional Enhancements Included
- **Animations**: Modal and toast slide-in animations via CSS keyframes
- **Micro-interactions**: Hover states on table rows, nav items, buttons
- **Custom scrollbar** styling
- **Smooth bar chart transitions**

---

## 📁 Project Structure

```
index.html        ← Entire app (React + CSS + JS in one file)
README.md         ← This file
```

Single-file approach was chosen for simplicity of submission and zero setup friction. In a production project, this would be split into component files with a proper Vite/CRA setup.

---

## 🔮 What I'd Add with More Time
- LocalStorage persistence for transactions
- Date range filter
- CSV export
- Animated number counters on the summary cards
- Dark/light mode toggle
