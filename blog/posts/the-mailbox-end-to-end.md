# The Mailbox End to End: What AmritFlow Does Today

*By the AmritFlow Team*

Most conversations about AP automation start with the ERP. They shouldn't.

The ERP is the system of record. It is where invoices are posted, payments are scheduled, and ledgers are balanced. But the ERP never sees the mess that arrives before it. It does not see the shared mailbox with 400 unread messages. It does not see the supplier who sends one PDF containing twelve invoices. It does not see the "urgent bank change" email that looks almost exactly like the vendor's real domain.

That mess is where the work lives. That is where the delays begin. That is where fraud enters.

AmritFlow sits at that front door. It reads the mailbox, triages what arrives, extracts what matters, checks it against policy, flags what looks wrong, and learns from every decision the team makes. All of it runs on the client's own infrastructure. Nothing leaves the building.

Here is what the system does today — and what your AP team can do with it.

## Reading the Mailbox

AmritFlow connects to a supplier mailbox over IMAP — Gmail, Outlook, or any provider that supports an app password. It pulls every new email and parses what arrives: headers, attachments, dates, sender domain. It verifies SPF and DKIM at intake.

Critically, it reads emails without marking them as read in the mailbox itself. Your team's existing view stays untouched. Nothing is disturbed while the system works alongside it.

**What your AP team can do:** No one opens the shared mailbox manually anymore. Every incoming email is already captured, timestamped, and categorized the moment it lands.

**How this helps our clients:** Their teams stop losing time to manual mailbox monitoring. Nothing slips through between shifts, and no email sits unopened for days. For a shared services centre handling thousands of supplier messages a month, this alone removes hours of low-value work from every operator's day — and it does so without changing how the mailbox itself behaves.

## Triage and Classification

Not every email is an invoice. AmritFlow splits inbound mail into two streams: emails with attachments, which enter the invoice path, and emails without attachments, which enter the query path.

For the query path, a keyword scan looks for urgency signals, bank-change requests, disconnection notices, and service interruption language. Each email receives a priority — P1, P2, or P3.

**What your AP team can do:** The queue arrives already sorted. Urgent items sit at the top. Bank-change requests are flagged the moment they arrive. No one has to read every email just to find the ones that matter.

**How this helps our clients:** Their most experienced people stop spending mornings sorting noise. Urgent supplier issues get attention within minutes, not hours. And the bank-change flags mean the highest-risk category of email — the one most commonly used in payment fraud — is separated from routine traffic before anyone opens it.

## Unbundling the Documents

Supplier PDFs are not tidy. One attachment can contain a dozen invoices. Some files are corrupt. Some are scanned badly. Some are password-protected.

AmritFlow opens each PDF attachment, validates its integrity, and quarantines anything corrupt rather than letting it silently fail. When a PDF contains multiple invoices, the system splits it into individual invoice pages and extracts the key fields from each: invoice number, PO number, and SES number.

**What your AP team can do:** A supplier sends one PDF with twelve invoices inside. The system turns it into twelve separate records. Each one is processed on its own. Nothing gets buried, and nothing gets missed.

**How this helps our clients:** Multi-invoice PDFs are one of the most common sources of missed payments in AP. When twelve invoices are bundled into one attachment, the ones at the back are often processed late or not at all. AmritFlow removes that failure mode entirely. Late payment fees drop, supplier relationships improve, and nothing depends on whether an operator scrolled to page nine.

## Distributing the Work

Verified invoices are grouped into batches, capped at fifteen per batch. Each batch is assigned to a processor and written to a tracker.

**What your AP team can do:** Work is distributed evenly. No processor is overloaded. No batch exceeds what a person can handle in one cycle. Your team stops managing the queue manually and starts working through it.

**How this helps our clients:** Supervisors stop spending their day allocating work. Capacity becomes visible. When one processor is out, the load redistributes without intervention. For clients running multi-shift operations, this means the handover between shifts is clean — each operator knows exactly what is theirs, and nothing falls between them.

## Checking Against Policy

Every invoice is checked against business tolerances, duplicate detection, and compliance rules. The system returns one of three outcomes: **Approved**, **Review Required**, or **Blocked**.

**What your AP team can do:** Most invoices clear without anyone touching them. Exceptions surface before payment. Duplicates and out-of-policy items never reach the ERP without a human reviewing them first.

**How this helps our clients:** Duplicate payments are one of the quietest forms of financial leakage in AP — and one of the hardest to catch manually. Policy checks run before payment, not after. Auditors get a consistent, rule-based record of every decision. And controllers can tighten or loosen tolerances without retraining the team, because the rules live in the system, not in people's heads.

## Working Together, Without Collisions

Multiple operators work the same mailbox without stepping on each other. AmritFlow uses atomic locks on each email: the first person to open an item holds the lock, and everyone else sees it as read-only. Roles are separated into working, observing, and developer. Session history is visible. Developers can force-end a session if needed. Every action is logged.

**What your AP team can do:** If one operator opens an invoice, another sees it is locked. Nothing gets worked twice. Nothing gets lost between shifts. Every action leaves a record.

**How this helps our clients:** Duplicate effort is invisible waste. Two operators processing the same invoice does not just cost time — it creates confusion in the audit trail. Atomic locking removes this entirely. For regulated clients, the session log becomes an evidence trail: who touched what, when, and what they did. That is exactly the kind of record an internal auditor asks for.

