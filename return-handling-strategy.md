# ACH Return Handling Strategy

ACH transactions may return after submission with standardized return codes.

These codes indicate why a transaction failed.

---

## Common Return Codes

R01 — Insufficient Funds  
R03 — No Account  
R04 — Invalid Account Number  

Each return type requires different handling.

---

## Retry Decisions

Retries must be carefully controlled to prevent duplicate payments.

Typical rules include:

- retry only eligible return codes
- enforce retry limits
- apply idempotency safeguards

---

## Failure Handling

If a transaction cannot be retried safely, the platform:

- marks the transaction as failed
- notifies the user
- records the failure in audit logs

Operations teams may review certain cases manually.