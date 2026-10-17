# Cetus Limit Order, DCA and Margin Audits

This folder collects audits of Cetus trading extensions: limit orders, recurring DCA orders and margin-trading integration. Reports retain their individual module and scope boundaries, including keeper, signature, repayment and external lending interactions where relevant.

## Audit Reports

Reports are listed newest first by report date or latest follow-up date. The date column shows the review period when provided, otherwise the report date.

| Module | Auditor | Audit Duration or Date | Final Commit / Reviewed Scope | Report |
| --- | --- | --- | --- | --- |
| DCA | CertiK | 2026-08-11 | [5 listed revisions](#a16) | [PDF](reports/Aug%202026-DCA%20Audit%20by%20Certik.pdf) |
| Margin | MoveBit | 2026-01-04 - 2026-01-07 | [7 listed revisions](#a19) | [PDF](reports/Jan%202026-Margin%20Audit%20by%20MoveBit.pdf) |
| DCA | CertiK | 2025-11-26 | [4 listed revisions](#a18) | [PDF](reports/Nov%202025-DCA%20Audit%20by%20Certik.pdf) |
| Limit Order | OtterSec | 2024-05-08 - 2024-05-16 | [Reviewed: `53bff8b`](#a17) | [PDF](reports/May%202024-Limit%20Order%20Audit%20by%20OtterSec.pdf) |
| Limit Order | MoveBit | 2024-04-07 - 2024-04-16 | [2 listed revisions](#a15) | [PDF](reports/Apr%202024-Limit%20Order%20Audit%20by%20MoveBit.pdf) |

A final commit is labeled where the report explicitly identifies it. Otherwise, the reviewed revision or complete revision list is reproduced below. Each report applies to its stated code and scope.

## Scope and Findings

<a id="a16"></a>
### 2026-08-11 - DCA - CertiK

**Scope:** cetus_dca/sources/acl.move, config.move and order.move across the listed revisions.

**Code revisions recorded in the report:**
- `482dc4009a3e95a117ae59752c3249f46d54e4cf`
- `c6b5cb9c6304525f5673f8f748ec254b96b255a0`
- `680dca8ae3f91a63078b56f1f6880b87daafe264`
- `788e10370cac04ce059875de9acd55e934ce441f`
- `77df6f1918c4fc8d8a17086995251121258b16ce`

**Source:** https://github.com/CetusProtocol/cetus-clmm-sui

**Findings:** 14 findings: 11 resolved and 3 acknowledged.

**Methodology:** Formal verification, manual review and static analysis, as listed in the report.

Updated report version: retains the fourteen findings and disposition totals of the November 2025 report and adds a listed code revision.

<a id="a19"></a>
### 2026-01-22 - Margin - MoveBit

**Scope:** cetus-margin-trading: admin_cap, context, errors, position, versioned, router, config, market and permissions. Covers Cetus integration code interacting with Suilend.

**Code revisions recorded in the report:**
- `b50b5eef220434a675e0cda862ec49d3880fb28d`
- `c8b639dbb7c7818bda4db65fc938f9fd0bff40f8`
- `612f8f38b959f132128666e2c27bd656b82fe5b2`
- `ddf6408badbaefe9da58822108137f343b73e2f0`
- `3e2540638972bc81f8bf3fbc7c1e7b3a83543a58`
- `d8b6e13ac981eeab038aa6f4faf37c0ca48a2a76`
- `119a46b4b66887c1a32deb33c2c4e24b3d8bc42f`

**Source:** https://github.com/CetusProtocol/cetus-margin-trading

**Findings:** 8 fixed: 1 critical, 1 major, 1 medium, 5 minor

**Methodology:** Architecture review, unit testing and manual review, as listed in Project Information.

<a id="a18"></a>
### 2025-11-26 - DCA - CertiK

**Scope:** cetus_dca/sources/acl.move, config.move and order.move across the listed revisions.

**Code revisions recorded in the report:**
- `482dc4009a3e95a117ae59752c3249f46d54e4cf`
- `c6b5cb9c6304525f5673f8f748ec254b96b255a0`
- `680dca8ae3f91a63078b56f1f6880b87daafe264`
- `788e10370cac04ce059875de9acd55e934ce441f`

**Source:** https://github.com/CetusProtocol/cetus-clmm-sui

**Findings:** 14 findings: 11 resolved and 3 acknowledged.

**Methodology:** Formal verification, manual review and static analysis, as listed in the report.

Earlier version of the DCA report; retained separately from the August 2026 update.

<a id="a17"></a>
### 2024-05-16 - Limit Order - OtterSec

**Scope:** cetus-limitorder at 53bff8b; order repayment, role removal and whitelist validation.

**Code revisions recorded in the report:**
- `53bff8b`

**Source:** https://github.com/CetusProtocol/cetus-limitorder

**Findings:** 4 findings: critical, medium and low vulnerabilities resolved; 1 informational

**Methodology:** Design and implementation review; methodology is described in the Procedure appendix.

<a id="a15"></a>
### 2024-04-16 - Limit Order - MoveBit

**Scope:** cetus-limitorder: acl.move, skip_list_u128.move, option_u128.move, config.move and order.move.

**Code revisions recorded in the report:**
- `0ad1830ae749b08a83163a83eec0ac0bd5e408ca`
- `53bff8b64cc27047abd0869bed333406cc8108bf`

**Source:** https://github.com/CetusProtocol/cetus-limitorder

**Findings:** 5 fixed: 3 major, 2 minor

**Methodology:** Architecture review, unit testing and manual review, as listed in Project Information.

Acknowledged findings are recorded separately from fixed or resolved findings. Audit reports apply to the reviewed versions and do not cover subsequent changes automatically.
