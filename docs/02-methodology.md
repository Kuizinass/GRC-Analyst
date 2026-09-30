# 02 · Risk Assessment Methodology

This assessment follows the process in **NIST SP 800-30 Rev. 1** (*Guide for Conducting Risk Assessments*), simplified for a small organization.

## Process

1. **Identify assets**: systems and data in scope, with a focus on where ePHI is stored or moves
2. **Identify threats**: what could realistically cause harm (e.g. phishing, ransomware, misconfiguration, insider error)
3. **Identify vulnerabilities**: weaknesses a threat could exploit
4. **Assess existing controls**: what already reduces the risk
5. **Score likelihood and impact** using the scales below
6. **Calculate risk**: Likelihood × Impact (1–25)
7. **Decide treatment**: mitigate, transfer, accept, or avoid
8. **Estimate residual risk** after the recommended action

## Likelihood Scale

| Score | Rating | Definition |
|---|---|---|
| 1 | Rare | Not expected in the next 3 years |
| 2 | Unlikely | Could happen once in 2–3 years |
| 3 | Possible | Could happen within the next year |
| 4 | Likely | Expected within the next year; similar companies experience it regularly |
| 5 | Almost certain | Expected within months, or already happening |

## Impact Scale

| Score | Rating | Definition |
|---|---|---|
| 1 | Minimal | No ePHI involved; negligible cost or disruption |
| 2 | Minor | Limited internal disruption; no customer impact |
| 3 | Moderate | Short outage or small data exposure; some customers notified |
| 4 | Major | Reportable breach affecting multiple customers; significant cost and regulatory attention |
| 5 | Severe | Large-scale ePHI breach; regulatory investigation, contract losses, threat to the business |

## Risk Rating

| Score | Rating | Expected action |
|---|---|---|
| 20–25 | 🔴 Critical | Escalate to leadership; treat within 30 days |
| 12–19 | 🟠 High | Treatment plan within 90 days |
| 6–11 | 🟡 Medium | Treat within 6 months or formally accept |
| 1–5 | 🟢 Low | Monitor; acceptable with owner sign-off |

## Risk Matrix

| Likelihood ↓ / Impact → | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| **5** | 🟢 5 | 🟡 10 | 🟠 15 | 🔴 20 | 🔴 25 |
| **4** | 🟢 4 | 🟡 8 | 🟠 12 | 🟠 16 | 🔴 20 |
| **3** | 🟢 3 | 🟡 6 | 🟡 9 | 🟠 12 | 🟠 15 |
| **2** | 🟢 2 | 🟢 4 | 🟡 6 | 🟡 8 | 🟡 10 |
| **1** | 🟢 1 | 🟢 2 | 🟢 3 | 🟢 4 | 🟢 5 |

## Treatment Options

- **Mitigate**: add or improve controls to reduce likelihood or impact
- **Transfer**: shift financial impact (e.g. cyber insurance, contractual terms)
- **Accept**: formally accept with a named owner, when cost outweighs benefit
- **Avoid**: stop the activity causing the risk

## Limitations

Scores are qualitative and reflect judgment at a point in time. The top risks would benefit from quantitative analysis (e.g. FAIR) to express impact in financial terms.
