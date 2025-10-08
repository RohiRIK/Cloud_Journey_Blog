---
title: "Microsoft Threat Explorer Phishing Investigation Playbook"
meta_description: "Master Microsoft Threat Explorer with our step-by-step playbook for investigating and remediating phishing incidents. Boost your enterprise security today."
keywords: "Microsoft Threat Explorer, Phishing Investigation, Office 365 Security, Microsoft Defender, Threat Hunting, Cybersecurity, Phishing Remediation, Incident Response"
---

# Microsoft Threat Explorer Phishing Investigation Playbook

## Introduction

Phishing attacks are a constant threat to every organization. Having the right tools and a clear plan to respond is crucial. This guide provides a detailed, step-by-step playbook for using Microsoft Threat Explorer to investigate and neutralize phishing threats within your enterprise environment. Let's dive in and learn how to leverage this powerful tool to protect your organization.

## Main Content

This specialized playbook provides step-by-step instructions for using Microsoft Threat Explorer's GUI interface to investigate and remediate phishing incidents in your enterprise environment.

### Prerequisites and Access

**Required Licenses:**
- **Microsoft Defender for Office 365 Plan 2** for full Threat Explorer capabilities
- **Microsoft Defender for Office 365 Plan 1** provides Real-time Detections (limited features)

**Access URLs:**
- **Threat Explorer:** https://security.microsoft.com/threatexplorerv3
- **Real-time Detections:** https://security.microsoft.com/realtimereportsv3

### Phase 1: Initial Phishing Investigation Setup

#### Step 1: Navigate to Threat Explorer Interface
1.  **Login to Microsoft Defender Portal:** Navigate to https://security.microsoft.com
2.  **Access Threat Explorer:** Go to **Email & collaboration** > **Explorer**
3.  **Select Phish View:** Click on the **Phish** tab at the top of the interface

#### Step 2: Configure Time Range and Filters

**Set Investigation Timeframe:**
1.  **Default Range:** Shows yesterday and today's data
2.  **Custom Range:** Click the date range selector
    -   **Maximum:** 30 days of historical data
    -   **Minimum:** Current day for real-time investigation

**Apply Basic Filters:**
1.  **Property Filter Box:** Located above the main chart area
2.  **Available Filter Categories:**
    -   **Basic:** Sender address, Recipients, Subject, Sender domain
    -   **Advanced:** Internet Message ID, Network message ID, Sender IP
    -   **URLs:** Click verdict, URL domain, URL threat
    -   **Authentication:** SPF, DKIM, DMARC status

### Phase 2: Phishing Detection and Analysis

#### Step 3: Search for Specific Phishing Indicators

**User Impersonation Detection:**
1.  **Click Sender Address Filter Box**
2.  **Select "Detection Technology"** from dropdown
3.  **Choose Filter Operator:** "Equal any of"
4.  **Select Values:**
    -   **Impersonation domain**
    -   **Impersonation user**
5.  **Click Refresh** to apply filters

**Domain Impersonation Search:**
1.  **Click Sender Address Filter Box**
2.  **Select "Impersonated Domain"** from Basic section
3.  **Enter Target Domain:** (e.g., contoso.com)
4.  **Apply Filter:** Click Refresh

**Specific User Targeting:**
1.  **Select "Impersonated User"** filter
2.  **Enter Full Email Address** of targeted executive
3.  **Multiple Users:** Separate with commas
4.  **Execute Search:** Click Refresh

#### Step 4: Analyze Phishing Email Details

**Email Investigation Workflow:**
1.  **Email View Tab:** Default view showing detailed email table
2.  **Column Customization:** Click **Customize columns** button
    -   **Essential Columns:** Date, Subject, Recipient, Sender address, Threat type
    -   **Security Columns:** Detection technology, Delivery action, Latest delivery location
    -   **Investigation Columns:** Alert ID, Network message ID, URL Count
3.  **Email Details Access:**
    -   **Click Subject Line:** Opens Email summary panel
    -   **Available Actions:**
        -   **Open Email Entity:** Full message analysis
        -   **View Header:** Complete email headers
        -   **Take Action:** Immediate remediation options
        -   **Email Preview:** Visual message content (requires Preview role)
        -   **Download Email:** Full message download (requires Preview role)

### Phase 3: URL and Click Analysis

