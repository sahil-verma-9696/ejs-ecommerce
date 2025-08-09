# 🛒 E-Commerce Project Roadmap (EJS + Node.js + MongoDB)

This roadmap progresses from basic functionality to advanced features, with each version introducing new capabilities.

---

## **Version 1.0 – Basic Storefront**
**Goal:** Build the core product listing and cart system.

### Features
- [ ] Basic project setup with Express.js and EJS templates
- [ ] MongoDB connection and Mongoose models
- [ ] Product model (name, description, price, image)
- [ ] Display all products on home page
- [ ] Product detail page
- [ ] Add to cart (session-based)
- [ ] View cart and remove items
- [ ] Static assets (CSS/JS/images)

**Tech Stack**
- **Backend:** Node.js + Express
- **Frontend:** EJS + CSS
- **Database:** MongoDB (Mongoose)
- **Session Management:** express-session

---

## **Version 2.0 – User Accounts**
**Goal:** Add authentication and order saving.

### Features
- [ ] User registration & login (bcrypt password hashing)
- [ ] MongoDB User model (name, email, password, address)
- [ ] Save cart items for logged-in users
- [ ] Checkout page (cash on delivery mode)
- [ ] Order model & order history for users
- [ ] Protect routes (only logged-in users can checkout)

**Tech Stack Additions**
- **Auth:** express-session + bcrypt
- **Flash Messages:** connect-flash for login/register feedback

---

## **Version 3.0 – Admin Dashboard**
**Goal:** Add admin panel for product & order management.

### Features
- [ ] Admin login
- [ ] CRUD for products (create, edit, delete)
- [ ] View orders and update status (Pending → Shipped → Delivered)
- [ ] Upload product images (multer)
- [ ] Dashboard with sales stats (basic)

**Tech Stack Additions**
- **File Upload:** multer
- **Admin UI:** EJS templates with bootstrap/admin theme

---

## **Version 4.0 – Payments & Search**
**Goal:** Enable online payments and improve product discovery.

### Features
- [ ] Payment gateway integration (Stripe / Razorpay)
- [ ] Search products by name
- [ ] Filter products by category, price
- [ ] Pagination for product listing
- [ ] Order email notifications (Nodemailer)

**Tech Stack Additions**
- **Payments:** Stripe/Razorpay API
- **Email:** Nodemailer

---

## **Version 5.0 – Performance & UX**
**Goal:** Improve performance, SEO, and user experience.

### Features
- [ ] Server-side rendering (SSR) optimization with EJS partials
- [ ] Lazy loading images
- [ ] Caching with Redis
- [ ] SEO-friendly URLs
- [ ] Wishlist functionality
- [ ] Recently viewed products
- [ ] Review & rating system

**Tech Stack Additions**
- **Cache:** Redis
- **SEO:** slugify for URLs

---

## **Version 6.0 – Advanced Features**
**Goal:** Turn into a fully-featured e-commerce platform.

### Features
- [ ] Multi-vendor support (different sellers can add products)
- [ ] Inventory management (stock tracking)
- [ ] Discount coupons & promo codes
- [ ] Address book for users
- [ ] Admin sales reports (charts)
- [ ] Real-time order status updates (Socket.IO)

**Tech Stack Additions**
- **Realtime:** Socket.IO
- **Charts:** Chart.js

---

## **Version 7.0 – Production Ready**
**Goal:** Make the app production-grade.

### Features
- [ ] Environment variables & config management
- [ ] Dockerize the application
- [ ] Logging with Winston/Morgan
- [ ] Security hardening (Helmet, CSRF protection)
- [ ] Deployment to cloud (Render/Heroku/VPS)

**Tech Stack Additions**
- **Security:** Helmet, csurf
- **Deployment:** Docker + cloud hosting

---

## 📌 Notes
- Always write clean, modular code.
- Use MVC architecture from the start.
- Maintain `.env` for sensitive credentials.
- Add unit & integration tests in later stages.

---

## 📄 Pages & Descriptions

Here’s the list of pages you’ll develop across all versions:

1. **Home Page**  
   Displays featured products, categories, and promotional banners.

