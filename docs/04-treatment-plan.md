# 04 · Risk Treatment Plan

Prioritized by risk score, then by effort. The first 30 days focus on the changes that remove the most risk for the least cost.

## Phase 1: First 30 Days (Critical + quick wins)

| Risk | Action | Owner | Effort | Score change |
|---|---|---|---|---|
| R-01 | Enforce phishing-resistant MFA for all staff; block legacy sign-in | IT Manager | Low | 20 → 8 |
| R-04 | Sign a BAA with the SMS vendor, or stop sending ePHI until signed | Compliance Manager | Low | 12 → 6 |

## Phase 2: Within 90 Days (High)

| Risk | Action | Owner | Effort | Score change |
|---|---|---|---|---|
| R-02 | Just-in-time production access; quarterly access reviews | CTO | Medium | 15 → 8 |
| R-03 | Automated cloud configuration monitoring; storage settings as code | CTO | Medium | 15 → 8 |
| R-05 | Quarterly restore tests; isolated, immutable backup copies | CTO | Medium | 15 → 6 |
| R-06 | High-priority alerts, weekly log review owner, 1-year retention | CTO | Medium | 12 → 6 |
| R-09 | Automated deprovisioning from HR system; monthly leaver audit | IT Manager | Medium | 12 → 4 |

## Phase 3: Within 6 Months (Medium)

| Risk | Action | Owner | Effort | Score change |
|---|---|---|---|---|
| R-07 | Enforce full-disk encryption; replace CSV exports with in-app reporting | IT Manager | Low | 8 → 3 |
| R-08 | Dependency scanning in the build pipeline; patch timelines by severity | CTO | Medium | 9 → 4 |
| R-10 | Add HIPAA breach notification steps to IR plan; annual tabletop | Compliance Manager | Low | 8 → 4 |

## Accepted Risks

| Risk | Rationale | Accepted by | Review |
|---|---|---|---|
| R-11 | No ePHI or production systems on premises; remote-first workforce | CTO | Annually |

## Tracking

Progress is reviewed monthly by the Compliance Manager and reported to leadership quarterly. Each completed action requires evidence (e.g. MFA enrollment report, access review sign-off, restore test record) before the residual score is accepted.