#### Step 5: Investigate Malicious URLs

**URL Analysis Interface:**
1.  **Navigate to URL Filters Section**
2.  **Click Verdict Filter:**
    -   **Blocked:** URLs prevented from opening
    -   **Blocked Overridden:** Users bypassed block warnings
    -   **Pending Verdict:** URLs under analysis
3.  **URL Investigation Views:**
    -   **Top URLs Tab:** Shows most prevalent malicious links
    -   **Top Clicks Tab:** User interaction data with Safe Links

**URL Details Investigation:**
1.  **Click URL Entry:** Opens detailed URL flyout
2.  **Available Information:**
    -   **Original URL:** Actual destination address
    -   **Threat Intelligence Verdict:** Microsoft security assessment
    -   **Active Alerts:** Related security incidents
    -   **Domain Registration:** Whois and ownership data
    -   **URL Prevalence:** Cross-tenant exposure data

#### Step 6: Export URL Click Data

**Export Workflow for Analysis:**
1.  **Select Entries:** Check boxes next to URLs of interest
2.  **Click Export Button:** Located above the data table
3.  **CSV Output Includes:**
    -   **Network Message ID:** For message correlation
    -   **Click Verdict:** User interaction outcome
    -   **Timestamp Data:** For timeline analysis

### Phase 4: Advanced Threat Hunting

#### Step 7: Use Detection Technology Filters

**Advanced Filtering Options:**
1.  **Detection Technology Filter Categories:**
    -   **Impersonation Brand:** Well-known brand spoofing
    -   **URL Detonation:** Safe Links dynamic analysis
    -   **LLM Content Analysis:** AI-powered threat detection
    -   **Mail Bombing:** Volume-based attacks
    -   **Spoof DMARC:** Authentication failures
2.  **Multi-Filter Investigation:**
    -   **Combine Filters:** Use multiple criteria simultaneously
    -   **Save Queries:** Store frequent searches (Threat Explorer only)
    -   **Property Operators:** "Equal any of," "Contains," "Does not equal"

#### Step 8: Analyze Chart Data Pivots

**Chart Visualization Options:**
1.  **Available Pivots:**
    -   **Delivery Action:** Message handling outcomes
    -   **Sender Domain:** Attack source analysis
    -   **Detection Technology:** Security layer effectiveness
    -   **Threat Classification:** Attack categorization
2.  **Interactive Analysis:**
    -   **Hover for Details:** View specific counts
    -   **Click Data Points:** Filter results by selection
    -   **Export Chart Data:** Download aggregated statistics

### Phase 5: Remediation Actions

#### Step 9: Take Immediate Response Actions

**Email Remediation Interface:**
1.  **Select Target Messages:** Check boxes in email list
2.  **Click Take Action Button:** Opens remediation wizard
3.  **Available Actions:**
    -   **Submit to Microsoft:** Report false positives/negatives
    -   **Trigger Investigation:** Launch automated AIR playbook
    -   **Delete/Quarantine:** Immediate message removal

**Automated Investigation Trigger:**
1.  **From Email Entity Page:** Click "Trigger Investigation"
2.  **From Threat Explorer:** Select messages and choose AIR action
3.  **Investigation Scope:** Last 30 days of similar emails
4.  **Playbook Automation:** Background analysis and response

#### Step 10: Monitor Investigation Progress

**AIR Integration Monitoring:**
1.  **Navigate to Action Center:** https://security.microsoft.com/action-center
2.  **Track AIR Progress:**
    -   **Pending Actions:** Require approval
    -   **Investigation History:** Completed analyses
    -   **Remediation Status:** Action outcomes

### Phase 6: Reporting and Documentation

#### Step 11: Export Investigation Data

**Comprehensive Data Export:**
1.  **Email Export Options:**
    -   **Maximum:** 200,000 filtered results
    -   **Custom Properties:** Select relevant columns
    -   **CSV Format:** Compatible with analysis tools
2.  **Export Workflow:**
    -   **Apply Filters:** Narrow to investigation scope
    -   **Select Export:** Choose data subset
    -   **Download File:** CSV with investigation results

#### Step 12: Generate Summary Reports

