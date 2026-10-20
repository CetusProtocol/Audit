# Cetus DLMM Audits

Cetus DLMM audits cover bin-based liquidity, pool and position accounting, price calculations, rewards and router code where included. Utility-library coverage is specific to each engagement.

## Audit Reports

Reports are listed newest first by report date or latest follow-up date. The date column shows the review period when provided, otherwise the report date.

| Module | Auditor | Audit Duration or Date | Reviewed Commit / Scope | Report |
| --- | --- | --- | --- | --- |
| DLMM | CertiK | 2026-10-16 | [Reviewed: `4f6e1fd913`](#certik-dlmm-2026-10-16) | [PDF](reports/Oct%202026-DLMM%20Audit%20by%20Certik.pdf) |
| DLMM - Upgrade audit | Asymptotic | 2026-06-06 | [cetus_dlmm v9](#asym-dlmm-upgrade-2026) | [Online report](https://cetus.asymptotic.tech/dlmm/upgrade-audit-v8-v9.html) |
| DLMM - Manual audit | Asymptotic | 2026-01-15 | [cetus_dlmm and dlmm_router; linked by the project index](#asym-dlmm-manual-2026) | [Online report](https://info.asymptotic.tech/Cetus-DLMM-Audit-Report-294159bbd66d8039a322f6fd936b66b8) |
| DLMM | Asymptotic | 2025-11-21 | [Final: `974933c29a`](#a11) | [PDF](reports/Nov%202025-DLMM%20Audit%20by%20Asymptotic.pdf) |
| DLMM | OtterSec | 2025-09-17 - 2025-10-21 | [3 listed revisions](#a12) | [PDF](reports/Nov%202025-DLMM%20Audit%20by%20OtterSec.pdf) |
| DLMM | CertiK | 2025-09-30 | [Final: `cd0c803861`](#a13) | [PDF](reports/Sep%202025-DLMM%20Audit%20by%20Certik.pdf) |
| DLMM | MoveBit | 2025-07-21 - 2025-09-25 | [14 listed revisions](#a14) | [PDF](reports/Sep%202025-DLMM%20Audit%20by%20MoveBit.pdf) |

A final commit is labeled where the report explicitly identifies it. Otherwise, the reviewed revision or complete revision list is reproduced below. Each report applies to its stated code and scope.

## Scope and Findings

<a id="certik-dlmm-2026-10-16"></a>
### 2026-10-16 - DLMM - CertiK

**Report:** [October 2026 security assessment](reports/Oct%202026-DLMM%20Audit%20by%20Certik.pdf)

**Scope:** DLMM core contracts and Cetus-maintained utility functions reviewed in the DLMM context. The appendix lists the reviewed files across the reported revisions; external framework dependencies retain the report's stated assumptions.

**Code revisions recorded in the report:**
- `57ba7dc0c7471d99e911202bb68762373c8e79f4`
- `160846ec4eb36bd5b9db416c015069a8c7d7e759`
- `f442ca0db0bd8c0e502029831fe3a1a2e960d038`
- `80530ae53d162e4da26aeb665de305e17fb7768e`
- `098cf12dcf1a499362592e7faf1c84473313d936`
- `4acdcb59b3ca08981c035459cc4de787a783d6b0`
- `bdd18518b29fb17e55b33566ebd90f18e243c44f`
- `abf32f00e8ff039833f0a4da9110d75ce21c05aa`
- `81af9930a0341a689b71dea6c39bad0a3997b08d`
- `cd0c803861e569be4a50defba26ca9d10725272c`
- `d1037ffc7ff7ffd314411d1a723aab0e2551d290`
- `324397b6df2d2af9444024482890d0bcf6fdb706`
- `741b9240616961549305c56074de9e467fdfd270`
- `2fba63d1dddbdd89cb9b59241af7d2f077544f6f`
- `0bf9b507c40c3c91c080354d1528053d8d1befb6`
- `f317a94e34ebe558226027543884ec27a9b81285`
- `e43f85791b90c54c54d3d494f2c225f6df85d2c3`
- `4f6e1fd913b1439ad6bcf903ee8ca8a12694238b`

**Source:** https://github.com/CetusProtocol/cetus-dlmm

**Findings:** 46 findings: 35 resolved and 11 acknowledged. Both major and both medium findings are resolved. Minor findings: 13 resolved and 3 acknowledged. Informational findings: 18 resolved and 7 acknowledged. The centralization finding is acknowledged; no critical findings are recorded.

**Methodology:** Manual review and static analysis.

The final report includes CED-45 through CED-51 from the earlier stepwise findings: CED-46 is resolved, while CED-45, CED-47, CED-48, CED-49, CED-50 and CED-51 are acknowledged.

<a id="asym-dlmm-upgrade-2026"></a>
### 2026-06-06 - DLMM - Upgrade audit - Asymptotic

**Report:** [Online report](https://cetus.asymptotic.tech/dlmm/upgrade-audit-v8-v9.html)

**Scope:** Review of the v8-to-v9 upgrade addressing rare overflow cases in fee accumulation and reward settlement in low-liquidity bins. The companion dlmm_router was unchanged in this upgrade window.

**Reviewed scope / revision:** On-chain cetus_dlmm version 9: `0x0489a4b326c17428d9ae6f10023468109b097f10e705af30ccc27bbb18ead065`. Baseline: the final code covered by the previous manual audit, described as internal version 8.

**Results:** The report records no security findings at any severity in the reviewed upgrade.

**Methodology:** Targeted review of the arithmetic-edge-case recovery paths and version gate.

<a id="asym-dlmm-manual-2026"></a>
### 2026-01-15 - DLMM - Manual audit - Asymptotic

**Report:** [Online report](https://info.asymptotic.tech/Cetus-DLMM-Audit-Report-294159bbd66d8039a322f6fd936b66b8)

**Scope:** Manual audit report for the DLMM core and companion router, linked and dated January 15, 2026 by Asymptotic's DLMM project index.

**Reviewed scope / revision:** Scope reference: cetus_dlmm and dlmm_router, as identified by the auditor's project index. See the linked report for its reviewed code revisions.

<a id="a11"></a>
### 2025-11-21 - DLMM - Asymptotic

**Scope:** cetus_dlmm and dlmm_router packages; frontend, backend, off-chain systems, deployment/operations and external services excluded.

**Final reviewed commit:** `974933c29a1705186e3784ddfd28fb10c01a62c9`.

**Code revisions recorded in the report:**
- `d1037ffc7ff7ffd314411d1a723aab0e2551d290 (initial)`
- `974933c29a1705186e3784ddfd28fb10c01a62c9 (final)`

**Source:** https://github.com/CetusProtocol/cetus-dlmm

**Findings:** 5 low remediated; 14 advisory: 10 remediated, 4 acknowledged

**Methodology:** Move smart-contract review, with findings, recommendations and remediation records in the report.

Five low findings are remediated; four advisories remain acknowledged.

<a id="a12"></a>
### 2025-11-04 - DLMM - OtterSec

**Scope:** cetus-dlmm, integer-mate and move-stl at their separately listed revisions.

**Code revisions recorded in the report:**
- `cd9ab3f (DLMM)`
- `1fc772f (integer-mate)`
- `0681fec (move-stl)`

**Source:** https://github.com/CetusProtocol/cetus-dlmm

**Findings:** 6 findings: 1 high, 1 medium and 4 informational; mixed subitem closure

**Methodology:** Design and implementation review; methodology is described in the Procedure appendix.

SUG-02 and SUG-03 contain both resolved and acknowledged subitems.

<a id="a13"></a>
### 2025-09-30 - DLMM - CertiK

**Scope:** DLMM core and the Cetus-maintained utility functions reviewed in the DLMM context; see Review Notes and file appendix.

**Final reviewed commit:** `cd0c803861e569be4a50defba26ca9d10725272c`.

**Code revisions recorded in the report:**
- `57ba7dc0c7471d99e911202bb68762373c8e79f4 (initial)`
- `160846ec4eb36bd5b9db416c015069a8c7d7e759`
- `f442ca0db0bd8c0e502029831fe3a1a2e960d038`
- `cd0c803861e569be4a50defba26ca9d10725272c (final)`

**Source:** https://github.com/CetusProtocol/cetus-dlmm

**Findings:** 32 findings: 29 resolved, 3 acknowledged

**Methodology:** Manual review and static analysis.

<a id="a14"></a>
### 2025-09-25 - DLMM - MoveBit

**Scope:** cetus_dlmm and dlmm_router files across the revisions listed in Project Information and Files in Scope.

**Code revisions recorded in the report:**
- `cd6b4e90ed6648a73bf7af64326caccced54bb29`
- `996091a88c9b5a85fb78681d2367919a0e8646f1`
- `f51c7e16a44fdf0ecc7441fc29b247f1d6713a90`
- `c0cb989e1369952b7064adffa3cffe549fc42668`
- `9ffb12f7960de6b610482c8f7291c6299b3b8c9d`
- `c318ee1050ecfb6d604182fe613c4bed78b4c328`
- `160846ec4eb36bd5b9db416c015069a8c7d7e759`
- `efdb6375f1e3192e30f2c3ac705929bfb1bfa8ee`
- `f442ca0db0bd8c0e502029831fe3a1a2e960d038`
- `80530ae53d162e4da26aeb665de305e17fb7768e`
- `3ad93678421b8bad01e7eca2cb4eda4b02c83503`
- `949ca8154c8ebf73d00d05f831b2947060542de4`
- `abf32f00e8ff039833f0a4da9110d75ce21c05aa`
- `16eabf284b0dd45d90c83d86cee2ea19c4cc4185`

**Source:** https://github.com/CetusProtocol/cetus-dlmm

**Findings:** 23 fixed: 1 critical, 1 major, 8 medium, 9 minor, 4 informational

**Methodology:** Architecture review, unit testing and manual review, as listed in Project Information.

Acknowledged findings are recorded separately from fixed or resolved findings. Audit reports apply to the reviewed versions and do not cover subsequent changes automatically.

## Formal Verification Reports

The following report is maintained online and is labeled current by Asymptotic's project index. It has no publication date, so it is listed separately from the dated audit history.

| Report | Auditor | Audit Duration or Date | Reviewed Revision | Link |
| --- | --- | --- | --- | --- |
| DLMM Comprehensive Formal Verification | Asymptotic | Current (undated) | [`1bfc5845e59ea56a873a4b635c1bc733806a5f97`](https://cetus.asymptotic.tech/dlmm/fv-report.html#reproducibility) | [Online report](https://cetus.asymptotic.tech/dlmm/fv-report.html) |

**Scope:** DLMM core and router, including flash-swap repayment, liquidity/position accounting, bin math/storage, dynamic fees, rewards, partner logic and administrative controls. The reproducibility section identifies cetus_dlmm v9 and dlmm_router v7.

**Methodology:** Sui Prover 1.5.3; arithmetic formulas, state-transition postconditions and access-control specifications.

**Coverage limits:** Some composed entry points and one price-grid numerical postcondition are covered structurally rather than by full end-to-end equations. Runtime assumptions, oracle feeds and off-chain indexers are outside scope.

