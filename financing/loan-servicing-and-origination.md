# Loan Servicing & Origination

NordBanking's Loan Servicing module allows credit specialists to issue, monitor, and settle digital credit agreements and drawdown facilities. Platform users can onboard borrowers, structure amortization terms, attach underwriting documents, and execute direct repayment processing from a central portfolio ledger.

### Loan Portfolio Ledger

Selecting _Loans & Credit_ from the primary menu displays real-time metadata for all active and pending facilities:

* _**Loan Ref ID**_ – Unique alphanumeric identifier for tracking and legal documentation.
* _**Borrower**_ – Legal entity or individual assigned to the credit facility.
* _**Principal Amount**_ – Total financed sum, including applicable origination and service fees.
* _**Status**_ – Current lifecycle state (e.g., Underwriting, Approved, Active, Delinquent, Settled).
* _**Funding Date**_ – Date funds were disbursed to the borrower.
* _**Maturity Date**_ – Final settlement deadline for outstanding principal and interest.
* _**Repayment Terms**_ – Schedule governing debt servicing (e.g., Monthly Amortization, Net 30, Interest-Only).

***

### Issuing a Credit Facility

#### 1. Initiate Facility

Navigate to _Loans & Credit_ and select _+ Issue Loan Facility_.

#### 2. Configure Parameters

_External Reference Identifier_ Custom alphanumeric reference (up to 8 characters) to override the auto-generated Loan Ref ID for external core banking or legacy system syncs.

_Borrower Profile_ Select an existing borrower or click _Add Borrower_ to configure a new profile:

* _Entity Type_ – Classify as Individual or Commercial Entity.
* _Account Status_ – Set to Active or Under Review.
* _Tax ID / SSN / EIN_ – 9-digit official tax identification number.
* _Risk Rating_ – Internal credit risk classification.
* _Contact & Routing_ – Email, mobile contact, billing address, and settlement bank details.

_Repayment & Maturity Schedule_

* _Funding Date_ – Date of primary capital release.
* _First Payment Due_ – Select standard payment cycles (Upon Disbursement, Net 15, Net 30, Net 60, or Custom Date).
* _Origination Ref_ – Associated purchase order or underwriting clearance code.
* _Auto-Debit Pay_ – Enable automated Clearing House (ACH) or credit card pull for recurring installments.

_Disbursement Allocation & Line Items_ Define capital distribution by selecting _+ Add Allocation_:

* _Component_ – Label allocation types (e.g., Net Principal Release, Origination Fee, Escrow Reserve).
* _Allocation Amount_ – Financed sum assigned to the specific component.
* _Interest & Fee Overrides_ – Apply specific sub-rates or local tax surcharges per item.

_Underwriting Documents_ Upload required credit checks, tax filings, or executed promissory notes using the _Upload_ panel.

#### 3. Finalize Agreement

* _Save Draft_ – Retains agreement configuration without releasing funds or alerting the borrower.
* _Approve & Send_ – Issues the binding loan offer directly to the borrower via secure portal email.
* _Disburse & Collect Fee_ – Triggers fund distribution and processes initial origination charges.

***

### Servicing Active Loans

To collect an installment or manual balance payoff for an active loan:

1. Select the relevant record from the _Loan Portfolio Ledger_.
2. Click _+ Record Repayment_.
3. Select payment rail (ACH, Wire Transfer, Direct Debit), enter payment details, and click _Process Charge_.