2. **Product Listing Page**  
   Shows all products with pagination, filters, and sorting options.

3. **Product Detail Page**  
   Displays single product details, images, price, and "Add to Cart" button.

4. **Cart Page**  
   Shows items added to cart, quantity controls, and total price.

5. **Login Page**  
   User login form with email and password.

6. **Register Page**  
   User registration form with name, email, password, and address.

7. **Checkout Page**  
   Shows cart summary, delivery address form, and payment options.

8. **Order Confirmation Page**  
   Displays order details after successful checkout.

9. **User Profile Page**  
   Allows users to update their details and view past orders.

10. **Wishlist Page** *(V5.0+)*  
    Displays saved items for later purchase.

11. **Admin Login Page**  
    For admin authentication.

12. **Admin Dashboard**  
    Overview of sales, orders, and key stats.

13. **Admin Product Management Page**  
    Add, edit, or delete products (with image upload).

14. **Admin Orders Page**  
    View and update customer order statuses.

15. **Search Results Page** *(V4.0+)*  
    Displays products matching search queries.

16. **404 Page**  
    Friendly error page for invalid routes.

---

**Total Pages by Version:**
- **V1.0:** 4 pages (Home, Product Detail, Cart, 404)  
- **V2.0:** +4 pages (Login, Register, Checkout, Profile) → **8 total**  
- **V3.0:** +3 pages (Admin Login, Admin Dashboard, Admin Product Management) → **11 total**  
- **V4.0:** +2 pages (Search Results, Order Confirmation) → **13 total**  
- **V5.0:** +1 page (Wishlist) → **14 total**  
- **V6.0:** No new public-facing pages, but adds features  
- **V7.0:** No new pages, focuses on deployment & security


# 🛣 E-Commerce Routes (EJS + Node.js + MongoDB)

## Public Routes (Accessible without login)
| Page Name               | Route (GET)                  | Description |
|-------------------------|------------------------------|-------------|
| Home Page               | `/`                          | Displays featured products, categories, and banners. |
| Product Listing Page    | `/products`                  | Shows all products with pagination, filters, sorting. |
| Product Detail Page     | `/products/:id`               | Displays details of a single product. |
| Cart Page               | `/cart`                      | Shows cart items (session-based for guests). |
| Login Page              | `/login`                     | User login form. |
| Register Page           | `/register`                  | New user registration form. |
| Search Results Page*    | `/search?q=<term>`            | Shows products matching search query. *(V4.0+)* |
| 404 Page                | `*`                          | Displayed for all unknown routes. |

---

## Protected Routes – User (Login Required)
| Page Name               | Route (GET) / (POST)         | Description |
|-------------------------|------------------------------|-------------|
| Checkout Page           | `/checkout`                  | Shows order summary & payment options. |
| Order Confirmation Page | `/order/confirmation/:id`    | Shows order details after placing an order. |
| User Profile Page       | `/profile`                   | User details & past orders. |
| Wishlist Page*          | `/wishlist`                  | User's saved products list. *(V5.0+)* |

---

## Protected Routes – Admin (Admin Login Required)
| Page Name               | Route (GET) / (POST)         | Description |
|-------------------------|------------------------------|-------------|
| Admin Login Page        | `/admin/login`               | Admin authentication form. |
| Admin Dashboard         | `/admin`                     | Overview of sales, orders, stats. |
| Admin Product Mgmt      | `/admin/products`            | Manage products (CRUD). |
| Admin Add Product       | `/admin/products/new`        | Form to add a new product. |
| Admin Edit Product      | `/admin/products/edit/:id`   | Form to update a product. |
| Admin Orders Page       | `/admin/orders`              | View and update order statuses. |

---

## Access Rules
- **Public Routes** → No authentication required.  
- **Protected User Routes** → Require user to be logged in (middleware: `authUser`).  
- **Protected Admin Routes** → Require admin role (middleware: `authAdmin`).  

---

## Example Middleware
```js
// authUser.js
function authUser(req, res, next) {
    if (req.session.user) return next();
    res.redirect('/login');
}

// authAdmin.js
function authAdmin(req, res, next) {
    if (req.session.user && req.session.user.role === 'admin') return next();
    res.redirect('/admin/login');
}
```