## Handling the Replies

For emails without attachments — supplier queries, clarifications, requests — AmritFlow provides a reply overlay. Replies are composed and sent. Every email can be marked as Handled, Escalated, or Ignored. Each action captures a training remark.

**What your AP team can do:** Supplier queries are handled without leaving the tool. Bank-change requests get escalated. Noise gets ignored. And every decision your team makes feeds the system's learning.

**How this helps our clients:** Supplier queries currently live in a dozen different places — personal inboxes, chat threads, sticky notes. AmritFlow keeps them in one place, tied to the mailbox they arrived in. Escalations follow a defined path. And every resolution becomes a training signal, which means the next identical query is handled faster than the last.

## Learning From Every Decision

This is the part that changes over time.

Every human decision is recorded into a corpus. A pattern engine computes confidence scores for each pattern, based on how often it appears and how consistently the team responds. A classifier then suggests an action for the next similar email. A draft engine pre-fills replies.

**The Earned Autonomy Framework:**

> 1. Human Acts → 2. System Proposes → 3. Human Approves → 4. System Executes

**What your AP team can do:** The system learns from their judgment. What once took five minutes becomes a one-click approval. Over time, your team's decisions become the system's playbook — and the repetitive layer starts to disappear.

**How this helps our clients:** This is where the economics change. Month one looks like assisted processing. Month six looks like a system that handles the predictable 60 to 70 percent on its own. The team's headcount does not change — but what those people do changes entirely. Instead of typing, they are reviewing, deciding, and improving the system. Automation becomes an asset that appreciates with use, not a set of rules that decays every time the business changes.

## Catching Fraud Before Payment Leaves

AmritFlow runs a fraud scan across the mailbox. It checks for SPF, DKIM, and DMARC failures. It looks for Reply-To mismatches, Return-Path mismatches, lookalike domains, display-name spoofing, unusual send times, attachment type mismatches, and bank-change requests buried in email bodies.

Each finding maps to a specific action: hold, flag, escalate, or callback.

**What your AP team can do:** Suspicious emails are surfaced before processing. Bank-change requests require a callback. Lookalike domains get blocked. This is the layer that catches fraud while it is still an email — before it becomes a payment.

**How this helps our clients:** Business email compromise is the single most expensive category of fraud in accounts payable. It does not rely on sophisticated technology. It relies on a tired operator missing a subtle domain difference at 4:30 PM on a Friday. AmritFlow does not get tired. It checks every email against ten signals, every time, and routes high-risk items to a callback before any payment instruction is acted on. For a CFO, this is the difference between a control that is documented and a control that is enforced.

## Knowing What the System Is Doing

During the pilot period, a live banner tracks progress. Emails received. Invoices extracted. Exceptions flagged. Both sides see exactly how much the system is processing, in real time.

**What your team can do:** Proof of value from day one. No waiting for a quarterly review to know whether the system is working.

**How this helps our clients:** Procurement decisions stall when value is invisible. The pilot tracker makes value visible from the first week — emails processed, invoices extracted, exceptions caught. By the end of the pilot, the client is not deciding based on a vendor's promise. They are deciding based on their own data, captured on their own infrastructure, in their own environment.

## Running Entirely on Your Infrastructure

AmritFlow runs on your own hardware. No cloud. No external API calls in the base product. Zero egress. Local database. Local logs. Local learning corpus.

The LLM slot is reserved but disabled by default. Clients who want LLM-enabled extraction can run a local model on their own hardware. Nothing is sent anywhere.

**What your team can do:** Invoices, vendor bank details, and payment amounts never leave your infrastructure. Your IT team can verify it with a network monitor. For regulated buyers in BFSI, pharma, and government, this is the only architecture that passes.

**How this helps our clients:** Data residency is no longer a preference. It is a board-level mandate and, in many sectors, a regulatory requirement. AmritFlow lets clients adopt advanced automation without triggering a data protection review, without signing a new processor agreement, and without adding a third party to their vendor risk register. For regulated buyers, this is not a feature. It is the reason the project can proceed at all.

## Installing in Under an Hour

Setup is a single command. The installer checks prerequisites, creates folders, initializes the database, and installs the default configuration. A launcher starts the system.

Your IT team extracts the package, runs the setup script, and the product is live. No development environment. No manual configuration.

**What your team can do:** The system is running the same day it is delivered.

**How this helps our clients:** Enterprise software deployments usually mean weeks of integration work, professional services fees, and a change management programme. AmritFlow is extracted, installed, and running in under an hour, on infrastructure the client already owns. Proof of value does not require a procurement cycle. It requires one afternoon.

## What This Means

AmritFlow today is a sovereign AP intake, triage, extraction, batching, policy, fraud-detection, and learning system that runs on your own server. It handles the mailbox end to end — from email to reviewed invoice — with a full audit trail and zero data leaving the building.

It does not replace the ERP. It does not replace your team. It removes the layer of work that should never have been manual in the first place.

**AmritFlow. Sovereign by design. Intelligent by observation.**

---

*This post describes AmritFlow Stream as it operates today. [Request a 14-day shadow pilot →](../index.html#engagement)*
