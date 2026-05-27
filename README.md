<div align="center">

<!-- Animated Typing Banner -->
<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=28&pause=1000&color=6366F1&center=true&vCenter=true&width=700&lines=SaaS+Auth+System+%F0%9F%94%90;Production-Ready+Auth+Boilerplate;Node.js+%2B+Express+%2B+MongoDB+%2B+JWT;Enterprise-Grade+Security+%E2%9A%A1" alt="Typing SVG" /></a>

<br/>

<p align="center">
  <img src="https://img.shields.io/badge/version-1.0.0-6366F1?style=for-the-badge&logo=semver&logoColor=white" alt="Version"/>
  <img src="https://img.shields.io/badge/Node.js-18%2B-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js"/>
  <img src="https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge&logo=opensourceinitiative&logoColor=white" alt="MIT License"/>
  <img src="https://img.shields.io/badge/PRs-Welcome-f59e0b?style=for-the-badge&logo=git&logoColor=white" alt="PRs Welcome"/>
  <img src="https://img.shields.io/badge/Maintained-Yes-06b6d4?style=for-the-badge" alt="Maintained"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Docker-Ready-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
  <img src="https://img.shields.io/badge/Swagger-API_Docs-85EA2D?style=for-the-badge&logo=swagger&logoColor=black" alt="Swagger"/>
  <img src="https://img.shields.io/badge/Jest-Tested-C21325?style=for-the-badge&logo=jest&logoColor=white" alt="Jest"/>
  <img src="https://img.shields.io/badge/PM2-Process_Manager-2B037A?style=for-the-badge&logo=pm2&logoColor=white" alt="PM2"/>
  <img src="https://img.shields.io/badge/Build-Passing-22c55e?style=for-the-badge&logo=githubactions&logoColor=white" alt="Build"/>
</p>

<br/>a

<p align="center">
  A <strong>production-ready</strong>, <strong>SaaS</strong> Auth System<br/>
  built with <strong>Node.js</strong> · <strong>Express</strong> · <strong>MongoDB</strong> · <strong>JWT</strong> · <strong>Passport.js</strong><br/>
  <em>Plug-and-play auth for your next SaaS product — register, ship, scale.</em>
</p>

<br/>

<p align="center">
  <a href="#-quick-start">Quick Start</a> ·
  <a href="#-features">Features</a> ·
  <a href="#-docker-setup">Docker</a> ·
  <a href="#-swagger-docs">Docs</a> ·
</p>

</div>

---

## 📋 Table of Contents

