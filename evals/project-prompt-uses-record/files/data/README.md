# Tables in the snapshot

All tables carry `user_id` and `signup_date`.

- `users`: plan, signup_date, signup_device, country, referrer, cancelled_at
- `events`: one row per in-app action (name, timestamp, properties as JSON)
- `transactions`: imported or entered bookkeeping lines (source, amount, category, categorised_by: user or auto)
- `invoices`: sent_at, due_at, paid_at, amount, client_id
- `bank_connections`: provider, connected_at, last_sync_status
- `support_tickets`: opened_at, first_message (text), resolved_at
- `emails_sent`: template, sent_at, opened_at
- `accountant_invites`: invited_at, accepted_at

Never used in any analysis so far: `transactions.categorised_by`, `invoices.paid_at`, `support_tickets.first_message`.
