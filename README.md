# E-Commerce Full-Stack Boilerplate

A complete full-stack e-commerce application built with React, Node.js, Express, and MongoDB. This boilerplate provides a solid foundation for building modern e-commerce applications with all essential features.

##  Features

### Frontend (React)
- **Modern UI/UX** with Tailwind CSS
- **Responsive Design** for all devices
- **Authentication System** (Login/Register)
- **Product Catalog** with search and filtering
- **Shopping Cart** functionality
- **User Profile** management
- **Order History** tracking
- **Admin Dashboard** for product management
- **Real-time Updates** with React Query

### Backend (Node.js/Express)
- **RESTful API** with Express.js
- **JWT Authentication** with bcrypt password hashing
- **MongoDB Database** with Mongoose ODM
- **Product Management** (CRUD operations)
- **User Management** with role-based access
- **Order Processing** system
- **Category Management**
- **File Upload** support
- **Input Validation** with express-validator
- **Error Handling** middleware

### Database Models
- **User** - Authentication and profile data
- **Product** - Product information with images and reviews
- **Category** - Product categorization
- **Order** - Order processing and tracking

## 🛠️ Tech Stack

### Frontend
- React 18
- React Router DOM
- React Query (TanStack Query)
- React Hook Form
- Tailwind CSS
- Lucide React (Icons)
- Axios
- React Hot Toast

### Backend
- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT (jsonwebtoken)
- bcryptjs
- express-validator
- multer (file uploads)
- cors
- dotenv

##  Installation

### Prerequisites
- Node.js (v16 or higher)
- MongoDB (local or cloud)
- npm or yarn

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd ecommerce-boilerplate
   ```

2. **Install dependencies**
   ```bash
   npm run install-all
   ```

3. **Environment Setup**
   
   Create a `.env` file in the `server` directory:
   ```bash
   cp server/env.example server/.env
   ```
   
   Update the `.env` file with your configuration:
   ```env
   # Database
   MONGODB_URI=mongodb://localhost:27017/ecommerce
   
   # JWT Secret
   JWT_SECRET=your-super-secret-jwt-key-here
   
   # Server Port
   PORT=5000
   
   # Stripe (for payments)
   STRIPE_SECRET_KEY=sk_test_your_stripe_secret_key
   STRIPE_PUBLISHABLE_KEY=pk_test_your_stripe_publishable_key
   
   # Email (for notifications)
   EMAIL_HOST=smtp.gmail.com
   EMAIL_PORT=587
   EMAIL_USER=your-email@gmail.com
   EMAIL_PASS=your-app-password
   
   # Frontend URL
   CLIENT_URL=http://localhost:3000
   ```

4. **Start MongoDB**
   ```bash
   # If using local MongoDB
   mongod
   
   # Or use MongoDB Atlas (cloud)
   # Update MONGODB_URI in .env file
   ```

5. **Run the application**
   ```bash
   # Development mode (runs both frontend and backend)
   npm run dev
   
   # Or run separately:
   # Backend only
   npm run server
   
   # Frontend only
   npm run client
   ```

6. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000

##  Project Structure

```
ecommerce-boilerplate/
├── client/                 # React frontend
│   ├── public/
│   ├── src/
│   │   ├── components/     # Reusable components
│   │   │   ├── auth/       # Authentication components
│   │   │   ├── layout/     # Layout components
│   │   │   └── products/   # Product-related components
│   │   ├── contexts/       # React contexts
│   │   ├── pages/          # Page components
│   │   │   └── admin/      # Admin pages
│   │   ├── App.js
│   │   └── index.js
│   ├── package.json
│   └── tailwind.config.js
├── server/                 # Node.js backend
│   ├── models/            # Database models
│   ├── routes/            # API routes
│   ├── middleware/        # Custom middleware
│   ├── index.js           # Server entry point
│   └── package.json
├── package.json           # Root package.json
└── README.md
```

##  API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user
- `PUT /api/auth/profile` - Update user profile

### Products
- `GET /api/products` - Get all products (with filtering)
- `GET /api/products/:id` - Get single product
- `POST /api/products` - Create product (Admin)
- `PUT /api/products/:id` - Update product (Admin)
- `DELETE /api/products/:id` - Delete product (Admin)
- `POST /api/products/:id/reviews` - Add product review

### Categories
- `GET /api/categories` - Get all categories
- `GET /api/categories/:id` - Get single category
- `POST /api/categories` - Create category (Admin)
- `PUT /api/categories/:id` - Update category (Admin)
- `DELETE /api/categories/:id` - Delete category (Admin)

### Orders
- `GET /api/orders` - Get user orders
- `GET /api/orders/:id` - Get single order
- `POST /api/orders` - Create new order
- `PUT /api/orders/:id/status` - Update order status (Admin)
- `PUT /api/orders/:id/payment` - Update payment status (Admin)

### Users (Admin)
- `GET /api/users` - Get all users (Admin)
- `GET /api/users/:id` - Get user by ID (Admin)
- `PUT /api/users/:id` - Update user (Admin)
- `DELETE /api/users/:id` - Delete user (Admin)

##  Customization

### Styling
The application uses Tailwind CSS for styling. You can customize the design by:
- Modifying `client/tailwind.config.js` for theme customization
- Updating `client/src/index.css` for global styles
- Creating custom components in `client/src/components/`

### Adding New Features
1. **Backend**: Add new routes in `server/routes/` and models in `server/models/`
2. **Frontend**: Create new components in `client/src/components/` and pages in `client/src/pages/`
3. **Database**: Add new schemas in `server/models/`

##  Authentication & Authorization

The application uses JWT tokens for authentication:
- Tokens are stored in localStorage
- Protected routes require valid tokens
- Admin routes require admin role
- Password hashing with bcrypt

##  Shopping Cart

The shopping cart is implemented using React Context:
- Cart state persists in localStorage
- Real-time updates across components
- Quantity management
- Price calculations

##  Responsive Design

The application is fully responsive and works on:
- Desktop computers
- Tablets
- Mobile phones
- All modern browsers

##  Deployment

### Frontend (Netlify/Vercel)
1. Build the frontend: `npm run build`
2. Deploy the `client/build` folder
3. Update API URLs in production

### Backend (Heroku/Railway/DigitalOcean)
1. Set environment variables
2. Deploy the `server` folder
3. Configure MongoDB connection

### Database (MongoDB Atlas)
1. Create MongoDB Atlas account
2. Create cluster
3. Update `MONGODB_URI` in environment variables

##  Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

##  License

This project is licensed under the MIT License.


##  Future Enhancements

- Payment integration (Stripe)
- Email notifications
- Advanced search with filters
- Product reviews and ratings
- Wishlist functionality
- Multi-language support
- Advanced admin analytics
- Mobile app (React Native)

---

