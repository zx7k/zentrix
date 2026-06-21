# Zentrix - Self-Hosted Email Service

## 🚀 Production-Ready Email Management System

Zentrix is a modern, self-hosted email management service built with **Next.js**, **TypeScript**, **Express**, and **Firebase Realtime Database**.

### ✨ Features

**Authentication**
- Secure registration with @zentrix.com email format
- Auto-generated random usernames (letters & numbers only)
- JWT-based authentication with bcrypt password hashing
- Session persistence with localStorage

**Email Management**
- ✉️ Compose new emails with rich text support
- 📤 Send emails securely through backend
- 📥 Receive and manage emails in real-time
- 📁 Organize with standard folders (Inbox, Sent, Drafts, Trash)
- ↩️ Reply and forward functionality
- 🔍 Search emails by subject, body, or sender
- 🗑️ Delete with trash recovery

**Security Features**
- Firebase Realtime Database for real-time sync
- Zod input validation
- DOMPurify XSS protection
- Helmet HTTP security headers
- Rate limiting on all endpoints
- CORS configuration
- Input sanitization
- Load balancer ready

**User Interface**
- 🌓 System/Dark/Light mode toggle
- 💾 Persistent theme settings
- 📱 Fully responsive design
- 🎨 Modern, advanced Tailwind CSS styling
- ⚡ Real-time updates

### 📋 Tech Stack

**Frontend**
- Next.js 14
- TypeScript
- React 18
- Tailwind CSS
- Firebase SDK
- Lucide React Icons

**Backend**
- Express.js
- Node.js
- Firebase Admin SDK
- Zod (Schema validation)
- Helmet (Security headers)
- bcryptjs (Password hashing)
- JWT (Authentication)

### 🗂️ Project Structure

```
zentrix/
├── backend/
│   ├── config/
│   │   ├── firebase.js
│   │   └── secrets.js
│   ├── middleware/
│   │   ├── authMiddleware.js
│   │   ├── errorHandler.js
│   │   └── requestLogger.js
│   ├── routes/
│   │   ├── auth.js
│   │   ├── email.js
│   │   └── admin.js
│   ├── utils/
│   │   ├── validation.js
│   │   ├── jwt.js
│   │   └── helpers.js
│   ├── package.json
│   └── server.js
│
├── frontend/
│   ├── app/
│   │   ├── layout.tsx
│   │   ├── page.tsx
│   │   ├── globals.css
│   │   ├── login/
│   │   ├── register/
│   │   └── dashboard/
│   ├── components/
│   │   ├── ThemeToggle.tsx
│   │   ├── Sidebar.tsx
│   │   └── EmailList.tsx
│   ├── hooks/
│   │   ├── useAuth.ts
│   │   ├── useTheme.ts
│   │   └── useEmails.ts
│   ├── lib/
│   │   ├── firebase.ts
│   │   ├── api.ts
│   │   └── validation.ts
│   ├── package.json
│   └── next.config.js
│
├── .env.example
└── README.md
```

### 🚀 Quick Start

**1. Clone Repository**
```bash
git clone https://github.com/zx7k/zentrix.git
cd zentrix
```

**2. Setup Backend**
```bash
cd backend
npm install
cp ../.env.example .env.local
npm run dev
```

**3. Setup Frontend**
```bash
cd frontend
npm install
cp ../.env.example .env.local
npm run dev
```

**4. Access Application**
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000

### 🔐 Security Configuration

All environment variables are in `.env.example`. Copy to `.env.local` and configure:

```env
NEXT_PUBLIC_FIREBASE_PROJECT_ID=zentrix-7
JWT_SECRET=your-secure-jwt-secret-min-32-chars
ENCRYPTION_KEY=your-secure-encryption-key-32-chars
BAC_K_END_PORT=5000
```

### 📊 API Endpoints

**Authentication**
- `POST /api/v1/auth/register` - Create account
- `POST /api/v1/auth/login` - Login
- `POST /api/v1/auth/generate-username` - Auto-generate username

**Emails**
- `GET /api/v1/email/inbox` - Get inbox
- `GET /api/v1/email/sent` - Get sent emails
- `POST /api/v1/email/send` - Send email
- `DELETE /api/v1/email/:id` - Delete email

**Admin**
- `GET /api/v1/admin/stats` - Get user stats
- `PUT /api/v1/admin/theme` - Update theme

### 🛡️ Security Middleware

- **Helmet**: Sets security HTTP headers
- **CORS**: Configured for localhost:3000
- **Rate Limiting**: 
  - Auth endpoints: 5 requests/15 min
  - General endpoints: 100 requests/15 min
- **Input Validation**: All inputs validated with Zod
- **Password Hashing**: bcrypt with 10 salt rounds
- **JWT Tokens**: 24-hour expiration

### 🌓 Theme System

Supports three modes:
- **Light**: Clean white theme
- **Dark**: Slate dark theme
- **System**: Follows OS preference

Theme preference is saved to localStorage and Firebase

### 📝 License

MIT License

### 🤝 Contributing

Contributions welcome! Please fork and create a pull request.

---

**Made with ❤️ by Zentrix Team**