# 📋 E-Commerce Project - Entities Documentation

This document provides a comprehensive overview of all database entities (MongoDB collections) used in the E-Commerce project, their attributes, constraints, and purposes.

---

## 🎯 Entity Overview

The project uses **6 main entities** that evolve across different versions:

1. **Product** - Core product information
2. **User** - Customer account management  
3. **Order** - Purchase transactions
4. **Cart** - Shopping cart items (for logged-in users)
5. **Category** - Product categorization *(implied in filters)*
6. **Review** - Product reviews and ratings *(V5.0+)*

---

## 📊 Entity Details

### 1. Product Entity
**Purpose:** Stores all product information including details, pricing, inventory, and media.

| Attribute | Data Type | Constraints | Description | Version |
|-----------|-----------|-------------|-------------|---------|
| `_id` | ObjectId | Primary Key, Auto-generated | Unique product identifier | V1.0+ |
| `name` | String | Required, Max 200 chars | Product name/title | V1.0+ |
| `description` | String | Required, Max 2000 chars | Detailed product description | V1.0+ |
| `price` | Number | Required, Min 0, Decimal(10,2) | Product price in currency | V1.0+ |
| `image` | String | Required, URL/Path format | Primary product image | V1.0+ |
| `images` | Array[String] | Optional, Max 10 images | Additional product images | V3.0+ |
| `category` | String | Required, Max 100 chars | Product category | V4.0+ |
| `stock` | Number | Required, Min 0, Integer | Available inventory count | V6.0+ |
| `sku` | String | Unique, Max 50 chars | Stock Keeping Unit | V6.0+ |
| `slug` | String | Unique, URL-friendly | SEO-friendly URL identifier | V5.0+ |
| `isActive` | Boolean | Default: true | Product availability status | V3.0+ |
| `vendorId` | ObjectId | Foreign Key (User), Optional | Multi-vendor support | V6.0+ |
| `createdAt` | Date | Auto-generated | Product creation timestamp | V1.0+ |
| `updatedAt` | Date | Auto-updated | Last modification timestamp | V1.0+ |

---

### 2. User Entity
**Purpose:** Manages customer accounts, authentication, and profile information.

| Attribute | Data Type | Constraints | Description | Version |
|-----------|-----------|-------------|-------------|---------|
| `_id` | ObjectId | Primary Key, Auto-generated | Unique user identifier | V2.0+ |
| `name` | String | Required, Max 100 chars | User's full name | V2.0+ |
| `email` | String | Required, Unique, Email format | User's email address | V2.0+ |
| `password` | String | Required, Min 8 chars, Hashed | Encrypted password (bcrypt) | V2.0+ |
| `phone` | String | Optional, Max 15 chars | Contact phone number | V2.0+ |
| `role` | String | Enum: ['customer', 'admin', 'vendor'] | User role/permissions | V2.0+ |
| `addresses` | Array[Object] | Optional, Max 5 addresses | Delivery addresses | V6.0+ |
| `addresses.street` | String | Required, Max 200 chars | Street address | V6.0+ |
| `addresses.city` | String | Required, Max 100 chars | City name | V6.0+ |
| `addresses.state` | String | Required, Max 100 chars | State/Province | V6.0+ |
| `addresses.zipCode` | String | Required, Max 10 chars | Postal/ZIP code | V6.0+ |
| `addresses.country` | String | Required, Max 100 chars | Country name | V6.0+ |
| `addresses.isDefault` | Boolean | Default: false | Default address flag | V6.0+ |
| `isActive` | Boolean | Default: true | Account status | V2.0+ |
| `emailVerified` | Boolean | Default: false | Email verification status | V7.0+ |
| `createdAt` | Date | Auto-generated | Account creation timestamp | V2.0+ |
| `updatedAt` | Date | Auto-updated | Last profile update timestamp | V2.0+ |

---

### 3. Order Entity
**Purpose:** Records purchase transactions, order details, and delivery tracking.

