# Bulk Email Campaign Manager

A modern, production-ready web application for managing and sending personalized email campaigns. Built with React + TypeScript, Node.js + Express, and SQLite.

## 🎯 Features

### Dashboard
- Real-time campaign statistics
- Recipients overview (uploaded, generated, sent, remaining, failed)
- Campaign progress tracking
- Performance metrics (24-hour stats, success/error rates)

### Campaign Management
- **Upload recipient lists** (CSV/TXT, up to 10,000 emails)
- **Email composer** with rich text editor and HTML support
- **Personalization** with placeholders ({{first_name}}, {{last_name}}, {{email}}, {{company}})
- **Generate personalized emails** for all recipients
- **Send campaigns** with pause/resume/stop controls

### Email Sending
- Multiple SMTP providers (Gmail, SendGrid, Amazon SES, Mailgun)
- Rate limiting and queue management
- Automatic retry for failed emails
- Skip already-sent emails
- No UI freezing with background queue processing

### Monitoring & Analytics
- Real-time sending progress
- Live logs (email generated, sent, retry, errors)
- Search and filter recipients
- Charts for performance analytics
- CSV/Excel/PDF export capabilities

### Security
- JWT authentication with role-based access (Admin)
- Encrypted SMTP credentials
- File validation and duplicate detection
- Invalid email prevention

## 🛠️ Tech Stack

### Frontend
- React 18+
- TypeScript
- Tailwind CSS
- Lucide React Icons
- Socket.io for real-time updates
- Recharts for analytics

### Backend
- Node.js + Express
- TypeScript
- BullMQ (Redis-based job queue)
- SQLite (PostgreSQL-ready)
- Nodemailer for email delivery
- JWT authentication

### Infrastructure
- Docker & Docker Compose
- Redis for job queue
- SQLite/PostgreSQL for database

## 📊 Database Schema

### Tables
- **users** - User accounts
- **campaigns** - Email campaigns
- **recipients** - Email recipients
- **emails** - Generated emails
- **email_logs** - Sending history
- **smtp_configs** - SMTP provider settings
- **attachments** - Campaign attachments

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- Docker & Docker Compose (optional but recommended)
- Redis

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Dannyex0/bulk-email-campaign-manager.git
   cd bulk-email-campaign-manager
   ```

2. **Setup Backend**
   ```bash
   cd backend
   cp .env.example .env
   npm install
   npm run dev
   ```

3. **Setup Frontend** (in another terminal)
   ```bash
   cd frontend
   cp .env.example .env
   npm install
   npm run dev
   ```

4. **Using Docker** (easier way)
   ```bash
   docker-compose up -d
   ```

### Access the Application
- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:3000
- **Health Check**: http://localhost:3000/api/health

## 📋 API Endpoints

### Authentication
- `POST /api/auth/register` - Register user
- `POST /api/auth/login` - Login user
- `POST /api/auth/logout` - Logout user

### Campaigns
- `GET /api/campaigns` - List all campaigns
- `POST /api/campaigns` - Create campaign
- `GET /api/campaigns/:id` - Get campaign details
- `PUT /api/campaigns/:id` - Update campaign
- `DELETE /api/campaigns/:id` - Delete campaign

### Recipients
- `POST /api/campaigns/:id/upload` - Upload recipient list
- `GET /api/campaigns/:id/recipients` - List recipients
- `GET /api/campaigns/:id/recipients/stats` - Recipient statistics

### Email Operations
- `POST /api/campaigns/:id/generate` - Generate personalized emails
- `POST /api/campaigns/:id/send` - Start sending campaign
- `POST /api/campaigns/:id/pause` - Pause campaign
- `POST /api/campaigns/:id/resume` - Resume campaign
- `POST /api/campaigns/:id/stop` - Stop campaign
- `POST /api/campaigns/:id/retry` - Retry failed emails

## 🔐 Security Features

- ✅ JWT-based authentication
- ✅ Role-based access control (Admin)
- ✅ Encrypted SMTP credentials
- ✅ Input validation and sanitization
- ✅ Duplicate email detection
- ✅ Invalid email filtering
- ✅ Rate limiting on API endpoints
- ✅ CORS protection

## 📈 Performance

- Supports up to 10,000 recipients
- Virtualized tables for smooth scrolling
- Background queue processing (no UI freezing)
- Rate limiting to respect SMTP provider limits
- Automatic retry with exponential backoff
- Horizontal scaling ready (multiple workers)

## 📝 Getting Started

See individual README files in:
- `backend/README.md` - Backend setup and API documentation
- `frontend/README.md` - Frontend setup and component structure

## 🤝 Contributing

Contributions are welcome! Please follow these steps:
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## 📄 License

MIT License

## 🆘 Support

For issues, questions, or suggestions, please open an issue on GitHub.

---

**Built with ❤️ for email marketing teams**
