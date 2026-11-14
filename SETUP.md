# Setup — Task 4

Open folder in VS Code → terminal → `npm.cmd install` → `npm.cmd start` → visit `http://127.0.0.1:3002`.

Register a test account, sign in, add products, open bag and choose Checkout. With no Stripe test key the checkout uses an explicitly labelled local demo simulator. To run tests: `npm.cmd test`.

For Stripe TEST integration only, configure `.env` from `.env.example`, run Stripe webhook forwarding to `/api/webhook` and use Stripe test card data provided by Stripe. Never use live API keys for this project.
