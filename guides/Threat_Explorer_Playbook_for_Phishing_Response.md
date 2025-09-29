# Threat Explorer Playbook for Phishing Response

This playbook provides a practitioner‑focused guide to using Microsoft 365 Defender Threat Explorer to detect, investigate, and remediate phishing at scale. It emphasizes actionable pivots, precise filtering, and bulk remediation to minimize time‑to‑containment, while preserving exports and auditable records for reporting and post‑incident review.

<aside>
🛡️

Audience: Security Operations Center (SOC) analysts and Incident Response (IR) responders. The guidance assumes operational familiarity with Microsoft 365 Defender and focuses on efficient triage, scoping, containment, and evidence handling.

</aside>

### Role Objectives

- SOC: Triage alerts, confirm scope, initiate containment, escalate with evidence
- IR: Lead scoping and eradication, coordinate approvals, finalize reports and lessons learned

### Prerequisites and Access

- Licensing: Microsoft Defender for Office 365 Plan 2 is required for the full Threat Explorer feature set. Plan 1 provides Real‑time detections only.
- Entry points:
    - Threat Explorer: https://security.microsoft.com/threatexplorerv3`
    - Real‑time detections: https://security.microsoft.com/realtimereportsv3`

### Phase 1: Prepare the Investigation Surface

### 1. Open Threat Explorer

1. Sign in to the Microsoft Defender portal at https://security.microsoft.com`.
2. Navigate to Email & collaboration → Explorer.
3. Select the Phish view.

### 2. Establish Scope and Baselines

- Time range: Use Yesterday–Today for routine monitoring. For incident scoping, set a custom range (up to 30 days).
- Core filters:
    - Basic: Sender address, Recipient, Subject, Sender domain
    - Advanced: Internet message ID, Network message ID, Sender IP
    - URL: Click verdict, URL domain, URL threat type
    - Authentication: SPF, DKIM, DMARC status

### Phase 2: Identify and Analyze Campaigns

### 1. Hunt for Impersonation and Targeting

- User impersonation: Detection Technology → Equal any of → Impersonation domain, Impersonation user → Refresh
- Domain impersonation: Basic → Impersonated Domain → [contoso.com](http://contoso.com) → Refresh
- Executive targeting: Impersonated User → [user@domain.com](mailto:user@domain.com)[, [user2@domain.com](mailto:user2@domain.com)] → Refresh

### 2. Examine Message Details

- Use Email view. Customize columns to include Date, Subject, Recipient, Sender, Threat type, Detection technology, Delivery action, Final delivery location, Alert ID, Network message ID, URL count.
- Open a message via Subject to access:
    - Open Email Entity
    - View header
    - Take action
    - Email preview and Download email (Preview role required)

### Phase 3: URL and Click Analysis

### 1. Investigate Malicious URLs

- Verdict filter: Blocked, Blocked overridden, Pending verdict
- Pivot views:
    - Top URLs: Prevalent malicious links
    - Top Clicks: User interaction with Safe Links
- URL entity details: Original URL, Threat intelligence verdict, Active alerts, Domain registration, URL prevalence

### 2. Export Click Telemetry

- Select rows → Export → CSV includes Network message ID, Click verdict, Timestamps

### Phase 4: Advanced Threat Hunting

### 1. Leverage Detection Technologies

- Examples: Impersonation brand, URL detonation, LLM content analysis, Mail bombing, Spoof DMARC
- Combine operators (Equal any of, Contains, Does not equal) and save frequent searches in Threat Explorer.

### 2. Use Analytical Pivots

- Charts: Delivery action, Sender domain, Detection technology, Threat classification
- Interactions: Hover for counts, click to filter, export underlying data

### Phase 5: Response and Containment

### 1. Execute Remediation

- In list view: Select messages → Take action (wizard)
- Options:
    - Submit to Microsoft (tune detections)
    - Trigger investigation (AIR playbook)
    - Delete or Quarantine
- AIR scope: Looks back 30 days, correlates similar artifacts, and automates analysis and responses

### 2. Track Remediation and Approvals

- Action center: https://security.microsoft.com/action-center`
    - Pending actions (approval queue)
    - Investigation history
    - Remediation status

### Phase 6: Reporting and Evidence Management

### 1. Export Investigation Results

- Up to 200,000 filtered email results per export
- Choose columns, export to CSV for downstream analytics

### 2. Produce Executive and SOC Summaries

- Top targeted users (up to 3,000)
- URL click analysis with Network message IDs
- Chart data exports for trend reporting
- Reuse saved filters for continuous monitoring

### Operational Best Practices

- Daily cadence:
    - Review Phish view
    - Monitor top targeted users
    - Track URL click trends
    - Inspect detection technology distribution
- Investigation workflow:
    - Start broad, then narrow
    - Use chart pivots to reveal patterns
    - Deep‑dive via Email entity
    - Export data to preserve evidence and metrics
- Integrations and tuning:
    - Stream Explorer data into Microsoft Sentinel for SIEM correlation
    - Use AIR for large or fast‑moving campaigns
    - Feed click telemetry into user awareness programs
    - Tune policies based on observed gaps

---

This playbook enables security teams to move decisively from detection to containment, maintain a defensible audit trail, and continuously improve email security posture.
