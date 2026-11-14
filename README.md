# NOIR MARKET — Secure E-Commerce Engine with Checkout Sandbox

**Progree Full Stack Development Internship — Task 4**  
**Developer:** Farhan Ahmed Siddiqui  
**Student ID:** B9/2731

A responsive local store with Express, SQLite, bcrypt password hashing, JWT cookie sessions, persistent cart, order history, inventory adjustment and two checkout modes.

## Start on Windows PowerShell

1. Install Node.js 22.13+ or Node.js 24 (Node built-in SQLite is used; no Python/build tools).
2. Open this folder in VS Code.
3. Run `npm.cmd install`.
4. Run `npm.cmd start`.
5. Open `http://127.0.0.1:3002`.
6. Run `npm.cmd test` in another terminal for automated API tests.

## Local demo checkout (default)

No API key is required. Register with a sample email and a password at least 10 characters long, sign in, add an item to the cart and click checkout. The offline **Simulate successful payment** action demonstrates inventory updates, order completion and cart clearing. This is **not** a real payment, not Stripe-hosted, and does not charge any card. Cancel keeps inventory unchanged.

## Optional Stripe TEST checkout

Create `.env` from `.env.example` and set `JWT_SECRET`, `STRIPE_SECRET_KEY=sk_test_...`, `STRIPE_WEBHOOK_SECRET` and `BASE_URL`. Use a Stripe test webhook forwarding to `/api/webhook`. Inventory updates only after a verified successful payment webhook. No live keys or real payments should be used for internship testing.

## Security and scope

Passwords are hashed with bcrypt; JWT is stored in HttpOnly SameSite cookies. Use HTTPS, secure cookies, a unique JWT secret, CSRF protections, production-grade rate limiting, logging, and Stripe webhook reconciliation before any production use. Local demo mode is deliberately **not a payment gateway**. Database is stored as `market.sqlite` and survives server restarts. The demo is local-only.

## Endpoints

`GET /api/health`, `GET /api/products`, `POST /api/register`, `POST /api/login`, `POST /api/logout`, `GET /api/me`, `GET/POST /api/cart`, `POST /api/checkout`, `GET /api/orders`, `GET /api/demo/order/:id`, `POST /api/demo/complete`, `POST /api/demo/cancel`, `POST /api/webhook`.

## Submission

See `B9-2731_Task4_Report.pdf` for architecture, testing and screenshot evidence. No deployment required.
