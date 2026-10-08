# Employee Directory System

## Overview

A secure TypeScript directory API for departments, employee profiles, reporting lines, contact self-service, search, and workforce summaries.

## Features

Admin/Employee roles, department and manager relationships, unique employee identities, paginated search and filters, limited employee self-service, administrator lifecycle control, audit records, and dashboard metrics.

## Technology Stack

Node.js 24, TypeScript 7, Express 5, built-in SQLite, Zod 4, Vitest 5, and Docker.

## Requirements / Installation

Install Node.js 24+ and npm 11+, then run `npm install`.

## Environment Variables

Configure `PORT`, `DB_PATH`, and `CORS_ORIGIN` using `.env.example`.

## Database Setup

The migration runs automatically. Development departments, employee, and users seed only when the user table is empty.

## Running the Application

Run `npm run dev`, or `npm run build && npm start`.

## Running Tests

Run `npm run check`. Tests cover creation/search, duplicates, contact self-service, privilege prevention, and deactivation.

## Default Development Accounts

`admin` and `employee`, password `ChangeMe123!` (development only).

## API Endpoints

`POST /api/auth/login`, `GET /api/departments`, `GET/POST /api/employees`, `PATCH /api/employees/:id`, and `GET /api/dashboard`.

## Folder Structure

`src/services` contains directory rules, `src/app.ts` contains routes/validation, `src/auth.ts` contains session security, `migrations` contains schema, and `tests` contains business-rule tests.

## Security Notes

Scrypt password hashes, digested two-hour sessions, roles, self-profile ownership, property allowlists against mass assignment, parameterized SQL, runtime validation, Helmet, constrained CORS, login rate limiting, and safe errors are implemented. Only intended directory fields are exposed. Use HTTPS and replace demo accounts in production.

## Known Limitations

Avatar uploads, SSO, HR/payroll data, org-chart graphics, bulk import, and SCIM integration are outside scope.

## License

MIT
