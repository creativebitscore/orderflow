# Demo
1. Copy `.env.example` to `.env` and replace secrets.
2. Run `docker compose up --build`.
3. Register: `curl -X POST http://localhost:8080/api/auth/register -H "Content-Type: application/json" -d '{"email":"demo@example.com","password":"password123"}'`.
4. Copy the access token and call product/inventory endpoints with `Authorization: Bearer TOKEN`.
5. Set inventory for a product, add that product to a cart, then `POST /api/orders` using the documented checkout body.
6. Poll `GET /api/orders?userId=...` and observe `PENDING → INVENTORY_RESERVED → CONFIRMED` or `CANCELLED`.
7. Set `PAYMENT_FAILURE_RATE=1.0`, restart payment-service, and repeat to demonstrate compensation and inventory release.
8. Open RabbitMQ at `http://localhost:15672` (`guest`/`guest` for local Docker only) to inspect durable queues.
9. Run `scripts/load-test.ps1` only after health checks pass; preserve its output as benchmark evidence.

Payment is simulated and never accepts card details.
