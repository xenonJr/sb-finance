# 🏦 SohojBank

**A fully functional mobile financial services (MFS) prototype with secure transactions, JWT auth, and investor-ready UX.**

🔒 **Link:** https://sohojbank.com/

---

## Overview

SohojBank is a working MFS prototype built for a client to demonstrate core banking capabilities to investors. Not a mockup — every feature is fully functional with real transactional logic, secure authentication, and proper data integrity.

Built to prove technical viability before committing to a production-scale launch.

---

## Tech Stack

| Layer | Tech |
|-------|------|
| Frontend | Angular 19, SCSS |
| Backend | Node.js, Express.js |
| Database | SQLite |
| Auth | JWT (access + refresh tokens), bcrypt |
| API | RESTful, role-based validation |

---

## Core Features

### 💸 Money Operations
- **Send Money** — Transfer funds between accounts with recipient validation, balance checks, and atomic execution
- **Cash Out** — Withdraw funds with agent verification and transaction fee calculation
- **Add Money** — Deposit funds with source validation and instant balance update
- All operations are **atomic** — if any step fails (insufficient balance, invalid recipient, network error), the entire transaction rolls back with no partial state

### 🔐 Security
- **JWT authentication** with token expiry and refresh logic — stateless, scalable session management
- **bcrypt password hashing** with configurable salt rounds — credentials never stored in plaintext
- **Input sanitization** on every endpoint to prevent SQL injection and XSS
- **Rate limiting** on auth endpoints to defend against brute-force attacks
- **Role-based API validation** — every protected route verifies token and permissions before processing

### 📊 Account Management
- Real-time balance display updated after every transaction
- Paginated transaction history with timestamps, amounts, counterparty details, and status flags
- Full audit trail — every transfer, cash-out, and deposit is logged for accountability
- User registration with validation, duplicate checking, and secure onboarding flow

### 📱 Frontend
- Mobile-first responsive design matching production MFS app standards
- Services grid — Add Money, Send Money, Cash Out with intuitive flow
- Recent Transactions feed with real-time updates
- Clean, trustworthy UI designed for investor presentations

---

## Architecture

```
[Angular 19 Frontend]
        ↓
[Express.js REST API]
   ├── /auth    → Registration, Login, Token Refresh
   ├── /account → Balance, Profile, Statements
   └── /txn     → Send Money, Cash Out, Add Money
        ↓
   [SQLite DB]
   (Atomic transactions with rollback)
```

---

## Why SQLite?

Deliberate choice for an investor demo prototype — zero-config, portable, single-file database that runs anywhere without server setup. Investors could interact with the app live on any machine without database configuration. The schema and transaction logic are designed to migrate cleanly to PostgreSQL or MySQL for production.

---



Open `http://localhost:4200` in your browser.

---

## Screenshots

> *Coming soon*

---

## License

MIT
