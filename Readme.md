# Fullstack E-Commerce DevOps Project

This is a **monorepo** project containing three main services:  

1. **Backend API** – Handles authentication, products, orders, and admin functionality.  
2. **Frontend Storefront** – Customer-facing e-commerce site.  
3. **Admin Dashboard** – Admin panel to manage products, orders, and users.  

---

## 1. Prerequisites

- Node.js (v18 or above recommended)  
- npm (v9 or above recommended)  
- Basic knowledge of terminal commands  
- API keys for third-party services: GEMINI, Cloudinary, Stripe, Gmail SMTP  

---

## 2. Project Structure

```text

fullstack-ecom-devops % tree
.
├── Readme.md
├── backend
│   ├── app.js
│   ├── config
│   │   └── config.env
│   ├── controllers
│   │   ├── adminController.js
│   │   ├── authController.js
│   │   ├── orderController.js
│   │   └── productController.js
│   ├── database
│   │   └── db.js
│   ├── middlewares
│   │   ├── authMiddleware.js
│   │   ├── catchAsyncError.js
│   │   └── errorMiddleware.js
│   ├── models
│   │   ├── orderItemsTable.js
│   │   ├── ordersTable.js
│   │   ├── paymentsTable.js
│   │   ├── productReviewsTable.js
│   │   ├── productTable.js
│   │   ├── shippinginfoTable.js
│   │   └── userTable.js
│   ├── package-lock.json
│   ├── package.json
│   ├── router
│   │   ├── adminRoutes.js
│   │   ├── authRoutes.js
│   │   ├── orderRoutes.js
│   │   └── productRoutes.js
│   ├── server.js
│   └── utils
│       ├── createTables.js
│       ├── generateForgotPasswordEmailTemplate.js
│       ├── generatePaymentIntent.js
│       ├── generateResetPasswordToken.js
│       ├── getAIRecommendation.js
│       ├── jwtToken.js
│       └── sendEmail.js
├── dashboard
│   ├── README.md
│   ├── eslint.config.js
│   ├── index.html
│   ├── package-lock.json
│   ├── package.json
│   ├── postcss.config.js
│   ├── public
│   │   └── vite.svg
│   ├── src
│   │   ├── App.jsx
│   │   ├── assets
│   │   │   ├── avatar.jpg
│   │   │   ├── laptop.webp
│   │   │   ├── pic.webp
│   │   │   └── react.svg
│   │   ├── components
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Header.jsx
│   │   │   ├── Orders.jsx
│   │   │   ├── Products.jsx
│   │   │   ├── Profile.jsx
│   │   │   ├── SideBar.jsx
│   │   │   ├── Users.jsx
│   │   │   └── dashboard-components
│   │   │       ├── MiniSummary.jsx
│   │   │       ├── MonthlySalesChart.jsx
│   │   │       ├── OrdersChart.jsx
│   │   │       ├── Stats.jsx
│   │   │       ├── TopProductsChart.jsx
│   │   │       └── TopSellingProducts.jsx
│   │   ├── index.css
│   │   ├── lib
│   │   │   └── helper.js
│   │   ├── main.jsx
│   │   ├── modals
│   │   │   ├── CreateProductModal.jsx
│   │   │   ├── UpdateProductModal.jsx
│   │   │   └── ViewProductModal.jsx
│   │   ├── pages
│   │   │   ├── ForgotPassword.jsx
│   │   │   ├── Login.jsx
│   │   │   └── ResetPassword.jsx
│   │   └── store
│   │       ├── slices
│   │       │   ├── adminSlice.js
│   │       │   ├── authSlice.js
│   │       │   ├── extraSlice.js
│   │       │   ├── orderSlice.js
│   │       │   └── productsSlice.js
│   │       └── store.js
│   ├── tailwind.config.js
│   └── vite.config.js
└── frontend
    ├── README.md
    ├── eslint.config.js
    ├── index.html
    ├── package-lock.json
    ├── package.json
    ├── postcss.config.js
    ├── public
    │   ├── avatar-holder.avif
    │   ├── electronics.jpg
    │   ├── fashion.jpg
    │   ├── furniture.jpg
    │   └── vite.svg
    ├── src
    │   ├── App.css
    │   ├── App.jsx
    │   ├── assets
    │   │   └── react.svg
    │   ├── components
    │   │   ├── Home
    │   │   │   ├── CategoryGrid.jsx
    │   │   │   ├── FeatureSection.jsx
    │   │   │   ├── HeroSlider.jsx
    │   │   │   ├── NewsletterSection.jsx
    │   │   │   └── ProductSlider.jsx
    │   │   ├── Layout
    │   │   │   ├── CartSidebar.jsx
    │   │   │   ├── Footer.jsx
    │   │   │   ├── LoginModal.jsx
    │   │   │   ├── Navbar.jsx
    │   │   │   ├── ProfilePanel.jsx
    │   │   │   ├── SearchOverlay.jsx
    │   │   │   └── Sidebar.jsx
    │   │   ├── PaymentForm.jsx
    │   │   └── Products
    │   │       ├── AISearchModal.jsx
    │   │       ├── Pagination.jsx
    │   │       ├── ProductCard.jsx
    │   │       └── ReviewsContainer.jsx
    │   ├── contexts
    │   │   └── ThemeContext.jsx
    │   ├── data
    │   │   └── products.js
    │   ├── index.css
    │   ├── lib
    │   │   └── axios.js
    │   ├── main.jsx
    │   ├── pages
    │   │   ├── About.jsx
    │   │   ├── Cart.jsx
    │   │   ├── Contact.jsx
    │   │   ├── FAQ.jsx
    │   │   ├── Home.jsx
    │   │   ├── NotFound.jsx
    │   │   ├── Orders.jsx
    │   │   ├── Payment.jsx
    │   │   ├── ProductDetail.jsx
    │   │   └── Products.jsx
    │   └── store
    │       ├── slices
    │       │   ├── authSlice.js
    │       │   ├── cartSlice.js
    │       │   ├── orderSlice.js
    │       │   ├── popupSlice.js
    │       │   └── productSlice.js
    │       └── store.js
    ├── tailwind.config.js
    └── vite.config.js
```
---

