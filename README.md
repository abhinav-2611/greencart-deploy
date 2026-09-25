# 🥗 GreenCart – Food Delivery Web Application

GreenCart is a **full-stack food delivery web application** built using the **MERN Stack — MongoDB, Express.js, React.js, and Node.js**.

The application allows users to browse products, manage their cart, save delivery addresses, and place orders using **Cash on Delivery (COD) or Stripe**.

It also provides a **seller-side application** for product and stock management and viewing customer orders.

---

## 🚀 Live Demo

**Frontend:**
https://greencart-deploy-myiw.vercel.app

**Backend API:**
https://greencart-deploy-gules.vercel.app

---

## ✨ Features

### 👤 User Features

* User registration
* User login and logout
* User authentication
* Browse all products
* View product details
* Add and update cart
* Add delivery addresses
* View saved addresses
* Place Cash on Delivery orders
* Place Stripe orders
* View user's orders

### 🛍️ Seller Features

* Seller login and logout
* Seller authentication
* Add new products
* Upload multiple product images
* View product list
* View product details
* Update product stock
* View customer orders

### 💳 Payment

* Cash on Delivery (COD)
* Stripe payment integration
* Stripe webhook handling

### ☁️ Image Upload

* Multer for handling product image uploads
* Cloudinary for image storage

---

## 🧑‍💻 Tech Stack

| Category        | Technologies                       |
| --------------- | ---------------------------------- |
| Frontend        | React.js, JavaScript, HTML5, CSS3  |
| Build Tool      | Vite                               |
| Backend         | Node.js, Express.js                |
| Database        | MongoDB, Mongoose                  |
| Authentication  | Cookies, Authentication Middleware |
| Image Upload    | Multer                             |
| Image Storage   | Cloudinary                         |
| Payments        | Stripe                             |
| Deployment      | Vercel                             |
| Version Control | Git, GitHub                        |

---

## 🏗️ Application Architecture

```text
                    ┌──────────────────────┐
                    │    React Frontend    │
                    │       (Vite)         │
                    └──────────┬───────────┘
                               │
                         REST APIs
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Node.js + Express  │
                    │       Backend        │
                    └──────┬───────┬───────┘
                           │       │
              ┌────────────┘       └─────────────┐
              ▼                                  ▼
      ┌────────────────┐                 ┌──────────────┐
      │    MongoDB     │                 │  Cloudinary  │
      │   + Mongoose   │                 │    Images    │
      └────────────────┘                 └──────────────┘
                           │
                           ▼
                     ┌───────────┐
                     │  Stripe   │
                     │  Payment  │
                     └───────────┘
```

---

# 🔌 API Endpoints

The backend exposes REST APIs for authentication, products, cart, addresses, and orders.

## 👤 User APIs

| Method | Endpoint             | Description               |
| ------ | -------------------- | ------------------------- |
| POST   | `/api/user/register` | Register a new user       |
| POST   | `/api/user/login`    | Login user                |
| GET    | `/api/user/is-auth`  | Check user authentication |
| GET    | `/api/user/logout`   | Logout user               |

## 🛍️ Seller APIs

| Method | Endpoint              | Description                 |
| ------ | --------------------- | --------------------------- |
| POST   | `/api/seller/login`   | Seller login                |
| GET    | `/api/seller/is-auth` | Check seller authentication |
| GET    | `/api/seller/logout`  | Seller logout               |

## 🍔 Product APIs

| Method | Endpoint             | Description          |
| ------ | -------------------- | -------------------- |
| POST   | `/api/product/add`   | Add a new product    |
| GET    | `/api/product/list`  | Get all products     |
| GET    | `/api/product/id`    | Get product details  |
| POST   | `/api/product/stock` | Update product stock |

## 🛒 Cart APIs

| Method | Endpoint           | Description        |
| ------ | ------------------ | ------------------ |
| POST   | `/api/cart/update` | Update user's cart |

## 📍 Address APIs

