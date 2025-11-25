# 🌿 Organic Store - E-Commerce Platform

A full-stack e-commerce application for organic products with a modern React frontend and Express.js backend. This project features product browsing, user authentication, shopping cart management, wishlist functionality, and secure Stripe payment integration.

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation & Setup](#installation--setup)
- [Running the Application](#running-the-application)
- [Environment Variables](#environment-variables)
- [API Documentation](#api-documentation)
- [Project Architecture](#project-architecture)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Project Overview

Organic Store is a comprehensive e-commerce platform designed for selling organic products. The application consists of two main parts:

1. **Frontend (organic/)** - React-based user interface with Redux state management
2. **Backend (organic-api/)** - Express.js REST API with MongoDB database

The platform provides customers with an intuitive shopping experience, including product discovery, user authentication, shopping cart management, and secure checkout with Stripe integration.

## ✨ Features

### Customer Features
- **Product Browsing** - Browse all products with detailed information
- **Category Filtering** - Filter products by category
- **Product Search** - Find products easily
- **Shopping Cart** - Add/remove products, manage quantities
- **Wishlist** - Save favorite products for later
- **User Authentication** - Secure login and registration
- **Checkout Process** - Multi-step checkout experience
- **Stripe Payment Integration** - Secure payment processing
- **Order History** - View past orders and confirmations
- **Responsive Design** - Mobile-friendly UI with Material-UI

### Admin Features
- **Product Management** - Add, edit, and delete products
- **Admin Dashboard** - Comprehensive admin panel
- **Order Management** - View and manage orders

## 🛠 Tech Stack

### Frontend
- **React 18.2** - UI library
- **Vite** - Build tool and dev server
- **Redux Toolkit** - State management
- **React Router v6** - Routing
- **Material-UI (MUI)** - UI component library
- **Axios** - HTTP client
- **React Toastify** - Notifications
- **React Icons** - Icon library
- **React Share** - Social sharing
- **Yup** - Form validation
- **country-state-city** - Location data

### Backend
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB ODM
- **Stripe** - Payment processing
- **JWT** - Authentication tokens
- **bcryptjs** - Password hashing
- **CORS** - Cross-origin requests
- **dotenv** - Environment variables

## 📁 Project Structure

```
organic-store/
├── organic/                          # Frontend (React + Vite)
│   ├── src/
│   │   ├── components/               # Reusable React components
│   │   │   ├── Banner/
│   │   │   ├── Button/
│   │   │   ├── Footer/
│   │   │   ├── Header/
│   │   │   ├── HomeLayout/
│   │   │   ├── ProductCard/
│   │   │   ├── ProductList/
│   │   │   └── ProductListByCategory/
│   │   ├── pages/                    # Page components
│   │   │   ├── AboutPage.jsx
│   │   │   ├── CartPage.jsx
│   │   │   ├── CheckoutPage.jsx
│   │   │   ├── ContactPage.jsx
│   │   │   ├── HomePage.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── SingleProduct.jsx
│   │   │   ├── SuccessPage.jsx
│   │   │   ├── WishListPage.jsx
│   │   │   ├── Dashboard/            # Admin dashboard
│   │   │   │   └── AdminPanels/
│   │   │   └── NotFound/
│   │   ├── slices/                   # Redux slices
│   │   │   ├── cartSlice.js
│   │   │   ├── productSlice.js
│   │   │   ├── singleProduct.js
│   │   │   ├── userSlice.js
│   │   │   └── wishListSlice.js
│   │   ├── utils/                    # Utility functions
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   ├── store.js                  # Redux store configuration
│   │   ├── theme.js                  # MUI theme configuration
│   │   └── assets/
│   ├── package.json
│   ├── vite.config.js
│   └── index.html
│
├── organic-api/                      # Backend (Express + MongoDB)
│   ├── controller/                   # Route controllers
│   │   ├── cartController.js
│   │   ├── orderController.js
│   │   ├── productController.js
│   │   ├── userController.js
│   │   └── wishlistController.js
│   ├── models/                       # Mongoose models
│   │   ├── cartModel.js
│   │   ├── orderModel.js
│   │   ├── productModel.js
│   │   ├── userModel.js
│   │   └── wishListModel.js
│   ├── routes/                       # API routes
│   │   ├── cartRoutes.js
│   │   ├── OrderRoutes.js
│   │   ├── productRoute.js
│   │   ├── stripeRoutes.js
│   │   ├── userRoutes.js
│   │   └── wishListRoutes.js
│   ├── middlewares/                  # Custom middleware
│   │   └── authMiddleware.js
│   ├── index.js                      # Entry point
│   ├── data.js                       # Sample data
│   ├── seed.js                       # Database seeding
│   ├── package.json
│   └── readme.md
│
└── README.md                         # This file
```

## 📦 Prerequisites

Before running the application, ensure you have the following installed:

- **Node.js** (v14 or higher)
- **npm** or **yarn** package manager
- **MongoDB** (local or cloud - MongoDB Atlas recommended)
- **Git** (for version control)

## 🚀 Installation & Setup

### 1. Clone the Repository

```bash
git clone <repository-url>
cd org
```

### 2. Setup Frontend

Navigate to the frontend directory and install dependencies:

```bash
cd organic
npm install
```

### 3. Setup Backend

Navigate to the backend directory and install dependencies:

```bash
cd ../organic-api
npm install
```

### 4. Configure Environment Variables

Create a `.env` file in the `organic-api/` directory with the following variables:

```env
# Database
MONGO_URI=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/<database>

# JWT
JWT_SECRET=your_super_secret_jwt_key_here

# Stripe
SECRET_KEY=sk_test_your_stripe_secret_key_here

# Server
PORT=8080
NODE_ENV=development
```

Create a `.env` (if needed) in the `organic/` directory:

```env
VITE_API_URL=http://localhost:8080/api/v1
```

## 🎮 Running the Application

### Option 1: Run Both Services Simultaneously (Recommended)

#### Terminal 1 - Backend:
```bash
cd organic-api
npm run dev
```

The API server will start on `http://localhost:8080`

#### Terminal 2 - Frontend:
```bash
cd organic
npm run dev
```

The React development server will start on `http://localhost:5173`

### Option 2: Build for Production

#### Build Frontend:
```bash
cd organic
npm run build
npm run preview
```

#### Build Backend:
```bash
cd organic-api
npm start
```

### Available Scripts

**Frontend (organic/)**
```bash
npm run dev      # Start development server
npm run build    # Build for production
npm run preview  # Preview production build
npm run lint     # Run ESLint
```

**Backend (organic-api/)**
```bash
npm run dev      # Start with nodemon (auto-reload)
npm start        # Start production server
npm test         # Run tests
```

## 🔧 Environment Variables

### Backend (.env in organic-api/)

| Variable | Description | Example |
|----------|-------------|---------|
| `MONGO_URI` | MongoDB connection string | `mongodb+srv://user:pass@cluster.mongodb.net/db` |
| `JWT_SECRET` | Secret key for JWT tokens | `your_secret_key` |
| `SECRET_KEY` | Stripe secret key | `sk_test_...` |
| `PORT` | Server port | `8080` |
| `NODE_ENV` | Environment mode | `development` or `production` |

### Frontend (.env in organic/)

| Variable | Description | Example |
|----------|-------------|---------|
| `VITE_API_URL` | API base URL | `http://localhost:8080/api/v1` |

## 📡 API Documentation

### Base URL
```
http://localhost:8080/api/v1
```

### Endpoints Overview

#### Products
```
GET    /products              # Get all products
POST   /products              # Create product (admin)
GET    /products/:id          # Get product by ID
DELETE /products/:id          # Delete product (admin)
```

#### Users
```
POST   /user/register         # Register new user
POST   /user/login            # Login user
GET    /user/profile          # Get user profile
```

#### Cart
```
GET    /cart                  # Get user's cart
POST   /cart                  # Add to cart
PUT    /cart/:id              # Update cart item
DELETE /cart/:id              # Remove from cart
```

#### Wishlist
```
GET    /wishlist              # Get user's wishlist
POST   /wishlist              # Add to wishlist
DELETE /wishlist/:id          # Remove from wishlist
```

#### Orders
```
POST   /order                 # Create order
GET    /order                 # Get user's orders
GET    /order/:id             # Get order details
```

#### Stripe
```
POST   /stripe/checkout       # Create payment session
```

## 🏗 Project Architecture

### Frontend Architecture

The frontend follows a component-based architecture with Redux for state management:

```
App (Root)
├── Redux Store (Slices)
│   ├── cartSlice
│   ├── productSlice
│   ├── userSlice
│   ├── wishListSlice
│   └── singleProduct
├── Routes
│   ├── HomePage
│   ├── ProductList
│   ├── CartPage
│   ├── CheckoutPage
│   ├── Dashboard (Admin)
│   └── Other Pages
└── Components
    ├── Header
    ├── Footer
    ├── ProductCard
    └── Various UI Components
```

### Backend Architecture

The backend follows an MVC pattern with controllers, routes, and models:

```
Express App
├── Routes
│   ├── /products
│   ├── /users
│   ├── /cart
│   ├── /wishlist
│   ├── /orders
│   └── /stripe
├── Controllers (Business Logic)
├── Models (Database Schema)
├── Middlewares (Auth, etc)
└── Database (MongoDB)
```

## 🔐 Authentication Flow

1. User registers with email and password
2. Password is hashed using bcryptjs
3. User logs in, receives JWT token
4. Token is stored in Redux state
5. Token sent with requests in Authorization header
6. authMiddleware verifies token on protected routes

## 💳 Payment Integration

- **Stripe** is integrated for secure payment processing
- Payment session created on checkout
- Stripe webhook handling for payment confirmation
- Order creation on successful payment

## 🐛 Troubleshooting

### Port Already in Use
```bash
# Change port in backend or kill process
lsof -i :8080
kill -9 <PID>
```

### MongoDB Connection Issues
- Verify MongoDB is running
- Check connection string in `.env`
- Ensure IP is whitelisted (if using MongoDB Atlas)

### CORS Errors
- Ensure backend is running on correct port
- Verify API URL in frontend `.env`
- Check CORS configuration in `index.js`

## 📝 Database Seeding

To populate the database with sample data:

```bash
cd organic-api
node seed.js
```

## 🤝 Contributing

1. Create a feature branch: `git checkout -b feature/YourFeature`
2. Commit changes: `git commit -m 'Add YourFeature'`
3. Push to branch: `git push origin feature/YourFeature`
4. Submit a Pull Request

## 📄 License

This project is licensed under the ISC License - see the LICENSE file for details.

---

**Last Updated:** November 25, 2025

For issues or questions, please create an issue in the repository.
