# Docker Setup Guide

## Prerequisites

- Docker v20.10+
- Docker Compose v1.29+
- Git

## Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/Desirecb/farmer-buyer-marketplace.git
   cd farmer-buyer-marketplace
   ```

2. **Create environment file**
   ```bash
   cp .env.example .env
   ```

3. **Start all services**
   ```bash
   docker-compose up -d
   ```

4. **Verify services are running**
   ```bash
   docker-compose ps
   ```

## Services

The `docker-compose.yml` includes:

- **PostgreSQL** (Port 5432)
- **Backend API** (Port 5000)
- **Frontend** (Port 3000)
- **Admin Panel** (Port 3001)
- **Redis** (Port 6379) - for caching and sessions
- **Nginx** (Port 80, 443) - reverse proxy

## Useful Docker Commands

```bash
# View logs
docker-compose logs -f backend

# Stop all services
docker-compose down

# Rebuild services
docker-compose up -d --build

# Run migrations in container
docker-compose exec backend npm run migrate:latest

# Access database shell
docker-compose exec postgres psql -U postgres -d farmer_buyer_db
```

## Troubleshooting

### Port Already in Use
```bash
# Find process using port
lsof -i :5000

# Kill process
kill -9 <PID>
```

### Database Connection Failed
- Ensure PostgreSQL container is running
- Check environment variables in `.env`
- Verify database credentials