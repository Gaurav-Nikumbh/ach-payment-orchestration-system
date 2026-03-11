# ACH Payment Lifecycle

An ACH payment moves through multiple stages before funds are settled between banks.

## Step 1 — Payment Initiation

A user initiates a payment through a digital banking interface.

Typical inputs include:

- payment amount
- receiving account details
- execution date

The request enters the platform through secure APIs.

---

## Step 2 — Validation and Authorization

The orchestration layer performs several checks:

- user authentication
- entitlement validation
- transaction limits
- account balance check via the bank core

These checks ensure the payment is eligible to proceed.

---

## Step 3 — Compliance and Risk Controls

Before submission, the platform applies:

- NACHA cutoff rules
- fraud and velocity checks
- transaction policy validation

These controls prevent invalid or risky payments from entering the network.

---

## Step 4 — Payment Scheduling

Payments may be:

- immediate
- scheduled
- recurring

Scheduled transactions are stored and triggered by background job services at the appropriate time.

---

## Step 5 — Batch File Creation

ACH transactions are grouped into NACHA batch files.

These files contain structured payment instructions and metadata required by the processor.

---

## Step 6 — Processor Submission

The NACHA batch file is transmitted to the bank's processor.

Processors submit the transactions to the ACH network.

---

## Step 7 — Clearing and Settlement

The ACH network routes the transaction between:

ODFI — originating bank  
RDFI — receiving bank

Settlement occurs based on ACH settlement windows.

---

## Step 8 — Status Updates

Processors return settlement confirmations and return files.

The platform updates transaction state and notifies users.