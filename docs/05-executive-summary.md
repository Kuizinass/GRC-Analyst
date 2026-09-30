# 05 · Executive Summary

**To:** Northwind Health Leadership Team
**Subject:** Cybersecurity risk assessment: key findings and decisions needed
**Date:** September 2026

## The Short Version

Northwind holds sensitive health information for around 1.2 million patients. We found **one critical risk and six high risks** that could lead to a reportable data breach, customer contract losses, or a regulatory investigation. Most can be fixed within 90 days, mainly with process changes and tools we largely already pay for.

## What Could Go Wrong

1. **A staff member falls for a phishing email and an attacker takes over their account.** Not every account is protected by strong multi-factor sign-in. This is the most likely route to a breach at a company like ours.
2. **Patient data is exposed through our own systems.** Too many people have standing access to patient records, and cloud settings are changed by hand with no automated checks.
3. **We can't recover quickly from ransomware.** We back up daily, but we have never tested restoring those backups.
4. **A supplier handles patient data without the legally required agreement.** Our SMS reminder provider receives patient names and appointment times without a signed Business Associate Agreement.

## What We Recommend

| Timeframe | Action | Why it matters |
|---|---|---|
| **30 days** | Strong multi-factor sign-in for all staff; sign the SMS vendor agreement | Removes our only critical risk and a clear compliance gap |
| **90 days** | Tighten access to patient data, automate cloud checks, test backups, improve monitoring, automate leaver access removal | Addresses all six high risks |
| **6 months** | Encrypt all laptops, automate software patching checks, test our incident response plan | Closes remaining medium risks |

## What We Need From You

- **Approve** the 30-day actions, which need no new budget
- **Approve** an estimated budget for backup isolation and cloud monitoring tooling (detailed costing to follow)
- **Confirm** that these actions support our SOC 2 Type II timeline, which three enterprise customers have made a condition of renewal

## After These Actions

All critical and high risks fall to medium or low, putting Northwind in a much stronger position for HIPAA compliance, our SOC 2 audit, and customer renewals.
