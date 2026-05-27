# Farmer-Buyer Marketplace

A comprehensive web-based platform connecting farmers directly with buyers, featuring real-time transactions, messaging, and admin management capabilities.

## 🎯 Project Overview

This is a full-stack application designed to:
- **Farmers**: List and manage their products
- **Buyers**: Browse and purchase farm products directly
- **Admin**: Monitor platform activities, manage users, and moderate content

## 📋 Tech Stack

- **Frontend**: React.js with Redux state management
- **Admin Panel**: React.js with specialized dashboard
- **Backend**: Node.js with Express.js
- **Database**: PostgreSQL
- **Real-time**: Socket.io for messaging
- **Payment**: Stripe integration (configurable)
- **Deployment**: Docker & Docker Compose
- **CI/CD**: GitHub Actions

## 🚀 MVP Features

### Phase 1 (Core)
- [ ] User authentication (Farmers, Buyers, Admin)
- [ ] Product listing (Farmers)
- [ ] Product browsing & search (Buyers)
- [ ] Shopping cart & checkout
- [ ] Order management
- [ ] User profiles

### Phase 2 (Communication)
- [ ] Real-time messaging
- [ ] Order notifications
- [ ] Review & rating system

### Phase 3 (Admin)
- [ ] Dashboard with analytics
- [ ] User management
- [ ] Product moderation
- [ ] Order tracking
- [ ] Report generation

## 📁 Project Structure

```
farmer-buyer-marketplace/
├── frontend/              # React buyer & farmer interface
├── admin/                 # React admin panel
├── backend/               # Node.js/Express API
├── database/              # PostgreSQL schemas
├── docker/                # Docker configuration
├── docs/                  # Documentation
├── .github/workflows/     # CI/CD pipelines
└── README.md
```

## 🛠️ Setup Instructions

### Prerequisites
- Node.js v16+
- PostgreSQL 12+
- Docker & Docker Compose
- Git

### Quick Start

1. **Clone Repository**
   ```bash
   git clone https://github.com/Desirecb/farmer-buyer-marketplace.git
   cd farmer-buyer-marketplace
   ```

2. **Using Docker (Recommended)**
   ```bash
   docker-compose up -d
   ```

3. **Manual Setup**
   
   **Backend Setup:**
   ```bash
   cd backend
   npm install
   cp .env.example .env
   npm run migrate
   npm start
   ```

   **Frontend Setup:**
   ```bash
   cd frontend
   npm install
   npm start
   ```

   **Admin Panel Setup:**
   ```bash
   cd admin
   npm install
   npm start
   ```

4. **Access the Application**
   - Frontend: http://localhost:3000
   - Admin: http://localhost:3001
   - Backend API: http://localhost:5000
   - API Docs: http://localhost:5000/api/docs

## 📚 Documentation

- [Backend API Documentation](./docs/API.md)
- [Database Schema](./docs/DATABASE.md)
- [Development Guide](./docs/DEVELOPMENT.md)
- [Deployment Guide](./docs/DEPLOYMENT.md)

## 🤝 Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

## 📄 License

MIT License - see LICENSE file for details

## 📞 Support

For issues and questions, please open an [Issue](https://github.com/Desirecb/farmer-buyer-marketplace/issues)

---

**Happy Coding! 🌾🚀**
