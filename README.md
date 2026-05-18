# Reusable Full-Stack Authentication System

A production-grade, modular, and reusable authentication system built with Next.js, TypeScript, Express.js, and MongoDB.

This project is designed following industry-standard architecture and security practices so it can be integrated into any future application with minimal configuration.

---

## Features

* User Registration
* Login and Logout
* Email Verification
* Forgot Password
* Reset Password
* Change Password
* Persistent Authentication
* JWT Access Tokens
* Refresh Tokens (HTTP-only Cookies)
* Protected Routes
* Role-Based Access Control (RBAC)
* Global Redux Toolkit Store
* Modular Frontend and Backend Architecture
* Strong TypeScript Type Safety
* Reusable Across Multiple Projects

---

## Tech Stack

### Frontend

* Next.js (App Router)
* TypeScript
* Tailwind CSS
* Redux Toolkit
* React Hook Form
* Zod

### Backend

* Node.js
* Express.js
* TypeScript
* MongoDB Atlas
* Mongoose

### Security

* JSON Web Tokens (JWT)
* Refresh Tokens
* bcrypt
* Node.js crypto module

### Email Service

* Brevo (Free Tier)

### Optional Infrastructure

* Redis (future enhancement)

---

## Project Structure

```text
reusable-auth-system/
├── frontend/          # Next.js application
├── backend/           # Express.js API
├── docs/
│   └── SRS.md         # Software Requirements Specification
├── README.md
└── .gitignore
```

---

## Frontend Architecture

```text
frontend/
├── app/
├── components/
├── features/
│   └── auth/
├── store/
├── lib/
├── middleware.ts
└── package.json
```

---

## Backend Architecture

```text
backend/
├── src/
│   ├── modules/
│   │   └── auth/
│   ├── config/
│   ├── middleware/
│   ├── utils/
│   ├── app.ts
│   └── server.ts
└── package.json
```

---

## Authentication Flow

1. User registers.
2. System stores the account with `isEmailVerified = false`.
3. Verification email is sent through Brevo.
4. User verifies the email.
5. User logs in.
6. Backend issues:

   * Access Token (JWT)
   * Refresh Token (HTTP-only cookie)
7. Frontend stores user state in Redux Toolkit.
8. Protected routes check authentication and roles.
9. Expired access tokens are automatically refreshed.
10. Forgot password and reset password flows use secure tokens.

---

## Security Features

* Password hashing with bcrypt
* Token hashing using crypto
* HTTP-only refresh cookies
* Access token expiration
* Secure password reset links
* Email verification tokens
* Role-based route protection
* Rate limiting (future enhancement)

---

## Documentation

Detailed requirements and architecture are available in:

* `docs/SRS.md`

---

## Setup

### Clone the Repository

```bash
git clone <repository-url>
cd reusable-auth-system
```

### Install Frontend Dependencies

```bash
cd frontend
pnpm install
```

### Install Backend Dependencies

```bash
cd ../backend
pnpm install
```

---

## Environment Variables

Create environment files for frontend and backend.

### Backend `.env`

```env
PORT=5000
MONGODB_URI=
JWT_ACCESS_SECRET=
JWT_REFRESH_SECRET=
BREVO_API_KEY=
BREVO_SENDER_EMAIL=
CLIENT_URL=http://localhost:3000
```

### Frontend `.env.local`

```env
NEXT_PUBLIC_API_URL=http://localhost:5000/api/v1
```

---

## Development

### Start Frontend

```bash
cd frontend
pnpm dev
```

### Start Backend

```bash
cd backend
pnpm dev
```

---

## Project Goals

* Build once and reuse in all future applications.
* Follow enterprise-level architectural standards.
* Maintain high security and code quality.
* Reduce authentication setup time in future projects.
* Provide an excellent portfolio and production foundation.

---

## Future Enhancements

* Multi-Factor Authentication (MFA)
* OAuth (Google, GitHub, LinkedIn)
* Device Management
* Session History
* Audit Logs
* Redis-Based Session Storage

---

## License

MIT License

---

## Author

**Ankit Yadav**
[LinkedIn Profile](https://in.linkedin.com/in/ankit-yadavji?utm_source=chatgpt.com)