**Investigation Documentation:**
1.  **Top Targeted Users Export:** Up to 3,000 users with attempt counts
2.  **URL Click Analysis:** Network Message IDs for correlation
3.  **Chart Data Export:** Aggregate threat statistics
4.  **Filter Persistence:** Saved queries for ongoing monitoring

### Best Practices for Threat Explorer Usage

**Daily Monitoring Workflow:**
1.  **Check Phish View Daily:** Review overnight detections
2.  **Monitor Top Targeted Users:** Identify repeat targets
3.  **Analyze URL Click Trends:** Track user behavior patterns
4.  **Review Detection Technologies:** Assess security layer effectiveness

**Investigation Efficiency:**
1.  **Start with Broad Filters:** Narrow scope progressively
2.  **Use Chart Pivots:** Identify patterns quickly
3.  **Leverage Email Entity:** Deep-dive individual messages
4.  **Export for Analysis:** Preserve evidence and metrics

**Integration Points:**
-   **Microsoft Sentinel:** Forward Threat Explorer data for SIEM correlation
-   **Automated Investigation:** Trigger AIR for complex campaigns
-   **User Education:** Identify training opportunities from click data
-   **Policy Tuning:** Adjust security controls based on detection gaps

This Threat Explorer playbook provides comprehensive GUI-based phishing investigation capabilities, enabling security teams to efficiently detect, analyze, and respond to email-based threats using Microsoft's advanced threat hunting interface.

### Sources
- About Threat Explorer and Real-time detections in Microsoft 365 Defender https://learn.microsoft.com/en-us/defender-office-365/threat-explorer-real-time-detections-about
- Email security with Threat Explorer and Real-time detections https://learn.microsoft.com/en-us/defender-office-365/threat-explorer-email-security
- Microsoft Defender for Office 365 Security Operations Guide https://learn.microsoft.com/en-us/defender-office-365/mdo-sec-ops-guide
- How to Stop Phishing Attacks in Microsoft 365 Using Defender https://www.cyberquell.com/blog/how-to-stop-phishing-attacks-in-microsoft-365-using-defender-without-losing-your-mind
- M365 Security Best Practices: Checklist & Implementation https://www.coreview.com/blog/microsoft-365-security-best-practices-and-how-to-implement-them
- Threat hunting in Threat Explorer and Real-time detections https://learn.microsoft.com/en-us/defender-office-365/threat-explorer-threat-hunting
- What's new in Microsoft Defender for Office 365 https://learn.microsoft.com/en-us/defender-office-365/defender-for-office-365-whats-new
- Threat Explorer Useful Feature in Microsoft Defender for Office 365 https://practical365.com/threat-explorer-microsoft-defender/
- Threat Explorer https://docs.trellix.com/bundle/network-security-platform-9.2.x-product-guide/page/GUID-46AF9550-083C-4331-ABE0-4634416213BD.html
- Threat Investigation and Response in Office 365 Security https://www.nakivo.com/blog/microsoft-365-threat-investigation-and-response/
- Email Security - Administrator's Guide - Online Help Center https://docs.trendmicro.com/all/ent/tmems/vAll/en-us/Administrators
- 20 Microsoft 365 Defender Reports to Boost Your Security https://blog.admindroid.com/microsoft-365-defender-reports-can-strengthen-your-security/
- Microsoft Defender Email Preview Enables Malicious Links https://office365itpros.com/2025/04/07/email-preview-defender/
- Microsoft Defender for Office 365 Security White Paper https://ironscales.com/microsoft-defender-for-o365/report-download
- Phishing investigation https://learn.microsoft.com/en-us/security/operations/incident-response-playbook-phishing
- Deep Dive on M365 Defender https://www.hornetsecurity.com/en/blog/deep-dive-m365-defender/
- Microsoft Defender For Office 365 https://ironscales.com/guides/microsoft-365-defender/microsoft-defender-for-office-365
- Overview of Microsoft Defender Threat Intelligence with demo https://www.youtube.com/watch?v=cjrvdYByt_0
- Microsoft Defender for Office 365: Workflow, Features & Plans https://www.bluevoyant.com/knowledge-center/microsoft-defender-for-office-365-workflow-features-and-plans

## Conclusion

By following this playbook, your security team can systematically investigate phishing campaigns, understand their scope, and take decisive action. Integrating Threat Explorer into your daily security operations will significantly strengthen your defense against email-based threats. Stay vigilant, and happy threat hunting!
