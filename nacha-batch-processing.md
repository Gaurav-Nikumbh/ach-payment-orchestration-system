# NACHA Batch Processing

ACH transactions are submitted in batches rather than individually.

## Why Batching Exists

The ACH network processes payments in scheduled settlement windows.

Transactions must therefore be grouped into batch files before submission.

---

## NACHA File Structure

A NACHA file contains several sections:

- file header
- batch header
- entry detail records
- addenda records
- batch control
- file control

Each section ensures the transaction is formatted correctly for network processing.

---

## Platform Responsibilities

The payment orchestration platform is responsible for:

- grouping transactions into batches
- ensuring correct formatting
- transmitting files securely to processors

Processors then submit the batches to the ACH network.