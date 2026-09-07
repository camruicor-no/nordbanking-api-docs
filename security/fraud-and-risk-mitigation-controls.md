# Fraud & Risk Mitigation Controls

{% hint style="danger" %}
Note to readers:<br>

* The following technical writing sample includes AI-generated spoof screenshots.
* This technical writing sample has been edited to conceal company information, susceptible to non-disclosure agreements
{% endhint %}

## Fraud & Risk Mitigation Controls

Configurable risk mitigation rules protect account holders and institutional assets by enforcing step-up verification for card-present, card-not-present (CNP), and remote check transactions. Enforcing strict security parameters lowers overall fraud exposure, minimizes chargeback liability, and enables automated real-time transaction blocks.

### Prerequisites

Access to risk configuration parameters requires one of the following administrative roles:

* System Administrator
* Risk Officer
* Compliance Supervisor

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### Transaction Security Parameters

#### Card-Present & Terminal Security

Applies to in-person terminal and swipe transactions:

* PAN Verification (Last 4 Digits) – Requires operators or terminal users to manually re-enter the last four digits of the payment card to verify physical card authenticity against magnetic stripe or chip data.

#### Remote & Manual Entry Security (Card-Not-Present)

Enforces step-up authentication when processing manually keyed or online banking transactions:

* CVV/CVC Security Code – Mandates input of the 3-digit or 4-digit card verification code.
* Postal Code (AVS) – Requires the billing postal code associated with the account. Mandatory for all corporate and commercial account transactions.
* Street Address Number (AVS) – Validates the numeric portion of the account holder's registered billing address.

#### Digital Check Capture Controls

Applies to mobile check deposits and remote check clearing:

* Contact Phone Number – Requires input of a verified phone number for the check drawer prior to submission.
* Check Sequence Number – Mandates manual entry of the physical check number to enforce duplicate check detection across clearing networks.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

### Configuring Risk & Security Parameters

Follow these steps to update transaction controls and modify authorization thresholds.

1. **Log** into the administrative console. From the main navigation menu, select **Risk & Compliance**, then click **Policy Management** > **Transaction Security**.
2. **Toggle** the required parameters for each operational channel to _Enabled_:

* Under **Card-Present Controls**, **check PAN Verification (Last 4 Digits)**.
* Under **CNP & Manual Entry**, **enable CVV/CVC Security Code, Postal Code (AVS),** and **Street Address Number (AVS)**.
* Under **Digital Check Capture Controls**, **enable Contact Phone Number** and **Check Sequence Number**.

3. To configure automated decline triggers, **scroll** to the **Real-Time Auto-Decline** section. **Toggle** the active switches to _On_ for each mismatch trigger you want to enforce.
4. **Review** your parameter changes, then **click Save Policy** at the bottom of the dashboard.&#x20;
5. When prompted by the system modal, **click Confirm Deployment** to push the updated rules to the core authorization engine.

### Real-Time Auto-Decline Triggers

Automated risk rules evaluate Address Verification Service (AVS) and card code (CVV) responses in real time. Enabling these triggers instructs the core authorization engine to automatically reject transactions that fail validation:

| **Security Trigger**       | **Engine Behavior**                                              | **Risk Impact**                              |
| -------------------------- | ---------------------------------------------------------------- | -------------------------------------------- |
| CVV Mismatch Block         | Instantly declines transactions when the card code fails.        | Prevents unauthorized stolen card usage.     |
| Postal Code Mismatch Block | Instantly declines transactions when the billing ZIP code fails. | Mitigates card-not-present fraud.            |
| Address Mismatch Block     | Instantly declines transactions when the street number fails.    | Prevents identity theft and synthetic fraud. |

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:**

Disabling an auto-decline rule permits mismatched transactions to process, shifting fraudulent liability to the institution. For optimal risk coverage, ensure the fields set as mandatory in your manual entry controls directly match your active auto-decline triggers.
{% endhint %}