- [✨ Features](#-features)
- [🛠️ Tech Stack](#️-tech-stack)
- [⚡ Quick Start](#-quick-start)
- [🔧 Environment Variables](#-environment-variables)
- [📁 Project Structure](#-project-structure)
- [🐳 Docker Setup](#-docker-setup)
- [🔐 Security Features](#-security-features)
- [🧪 Testing](#-testing)
- [🏗️ Architecture](#️-architecture)

---

## ✨ Features

<div align="center">

| 🔑 Authentication | 🛡️ Security | 🔧 Developer Experience |
|:---|:---|:---|
| ✅ Register & Login | ✅ JWT Access Tokens | ✅ Swagger API Docs |
| ✅ Refresh Tokens | ✅ Role-Based Access Control | ✅ Docker & Docker Compose |
| ✅ Forgot Password Flow | ✅ Security Middleware (Helmet, CORS) | ✅ PM2 Process Manager |
| ✅ Password Reset | ✅ Rate Limiting | ✅ Jest Unit & Integration Tests |
| ✅ Email Verification | ✅ Input Validation (Joi) | ✅ Structured Logging System |
| ✅ Google OAuth 2.0 | ✅ HTTP-only Cookies | ✅ Environment-based Config |

</div>

---

## 🛠️ Tech Stack

<div align="center">

### Core

<img src="https://skillicons.dev/icons?i=nodejs,express,mongodb,js&theme=dark" alt="Core Stack"/>

### Auth & Validation

<img src="https://skillicons.dev/icons?i=jest,docker,postman,git&theme=dark" alt="Dev Tools"/>

### Infrastructure & Tooling

<p>
  <img src="https://img.shields.io/badge/Mongoose-880000?style=for-the-badge&logo=mongoose&logoColor=white" alt="Mongoose"/>
  <img src="https://img.shields.io/badge/Passport.js-34E27A?style=for-the-badge&logo=passport&logoColor=black" alt="Passport"/>
  <img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white" alt="JWT"/>
  <img src="https://img.shields.io/badge/Joi-0080FF?style=for-the-badge&logo=javascript&logoColor=white" alt="Joi"/>
  <img src="https://img.shields.io/badge/Nodemailer-22B573?style=for-the-badge&logo=gmail&logoColor=white" alt="Nodemailer"/>
  <img src="https://img.shields.io/badge/PM2-2B037A?style=for-the-badge&logo=pm2&logoColor=white" alt="PM2"/>
  <img src="https://img.shields.io/badge/Swagger-85EA2D?style=for-the-badge&logo=swagger&logoColor=black" alt="Swagger"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
</p>

</div>

---

## ⚡ Quick Start

### Prerequisites

> Make sure you have these installed before proceeding.

```bash
node  >= 18.0.0
npm   >= 9.0.0
mongoDB >= 6.0  (or a MongoDB Atlas URI)
docker  >= 24.0 (optional, for containerized setup)
```

### 1 · Clone the repository

```bash
git clone https://github.com/your-username/saas-auth-system.git
cd saas-auth-system
```

### 2 · Install dependencies

```bash
yarn install
```

### 3 · Configure environment

```bash
cp .env.example .env
# Open .env and fill in your values (see Environment Variables below)
```

### 4 · Start development server

```bash
yarn dev
```

> 🎉 Server is running at `http://localhost:3000`
> 📖 Swagger docs available at `http://localhost:3000/v1/docs`

---

## 🔧 Environment Variables

Create a `.env` file in the root directory. Reference `.env.example` for all required keys.

```env
# ─── Server ──────────────────────────────────────────────
PORT=3000

# ─── Database ────────────────────────────────────────────
MONGODB_URL=mongodb://localhost:27017/saas-auth

# ─── JWT ─────────────────────────────────────────────────
JWT_SECRET=your_super_secret_jwt_key_here
JWT_ACCESS_EXPIRATION_MINUTES=30
JWT_REFRESH_EXPIRATION_DAYS=30

# ─── Email (SMTP) ─────────────────────────────────────────
SMTP_HOST=smtp.mailtrap.io
SMTP_PORT=587
SMTP_USERNAME=your_smtp_username
SMTP_PASSWORD=your_smtp_password
EMAIL_FROM=noreply@yoursaas.com

# ─── OAuth (Google) ───────────────────────────────────────
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
```

> [!WARNING]
> Never commit your `.env` file to version control. It is already listed in `.gitignore`.

> [!TIP]
> For local email testing, use [Mailtrap](https://mailtrap.io) or [Ethereal Email](https://ethereal.email) as your SMTP provider.

---

## 📁 Project Structure

```
saas-auth-system/
│
├── 📂 src/
│   ├── 📂 config/          # App configuration (DB, Passport, env validation)
│   ├── 📂 controllers/     # Route handler logic
│   ├── 📂 middlewares/     # Auth, error handling, rate limiting
│   ├── 📂 models/          # Mongoose data models
│   ├── 📂 routes/          # Express route definitions
│   ├── 📂 services/        # Business logic layer
│   ├── 📂 utils/           # Helpers, token generators, email sender
│   ├── 📂 validations/     # Joi request validation schemas
│   └── 📄 index.js         # Application entry point
│
├── 📂 tests/               # Jest unit & integration tests
├── 📄 .env.example         # Environment variable template
├── 📄 docker-compose.yml   # Multi-container Docker setup
├── 📄 Dockerfile           # Production Docker image
├── 📄 ecosystem.config.js  # PM2 process configuration
├── 📄 swagger.json         # Swagger / OpenAPI specification
└── 📄 package.json
```

---

## 🐳 Docker Setup

### Development (with hot reload)

```bash
docker-compose up --build
```

### Production

```bash
docker-compose -f docker-compose.prod.yml up -d
```

### Sample `docker-compose.yml`

```yaml
version: '3.8'

services:
  app:
    build: .
    ports:
      - '3000:3000'
    environment:
      - NODE_ENV=production
      - MONGODB_URL=mongodb://mongo:27017/saas-auth
    depends_on:
      - mongo
    restart: unless-stopped

  mongo:
    image: mongo:6.0
    ports:
      - '27017:27017'
    volumes:
      - mongo_data:/data/db
    restart: unless-stopped

volumes:
  mongo_data:
```

---

## 🔐 Security Features

> [!IMPORTANT]
> This boilerplate ships with the following security hardening out of the box.

```
✅  Helmet.js          — Secure HTTP headers
✅  CORS               — Configurable origin whitelist
✅  Rate Limiting      — Brute-force protection on auth routes
✅  JWT Rotation       — Short-lived access tokens + refresh token rotation
✅  HTTP-only Cookies  — Prevents XSS token theft
✅  Joi Validation     — Strict input sanitization on all endpoints
✅  Password Hashing   — bcrypt with configurable salt rounds
✅  Email Verification — Prevents fake account creation
✅  Role-Based Access  — Fine-grained endpoint authorization (user / admin)
✅  Token Blacklist    — Logout invalidates refresh tokens in DB
```

---

## 🧪 Testing

This project uses **Jest** for unit and integration testing.

```bash
# Run all tests
npm test

# Run with coverage report
npm run test:coverage

# Run in watch mode (development)
npm run test:watch
```

## 🏗️ Architecture

```
  ┌──────────────────────────────────────────────────────┐
  │                     CLIENT                           │
  │          (Web App / Mobile App / Postman)            │
  └────────────────────────┬─────────────────────────────┘
                           │ HTTPS
  ┌────────────────────────▼─────────────────────────────┐
  │                   EXPRESS SERVER                      │
  │  ┌─────────────┐  ┌──────────────┐  ┌─────────────┐ │
  │  │   Routes    │→ │ Middlewares  │→ │ Controllers │ │
  │  └─────────────┘  └──────────────┘  └──────┬──────┘ │
  │                                            │        │
  │  ┌─────────────────────────────────────────▼──────┐ │
  │  │                  Services Layer                 │ │
  │  │  (Auth · User · Email · Token · Password)       │ │
  │  └────────────────────┬────────────────────────────┘ │
  └───────────────────────┼──────────────────────────────┘
                          │
  ┌───────────────────────▼──────────────────────────────┐
  │                   DATA LAYER                          │
  │   ┌──────────────┐          ┌──────────────────────┐ │
  │   │   MongoDB    │          │  External Services   │ │
  │   │  (Mongoose)  │          │  (SMTP · Google OAuth)│ │
  │   └──────────────┘          └──────────────────────┘ │
  └──────────────────────────────────────────────────────┘
```

---

## 📖 Swagger Docs

Interactive API documentation is generated and available at:

```
http://localhost:3000/v1/docs
```

<div align="center">
  <img src="https://img.shields.io/badge/OpenAPI-3.0-85EA2D?style=for-the-badge&logo=swagger&logoColor=black" alt="OpenAPI 3.0"/>
  <img src="https://img.shields.io/badge/Interactive-Docs-6366F1?style=for-the-badge&logo=swagger&logoColor=white" alt="Interactive Docs"/>
</div>

All endpoints are documented with:
- Request body schemas
- Response examples
- Auth requirements
- Error codes

---

<div align="center">

### 🌟 If this project helped you, give it a star!

<img src="https://img.shields.io/github/stars/starrysanjay/saas-auth-system?style=for-the-badge&logo=github&color=6366F1" alt="Stars"/>
<img src="https://img.shields.io/github/forks/starrysanjay/saas-auth-system?style=for-the-badge&logo=github&color=22c55e" alt="Forks"/>
<img src="https://img.shields.io/github/issues/starrysanjay/saas-auth-system?style=for-the-badge&logo=github&color=f59e0b" alt="Issues"/>

<br/><br/>

**Built with ❤️ using Node.js · Express · MongoDB · JWT**

<sub>
  <a href="https://github.com/starrysanjay/saas-auth-system/issues">Report a Bug</a> ·
  <a href="https://github.com/starrysanjay/saas-auth-system/issues">Request a Feature</a> ·
  <a href="https://github.com/starrysanjay/saas-auth-system/discussions">Discussions</a>
</sub>

<br/><br/>

<img src="https://img.shields.io/badge/Made%20with-Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Made with Node.js"/>

</div>
