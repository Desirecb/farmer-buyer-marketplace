# Backend Setup Guide

## Prerequisites

- Node.js v16+
- PostgreSQL 12+
- npm or yarn

## Environment Variables

Create a `.env` file in the `backend` directory:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=your_password
DB_NAME=farmer_buyer_db

# JWT
JWT_SECRET=your_jwt_secret_key_here
JWT_EXPIRE=7d

# Email Service
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your_email@gmail.com
SMTP_PASSWORD=your_app_password

# Payment Gateway (Stripe)
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key

# File Upload
UPLOAD_PATH=./uploads
MAX_FILE_SIZE=5242880

# Socket.io
SOCKET_PORT=5001
```

## Installation & Setup

1. **Install Dependencies**
   ```bash
   cd backend
   npm install
   ```

2. **Create Database**
   ```bash
   npm run migrate:latest
   npm run seed:db
   ```

3. **Start Development Server**
   ```bash
   npm run dev
   ```

4. **API will be available at**: `http://localhost:5000`

## Project Structure

```
backend/
├── src/
│   ├── config/           # Configuration files
│   ├── controllers/      # Route controllers
│   ├── models/           # Database models
│   ├── routes/           # API routes
│   ├── middleware/       # Express middleware
│   ├── utils/            # Utility functions
│   ├── validations/      # Input validation schemas
│   └── app.js            # Express app setup
├── migrations/           # Database migrations
├── seeds/                # Database seeds
├── tests/                # Test files
├── .env.example          # Environment variables template
└── package.json
```

## Available Scripts

```bash
npm start              # Start production server
npm run dev            # Start development server with nodemon
npm test               # Run tests
npm run migrate:latest # Run database migrations
npm run seed:db        # Seed database with sample data
npm run lint           # Run ESLint
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `POST /api/auth/refresh-token` - Refresh JWT token

### Users
- `GET /api/users/:id` - Get user profile
- `PUT /api/users/:id` - Update user profile
- `DELETE /api/users/:id` - Delete user account

### Products (Farmers)
- `POST /api/products` - Create product listing
- `GET /api/products` - Get all products
- `GET /api/products/:id` - Get product details
- `PUT /api/products/:id` - Update product
- `DELETE /api/products/:id` - Delete product

### Orders (Buyers)
- `POST /api/orders` - Create order
- `GET /api/orders` - Get user orders
- `GET /api/orders/:id` - Get order details
- `PUT /api/orders/:id/status` - Update order status

### Admin
- `GET /api/admin/dashboard` - Dashboard stats
- `GET /api/admin/users` - Manage users
- `GET /api/admin/products` - Moderate products
- `GET /api/admin/orders` - View all orders

## Testing

```bash
npm test                    # Run all tests
npm run test:watch        # Run tests in watch mode
npm run test:coverage     # Generate coverage report
```

## Troubleshooting

### Database Connection Error
- Ensure PostgreSQL is running
- Check DB credentials in `.env`
- Verify database name exists

### Port Already in Use
```bash
# Kill process on port 5000
lsof -ti:5000 | xargs kill -9
```

### Module Not Found
```bash
rm -rf node_modules
npm install
```