| Method | Endpoint           | Description        |
| ------ | ------------------ | ------------------ |
| POST   | `/api/address/add` | Add user address   |
| GET    | `/api/address/get` | Get user addresses |

## 📦 Order APIs

| Method | Endpoint            | Description        |
| ------ | ------------------- | ------------------ |
| POST   | `/api/order/cod`    | Place COD order    |
| GET    | `/api/order/user`   | Get user's orders  |
| GET    | `/api/order/seller` | Get seller orders  |
| POST   | `/api/order/stripe` | Place Stripe order |

## 💳 Stripe Webhook

| Method | Endpoint  | Description                  |
| ------ | --------- | ---------------------------- |
| POST   | `/stripe` | Handle Stripe webhook events |

---

# 📁 Project Structure

```text
greencart/
│
├── client/                         # React frontend
│   ├── public/                     # Static assets
│   ├── src/                        # React source code
│   ├── .env                        # Frontend environment variables
│   ├── .gitignore
│   ├── eslint.config.js
│   ├── index.html
│   ├── package.json
│   ├── package-lock.json
│   ├── vercel.json
│   └── vite.config.js
│
├── server/                         # Node.js + Express backend
│   ├── configs/                    # Database & service configuration
│   ├── controllers/                # Application logic
│   ├── middlewares/                # Authentication middleware
│   ├── models/                     # MongoDB/Mongoose models
│   ├── routes/                     # API routes
│   ├── .env                        # Backend environment variables
│   ├── package.json
│   ├── package-lock.json
│   ├── server.js                   # Backend entry point
│   └── vercel.json
│
└── README.md
```

---

# 🗄️ Database

GreenCart uses **MongoDB** with **Mongoose** for database operations.

The backend contains models for the application's core data such as:

* Users
* Products
* Addresses
* Orders

---

# ⚙️ Installation & Setup

## 1. Clone the Repository

```bash
git clone <your-github-repository-url>
cd greencart
```

## 2. Install Frontend Dependencies

```bash
cd client
npm install
```

## 3. Install Backend Dependencies

Open another terminal:

```bash
cd server
npm install
```

---

# 🔐 Environment Variables

Create `.env` files inside the `client` and `server` directories.

Use the **same variable names as defined in your actual project configuration**.

Example:

```env
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
PORT=4000
```

Add your Cloudinary and Stripe credentials according to your project configuration.

> Never commit real credentials, passwords, API keys, or secrets to GitHub.

---

# ▶️ Run the Project Locally

### Start Backend

From the `server` directory:

```bash
npm run server
```

Backend:

```text
http://localhost:4000
```

### Start Frontend

From the `client` directory:

```bash
npm run dev
```

Frontend:

```text
http://localhost:5173
```

---

# 🌐 Deployment

GreenCart is deployed using **Vercel**.

### Frontend

```text
https://greencart-deploy-myiw.vercel.app
```

### Backend

```text
https://greencart-deploy-gules.vercel.app
```

Example API request:

```text
https://greencart-deploy-gules.vercel.app/api/product/list
```

---

# 🧠 What I Learned

Through this project, I gained practical experience in:

* Building a full-stack MERN application
* Developing REST APIs with Express.js
* Connecting React with a Node.js backend
* Working with MongoDB and Mongoose
* Implementing user and seller authentication
* Creating protected backend routes
* Performing database CRUD operations
* Managing shopping cart functionality
* Managing delivery addresses
* Implementing order placement
* Integrating Stripe payments
* Handling Stripe webhooks
* Uploading images using Multer
* Storing images using Cloudinary
* Using environment variables
* Deploying a full-stack application using Vercel

---

# 👨‍💻 Author

**Abhinav Srivastava**

MCA Graduate | Full-Stack Developer

* GitHub: https://github.com/abhinav-2611
* LinkedIn: https://www.linkedin.com/in/abhinav-srivastava-264641437/

---

## ⭐ Support

If you found this project useful, consider giving the repository a ⭐.

**Built with ❤️ using the MERN Stack.**