| Attribute | Data Type | Constraints | Description | Version |
|-----------|-----------|-------------|-------------|---------|
| `_id` | ObjectId | Primary Key, Auto-generated | Unique order identifier | V2.0+ |
| `userId` | ObjectId | Foreign Key (User), Required | Customer who placed order | V2.0+ |
| `orderNumber` | String | Unique, Auto-generated | Human-readable order number | V2.0+ |
| `items` | Array[Object] | Required, Min 1 item | Ordered products details | V2.0+ |
| `items.productId` | ObjectId | Foreign Key (Product) | Reference to product | V2.0+ |
| `items.name` | String | Required | Product name (snapshot) | V2.0+ |
| `items.price` | Number | Required, Min 0 | Product price at time of order | V2.0+ |
| `items.quantity` | Number | Required, Min 1 | Quantity ordered | V2.0+ |
| `items.image` | String | Required | Product image (snapshot) | V2.0+ |
| `totalAmount` | Number | Required, Min 0, Decimal(10,2) | Total order value | V2.0+ |
| `paymentMethod` | String | Enum: ['cod', 'stripe', 'razorpay'] | Payment method used | V2.0+ |
| `paymentStatus` | String | Enum: ['pending', 'paid', 'failed'] | Payment status | V4.0+ |
| `paymentId` | String | Optional | Payment gateway transaction ID | V4.0+ |
| `orderStatus` | String | Enum: ['pending', 'confirmed', 'shipped', 'delivered', 'cancelled'] | Order processing status | V2.0+ |
| `shippingAddress` | Object | Required | Delivery address | V2.0+ |
| `shippingAddress.street` | String | Required | Street address | V2.0+ |
| `shippingAddress.city` | String | Required | City name | V2.0+ |
| `shippingAddress.state` | String | Required | State/Province | V2.0+ |
| `shippingAddress.zipCode` | String | Required | Postal code | V2.0+ |
| `shippingAddress.country` | String | Required | Country | V2.0+ |
| `couponCode` | String | Optional | Applied discount coupon | V6.0+ |
| `discount` | Number | Default: 0, Min 0 | Discount amount | V6.0+ |
| `createdAt` | Date | Auto-generated | Order placement timestamp | V2.0+ |
| `updatedAt` | Date | Auto-updated | Last status update timestamp | V2.0+ |

---

### 4. Cart Entity
**Purpose:** Stores shopping cart items for logged-in users (persistent cart).

| Attribute | Data Type | Constraints | Description | Version |
|-----------|-----------|-------------|-------------|---------|
| `_id` | ObjectId | Primary Key, Auto-generated | Unique cart identifier | V2.0+ |
| `userId` | ObjectId | Foreign Key (User), Required | Cart owner | V2.0+ |
| `items` | Array[Object] | Optional, Max 50 items | Cart products | V2.0+ |
| `items.productId` | ObjectId | Foreign Key (Product) | Reference to product | V2.0+ |
| `items.quantity` | Number | Required, Min 1, Max 10 | Product quantity | V2.0+ |
| `items.addedAt` | Date | Auto-generated | Item addition timestamp | V2.0+ |
| `createdAt` | Date | Auto-generated | Cart creation timestamp | V2.0+ |
| `updatedAt` | Date | Auto-updated | Last cart modification | V2.0+ |

---

### 5. Category Entity
**Purpose:** Organizes products into hierarchical categories for better navigation.

| Attribute | Data Type | Constraints | Description | Version |
|-----------|-----------|-------------|-------------|---------|
| `_id` | ObjectId | Primary Key, Auto-generated | Unique category identifier | V4.0+ |
| `name` | String | Required, Unique, Max 100 chars | Category name | V4.0+ |
| `slug` | String | Required, Unique, URL-friendly | SEO-friendly identifier | V4.0+ |
| `description` | String | Optional, Max 500 chars | Category description | V4.0+ |
| `parentId` | ObjectId | Foreign Key (Category), Optional | Parent category (for hierarchy) | V4.0+ |
| `image` | String | Optional, URL/Path | Category image | V4.0+ |
| `isActive` | Boolean | Default: true | Category visibility | V4.0+ |
| `sortOrder` | Number | Default: 0 | Display order | V4.0+ |
| `createdAt` | Date | Auto-generated | Category creation timestamp | V4.0+ |
| `updatedAt` | Date | Auto-updated | Last modification timestamp | V4.0+ |