## 3. Setup & Installation

Clone the repository and navigate to the project root:

```bash
git clone https://github.com/Aadi-Sonwane/fullstack-ecom-devops.git
cd fullstack-ecom-devops
```

### 3.1 Install Dependencies

Install dependencies for each service:

```bash
# Backend dependencies
cd backend
npm install

# Frontend dependencies
cd ../frontend
npm install

# Dashboard dependencies
cd ../dashboard
npm install
cd ..
```

## 4. Configuration
### 4.1 Backend (`backend/config/config.env`)

Create the `config.env` file in ``backend/config:``

```bash
# Server
PORT=5000
FRONTEND_URL=http://localhost:5173
DASHBOARD_URL=http://localhost:5174

# Auth & Security
JWT_SECRET_KEY=PASTE_YOUR_JWT_SECRET_KEY
JWT_EXPIRES_IN=7d
COOKIE_EXPIRES_IN=7d

# Email Service
SMTP_SERVICE=gmail
SMTP_MAIL=PASTE_YOUR_EMAIL
SMTP_PASSWORD=PASTE_YOUR_EMAIL_APP_PASSWORD
SMTP_HOST=smtp.gmail.com
SMTP_PORT=465

# Third-Party Services
GEMINI_API_KEY=PASTE_YOUR_GEMINI_API_KEY
CLOUDINARY_CLIENT_NAME=PASTE_YOUR_CLOUDINARY_CLOUD_NAME
CLOUDINARY_CLIENT_API=PASTE_YOUR_CLOUDINARY_CLIENT_API
CLOUDINARY_CLIENT_SECRET=PASTE_YOUR_CLOUDINARY_SECRET_KEY

# Stripe Payment Gateway
STRIPE_SECRET_KEY=PASTE_YOUR_STRIPE_SECRET_KEY
STRIPE_WEBHOOK_SECRET=PASTE_YOUR_STRIPE_WEBHOOK_SECRET
STRIPE_FRONTEND_KEY=PASTE_YOUR_STRIPE_PUBLIC_KEY
```

### 4.2 Frontend
- No additional configuration required.

- Uses backend API URL http://localhost:5000 by default.

- Runs on port 5173.

### 4.3 Dashboard

- No additional configuration required.

- Uses backend API URL http://localhost:5000 by default.

- Runs on port 5174.


## 5. Running the Applications
* Open three separate terminal windows: 

### 5.1 Backend API
```bash
cd backend
npm run dev
```
URL: http://localhost:5000

### 5.2 Frontend Storefront
```bash
cd frontend
npm run dev
```
URL: http://localhost:5173
### 5.3 Admin Dashboard
```bash
cd dashboard
npm run dev     
```
URL: http://localhost:5174

---
## 6 Summary of URLs

| Service            | URL                      | Port  |
|--------------------|--------------------------|-------|
| Backend API        | http://localhost:5000    | 5000  |
| Frontend Storefront| http://localhost:5173    | 5173  |
| Admin Dashboard    | http://localhost:5174    | 5174  |

---

## 7. Additional Notes
- Make sure all services are running concurrently for the frontend and dashboard to function properly.

- Replace all API keys and credentials in `config.env` before running the backend.

- You can customize frontend and dashboard ports in their respective `vite.config.js` files if needed.


---

