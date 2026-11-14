# Security notes

Local-only internship demo. Password hashes use bcrypt, sessions use JWT in HttpOnly SameSite cookies. Never commit `.env`, real credentials or payment keys. The demo payment simulator is not a real processor. For production, require HTTPS + Secure cookies, CSRF controls, explicit JWT_SECRET, real webhook monitoring, stock reservation/locking, idempotent fulfillment and security review.
