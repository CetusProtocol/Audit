# Cetus Farm and Vault Audits

This folder collects farming and vault audits. Farming manages incentives for deposited CLMM positions; vaults manage liquidity, reinvestment and rebalancing. Each report identifies the contracts and dependencies it reviewed.

## Audit Reports

Reports are listed newest first by report date or latest follow-up date. The date column shows the review period when provided, otherwise the report date.

| Module | Auditor | Audit Duration or Date | Final Commit / Reviewed Scope | Report |
| --- | --- | --- | --- | --- |
| Farm | CertiK | 2026-10-20 | [Reviewed: `573d537888`](#certik-farming-2026-10-20) | [PDF](reports/Oct%202026-Farming%20Audit%20by%20Certik.pdf) |
| Vault | OtterSec | 2024-03-01 - 2024-03-20; follow-up: 2025-05-27 - 2025-06-06 | [2 listed revisions](#a26) | [PDF](reports/2024-03-30-vaults-ottersec-with-2025-follow-up.pdf) |
| Vault | OtterSec | 2024-03-01 - 2024-03-20 | [Reviewed: `c23ab34`](#a27) | [PDF](reports/Mar%202024-Vault%20Audit%20by%20OtterSec.pdf) |
| Vault | MoveBit | 2024-02-23 - 2024-02-27 | [2 listed revisions](#a24) | [PDF](reports/Feb%202024-Vault%20Audit%20by%20MoveBit.pdf) |
| Farm | MoveBit | 2023-12-29 - 2024-01-05 | [4 listed revisions](#a25) | [PDF](reports/Jan%202024-Farm%20Audit%20by%20MoveBit.pdf) |

A final commit is labeled where the report explicitly identifies it. Otherwise, the reviewed revision or complete revision list is reproduced below. Each report applies to its stated code and scope.

## Scope and Findings

<a id="certik-farming-2026-10-20"></a>
### 2026-10-20 - Farm - CertiK

**Report:** [October 2026 stable farming security assessment](reports/Oct%202026-Farming%20Audit%20by%20Certik.pdf)

**Scope:** Stable farming pool, rewarder, configuration, ACL and router files listed in the report. The protocol supports staking CLMM positions and distributing farming rewards. The underlying cetus_clmm dependency is outside this audit's scope.

**Code revisions recorded in the report:**
- `0e288bfd710883e9dc48fff439cb6c62b95e57ce`
- `ac44249508a51947cbfaf6d6cf048496328d3d1b`
- `fa08737a605c78c2aa77fe31fb864878c732e469`
- `14fadb735e3ec744721fe65e05f72554045edeca`
- `573d537888d6f6b6f5aa5ce77d8c61c875cc396f`

**Source:** https://github.com/CetusProtocol/cetus-clmm-sui/tree/main/stable_farming

**Findings:** 16 findings: 10 resolved and 6 acknowledged. Both medium findings are resolved. Low findings: 1 resolved and 3 acknowledged. Informational findings: 7 resolved and 2 acknowledged. The centralization finding is acknowledged. No critical or high findings are recorded. Optimization entries are listed separately.

**Methodology:** Manual review and static analysis.

<a id="a26"></a>
### 2025-06-06 - Vault - OtterSec

**Scope:** vaults at c23ab34; follow-up includes PR#1 and compensation-repository revision 3eab21e.

**Code revisions recorded in the report:**
- `c23ab34`
- `3eab21e (compensation repository); PR#1 also reviewed`

**Source:** https://github.com/CetusProtocol/vaults

**Findings:** 7 findings: 1 medium and 2 low vulnerabilities resolved; 4 general findings

**Methodology:** Design and implementation review; methodology is described in the Procedure appendix.

Cover retains March 30, 2024; the text records the May-June 2025 follow-up. General finding numbering differs from the earlier report.

<a id="a27"></a>
### 2024-03-30 - Vault - OtterSec

**Scope:** vaults at c23ab34; liquidity management, fee/reward reinvestment and rebalancing.

**Code revisions recorded in the report:**
- `c23ab34`

**Source:** https://github.com/CetusProtocol/vaults

**Findings:** 8 findings: 1 medium and 2 low vulnerabilities resolved; 5 general findings

**Methodology:** Design and implementation review; methodology is described in the Procedure appendix.

<a id="a24"></a>
### 2024-02-29 - Vault - MoveBit

**Scope:** vaults: fetcher, ACL, router, utils, vaults source and manifest.

**Code revisions recorded in the report:**
- `464c943caf624e3434986280b4a02e275e6a8bba`
- `c23ab3489af813cad58a4cdfbad0f2600a40d06a`

**Source:** https://github.com/CetusProtocol/vaults

**Findings:** 4 findings: 2 fixed, 2 acknowledged; acknowledged items include major centralization and medium rewards loss

**Methodology:** Architecture review, unit testing and manual review, as listed in Project Information.

ROU-1 rewards loss and VAU-1 centralization are acknowledged.

<a id="a25"></a>
### 2024-01-19 - Farm - MoveBit

**Scope:** stable-farming source and manifest, with CLMM rewarder interactions described in the findings.

**Code revisions recorded in the report:**
- `cab10270ca5567772b47bad65bc2db0953bcc55e`
- `8f83fca210929aa86053e2338c00204450170c46`
- `26a210c342f590739f9360d1195d62180c2e4b54`
- `61e18eb5ed3ac7c9bc84811a472fa03725ecb6a8`

**Source:** https://github.com/CetusProtocol/cetus-clmm-sui

**Findings:** 9 fixed: 4 major, 5 minor

**Methodology:** Architecture review, unit testing and manual review, as listed in Project Information.

Acknowledged findings are recorded separately from fixed or resolved findings. Audit reports apply to the reviewed versions and do not cover subsequent changes automatically.