---

### 6. Review Entity
**Purpose:** Manages product reviews and ratings from customers.

| Attribute | Data Type | Constraints | Description | Version |
|-----------|-----------|-------------|-------------|---------|
| `_id` | ObjectId | Primary Key, Auto-generated | Unique review identifier | V5.0+ |
| `userId` | ObjectId | Foreign Key (User), Required | Review author | V5.0+ |
| `productId` | ObjectId | Foreign Key (Product), Required | Reviewed product | V5.0+ |
| `rating` | Number | Required, Min 1, Max 5, Integer | Star rating (1-5) | V5.0+ |
| `title` | String | Optional, Max 200 chars | Review title/summary | V5.0+ |
| `comment` | String | Required, Max 1000 chars | Review content | V5.0+ |
| `isVerifiedPurchase` | Boolean | Default: false | Verified buyer status | V5.0+ |
| `helpful` | Array[ObjectId] | Optional | Users who found review helpful | V5.0+ |
| `isApproved` | Boolean | Default: false | Admin moderation status | V5.0+ |
| `createdAt` | Date | Auto-generated | Review submission timestamp | V5.0+ |
| `updatedAt` | Date | Auto-updated | Last review modification | V5.0+ |

---

## 🔗 Entity Relationships

### One-to-Many Relationships
- **User → Orders** (One user can have many orders)
- **User → Cart** (One user has one cart with many items)
- **User → Reviews** (One user can write many reviews)
- **Product → Order Items** (One product can be in many orders)
- **Product → Cart Items** (One product can be in many carts)
- **Product → Reviews** (One product can have many reviews)
- **Category → Products** (One category can have many products)
- **Category → Subcategories** (Self-referencing for hierarchy)

### Many-to-Many Relationships
- **Products ↔ Categories** (A product can belong to multiple categories)
- **Users ↔ Products** (Wishlist - implemented as separate collection)

---

## 📋 Additional Collections

### Wishlist Entity (V5.0+)
| Attribute | Data Type | Constraints | Description |
|-----------|-----------|-------------|-------------|
| `userId` | ObjectId | Foreign Key (User), Required | Wishlist owner |
| `productId` | ObjectId | Foreign Key (Product), Required | Saved product |
| `addedAt` | Date | Auto-generated | Addition timestamp |

### Coupon Entity (V6.0+)
| Attribute | Data Type | Constraints | Description |
|-----------|-----------|-------------|-------------|
| `code` | String | Unique, Required, Max 20 chars | Coupon code |
| `discountType` | String | Enum: ['percentage', 'fixed'] | Discount type |
| `discountValue` | Number | Required, Min 0 | Discount amount |
| `minOrderAmount` | Number | Default: 0 | Minimum order value |
| `maxUses` | Number | Optional | Usage limit |
| `usedCount` | Number | Default: 0 | Times used |
| `isActive` | Boolean | Default: true | Coupon status |
| `expiresAt` | Date | Required | Expiration date |

---

## 🔒 Security Considerations

- **Password Storage:** All passwords are hashed using bcrypt (V2.0+)
- **Data Validation:** Mongoose schemas enforce all constraints
- **Authentication:** Session-based authentication with secure cookies
- **Authorization:** Role-based access control (customer/admin/vendor)
- **Input Sanitization:** All user inputs are sanitized and validated
- **CSRF Protection:** Implemented in V7.0
- **Rate Limiting:** API endpoints have rate limits (V7.0)

---

## 🚀 Performance Optimization

### Database Indexes (V7.0+)
- `Product.name` - Text index for search
- `Product.category` - Regular index for filtering
- `User.email` - Unique index for authentication
- `Order.userId` - Regular index for user orders
- `Order.orderNumber` - Unique index for lookups
- `Review.productId` - Regular index for product reviews

### Caching Strategy (V5.0+)
- Product listings cached in Redis
- Category data cached for navigation
- User sessions stored in Redis

---

*This documentation evolves with each project version and should be updated accordingly.*
