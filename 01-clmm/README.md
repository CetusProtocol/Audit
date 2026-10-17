# Cetus CLMM Audits

Cetus CLMM audits cover concentrated-liquidity pools, ticks, positions, swaps, fees, rewards and the integration code included in each engagement. Pool, position and tick accounting work together; configuration, upgrade and emergency capabilities govern privileged operations.

## Audit Reports

Reports are listed newest first by report date or latest follow-up date. The date column shows the review period when provided, otherwise the report date.

| Module | Auditor | Audit Duration or Date | Reviewed Commit / Scope | Report |
| --- | --- | --- | --- | --- |
| CLMM | MoveBit | 2026-09-11 - 2026-09-14 | [Reviewed: `f7f62b49b7`](#a09) | [PDF](reports/Sep%202026-CLMM%20Audit%20by%20MoveBit.pdf) |
| CLMM - Upgrade audit | Asymptotic | 2026-06-06 | [cetus_clmm v14](#asym-clmm-upgrade-2026) | [Online report](https://cetus.asymptotic.tech/clmm/upgrade-audit-v13-v14.html) |
| CLMM - Formal verification update | Asymptotic | 2026-06-06 | [cetus_clmm v14 specifications](#asym-clmm-fv-update-2026) | [Online report](https://cetus.asymptotic.tech/clmm/upgrade-fv-v13-v14.html) |
| CLMM | Asymptotic | 2025-09-15 | [Final: `a477627`](#a08) | [PDF](reports/Sep%202025-CLMM%20Audit%20by%20Asymptotic.pdf) / [Online](https://info.asymptotic.tech/cetus-clmm-audit-report) |
| CLMM | CertiK | 2025-07-31 | [4 listed revisions](#a03) | [PDF](reports/Jul%202025-CLMM%20Audit%20by%20CertiK.pdf) |
| CLMM | MoveBit | 2025-05-29 - 2025-05-30 | [2 listed revisions](#a04) | [PDF](reports/Jun%202025-CLMM%20Audit%20by%20MoveBit.pdf) |
| CLMM | OtterSec | 2024-11-15 - 2024-11-30; follow-up: 2025-05-27 - 2025-06-06 | [2 listed revisions](#a05) | [PDF](reports/Jun%202025-CLMM%20Audit%20by%20OtterSec.pdf) |
| CLMM | Zellic | 2025-03-12 - 2025-04-08 | [Reviewed: `390ee5b030`](#a02) | [PDF](reports/Apr%202025-CLMM%20Audit%20by%20Zellic.pdf) |
| CLMM | OtterSec | 2024-11-11 - 2024-11-15 | [Reviewed: `e3564d4`](#a07) | [PDF](reports/Nov%202024-CLMM%20Audit%20by%20OtterSec.pdf) |
| CLMM | OtterSec | 2023-03-30 - 2023-05-03 | [Reviewed: `11d65f5`](#a06) | [PDF](reports/May%202023-CLMM%20Audit%20by%20OtterSec.pdf) |
| CLMM | MoveBit | 2023-03-27 - 2023-04-28 | [2 listed revisions](#a01) | [PDF](reports/Apr%202023-CLMM%20Audit%20by%20MoveBit.pdf) |

A final commit is labeled where the report explicitly identifies it. Otherwise, the reviewed revision or complete revision list is reproduced below. Each report applies to its stated code and scope.

## Scope and Findings

<a id="a09"></a>
### 2026-09-14 - CLMM - MoveBit

**Scope:** PR#61 in cetus-clmm-sui; scope table lists packages/cetus_clmm/sources/config.move. Source revision is recorded in cetus-contracts.

**Code revisions recorded in the report:**
- `f7f62b49b74cf4da948c325f210638d73cdefac7`

**Source:** https://github.com/CetusProtocol/cetus-contracts

**Findings:** 0 findings in a narrowly scoped PR review

**Methodology:** Architecture review, unit testing and manual review, as listed in Project Information.

Zero findings applies to the scoped PR and config.move review.

<a id="asym-clmm-upgrade-2026"></a>
### 2026-06-06 - CLMM - Upgrade audit - Asymptotic

**Report:** [Online report](https://cetus.asymptotic.tech/clmm/upgrade-audit-v13-v14.html)

**Scope:** Review of the v13-to-v14 upgrade: pool-creation entry points, composable partner-fee claims, liquidity-event data, emergency control bounds and upgrade-stable type identities. The pinned MoveSTL and integer-mate dependencies were also checked.

**Reviewed scope / revision:** On-chain cetus_clmm version 14: `0x25ebb9a7c50eb17b3fa9c5a30fb8b5ad8f97caaf4928943acbcff7153dfee5e3`. Baseline: the final code covered by the previous manual audit, described as internal version 13.

**Results:** The report records no security findings at any severity in the reviewed upgrade.

**Methodology:** Targeted review of the upgrade delta and pinned dependencies.

<a id="asym-clmm-fv-update-2026"></a>
### 2026-06-06 - CLMM - Formal verification update - Asymptotic

**Report:** [Online report](https://cetus.asymptotic.tech/clmm/upgrade-fv-v13-v14.html)

**Scope:** Formal-verification update for deprecated and incident-response functions, new v14 entry points, reward/accrual overflow reasoning and strengthened postconditions.

**Reviewed scope / revision:** On-chain cetus_clmm version 14: `0x25ebb9a7c50eb17b3fa9c5a30fb8b5ad8f97caaf4928943acbcff7153dfee5e3`. The update builds on the previously published formal-verification report.

**Results:** The report describes proofs for the updated entry points, unconditional aborts on deprecated functions, and overflow/abort bounds promoted from assumptions to proven obligations.

**Methodology:** Formal verification of the stated specifications and postconditions.

<a id="a08"></a>
### 2025-09-15 - CLMM - Asymptotic

**Scope:** cetus_clmm directory, plus the explicitly reviewed MoveSTL and integer-mate dependencies.

**Final reviewed commit:** `a477627`.

**Code revisions recorded in the report:**
- `6b277ca (initial; cetus-for-audit)`
- `a477627 (final; cetus-contracts)`
- `b1418ed (MoveSTL final)`
- `09a12d9 (integer-mate final)`

**Source:** Initial cetus-for-audit; final cetus-contracts; MoveSTL and integer-mate as specified in report

**Findings:** 8 low and 12 advisory findings; remediated and acknowledged dispositions as recorded in the report.

**Methodology:** Move smart-contract review, with findings, recommendations and remediation records in the report.

The report summary says findings were adequately addressed. Individual dispositions include acknowledged L-7, A-1, A-2 and A-10; A-10 is described as partially fixed.

<a id="a03"></a>
### 2025-07-31 - CLMM - CertiK

**Scope:** Twelve CLMM files listed in the scope table, including recovery-related functionality. Review notes exclude the listed Sui/MoveSTL/IntegerMate dependencies.

**Code revisions recorded in the report:**
- `390ee5b030de44a782dc0fc6f23061611a92a64b`
- `4b243d4bb07aaed89dd44d8f1991cb9a54a5f586`
- `bda1995f7f704548c2c3954fa3014dc38c3f4c26`
- `0df3adad7d3e41c24e64e418d38173c48221fe32`

**Source:** https://github.com/CetusProtocol/cetus-clmm-sui

**Findings:** 17 findings: 13 resolved and 4 acknowledged; separate optimization entries.

**Methodology:** Manual review and static analysis.

Centralization is retained as a separate finding category. Optimizations are listed separately in the report.

<a id="a04"></a>
### 2025-06-16 - CLMM - MoveBit

**Scope:** factory.move, config.move, pool_creator.move, pool.move and positon_snapshot.move under cetus_clmm/sources, as printed in section 1.2.

**Code revisions recorded in the report:**
- `11ea0aec59a8edcf813a744797e64f58cf84d99c`
- `8437040e7a22bf11c8525d801d83f37300dc7d90`

**Source:** https://github.com/CetusProtocol/cetus-clmm-sui

**Findings:** 3 findings: 2 fixed, 1 acknowledged

**Methodology:** Architecture review, unit testing and manual review, as listed in Project Information.

The scope table repeats factory.move with different hashes; filenames are reproduced as printed.

<a id="a05"></a>
### 2025-06-06 - CLMM - OtterSec

**Scope:** cetus-clmm-sui at e3564d4; additional review of PR#1, PR#2 and compensation-repository revision 3eab21e.

**Code revisions recorded in the report:**
- `e3564d4`
- `3eab21e (compensation repository); PR#1 and PR#2 also reviewed`

**Source:** https://github.com/CetusProtocol/cetus-clmm-sui

**Findings:** 10 findings: 2 low vulnerabilities resolved, 8 informational with entry-specific dispositions

**Methodology:** Design and implementation review; methodology is described in the Procedure appendix.

Includes the May-June 2025 follow-up. Finding identifiers must be read within this report.

<a id="a02"></a>
### 2025-04-11 - CLMM - Zellic

**Scope:** cetus_clmm/sources/**.move and integrate/sources/**.move. Frontend, infrastructure and key custody excluded.

**Code revisions recorded in the report:**
- `390ee5b030de44a782dc0fc6f23061611a92a64b`

**Source:** https://github.com/CetusProtocol/cetus-clmm-sui

**Findings:** 3 informational, all acknowledged

**Methodology:** Manual review and automated testing, with coding, business-logic, integration and code-maturity analysis.

<a id="a07"></a>
### 2024-11-19 - CLMM - OtterSec

**Scope:** cetus-clmm-sui at e3564d4, including pool creation and code maturity.

**Code revisions recorded in the report:**
- `e3564d4`

**Source:** https://github.com/CetusProtocol/cetus-clmm-sui

**Findings:** 2 informational findings; dispositions are recorded in the individual entries.

**Methodology:** Design and implementation review; methodology is described in the Procedure appendix.

<a id="a06"></a>
### 2023-05-03 - CLMM - OtterSec

**Scope:** Sui CLMM program at 11d65f5.

**Code revisions recorded in the report:**
- `11d65f5`

**Source:** https://github.com/CetusProtocol/cetus-clmm-sui

**Findings:** 9 findings: 1 high and 1 medium resolved; 7 informational with mixed dispositions

**Methodology:** Design and implementation review; methodology is described in the Procedure appendix.

<a id="a01"></a>
### 2023-04-28 - CLMM - MoveBit

**Scope:** CLMM core/math, integrations, manifests and selected utility modules; Appendix 1 supplies last-reviewed file hashes.

**Code revisions recorded in the report:**
- `11d65f5da993bf0bbc06cfd6591f833a10b842fd`
- `0f6514e922fd9aed0efe9b0bfb57e348de534c0e`

**Source:** https://github.com/CetusProtocol/cetus-clmm-sui

**Findings:** 18 fixed: 1 critical, 2 major, 3 medium, 12 minor

**Methodology:** Architecture review, unit testing and manual review, as listed in Project Information.

Acknowledged findings are recorded separately from fixed or resolved findings. Audit reports apply to the reviewed versions and do not cover subsequent changes automatically.

## Formal Verification Reports

The following report is maintained online and is labeled current by Asymptotic's project index. It has no publication date, so it is listed separately from the dated audit history.

| Report | Auditor | Audit Duration or Date | Reviewed Revision | Link |
| --- | --- | --- | --- | --- |
| CLMM Comprehensive Formal Verification | Asymptotic | Current (undated) | [`6b277ca39cf8110dc19da74c8888560444d35067`](https://cetus.asymptotic.tech/clmm/fv-report.html#reproducibility) | [Online report](https://cetus.asymptotic.tech/clmm/fv-report.html) |

**Scope:** CLMM core arithmetic, tick conversion, pool/position lifecycle, balance-sheet operations, fee/reward accounting, access controls and emergency behavior.

**Methodology:** Sui Prover 1.5.3 with function specifications, preconditions/postconditions and Lean 4 tick-math proofs.

**Coverage limits:** The report identifies some entry points as structurally modeled without exhaustive postcondition proofs. Off-chain systems, oracle accuracy and governance processes beyond on-chain role enforcement are outside scope.

