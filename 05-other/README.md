# Cetus Other Contracts Audits

This folder collects audits of CETUS/xCETUS, Launchpad, RFQ and LP Burn. These reports cover token conversion and locking, launchpad subscriptions, signed market-maker interactions and CLMM-position burn functionality respectively.

## Audit Reports

Reports are listed newest first by report date or latest follow-up date. The date column shows the review period when provided, otherwise the report date.

| Module | Auditor | Audit Duration or Date | Final Commit / Reviewed Scope | Report |
| --- | --- | --- | --- | --- |
| RFQ | MoveBit | 2025-06-17 - 2025-06-20 | [3 listed revisions](#a22) | [PDF](reports/2025-06-24-rfq-movebit.pdf) |
| LP Burn | MoveBit | 2024-09-29 - 2024-09-30 | [2 listed revisions](#a23) | [PDF](reports/Sep%202024-LP%20Burn%20Audit%20by%20MoveBit.pdf) |
| Launchpad | MoveBit | 2023-07-12 - 2023-07-20 | [3 listed revisions](#a21) | [PDF](reports/2023-07-20-launchpad-movebit.pdf) |
| Token / xCETUS | MoveBit | 2023-04-21 - 2023-04-26 | [2 listed revisions](#a20) | [PDF](reports/Apr%202023-Token%20Audit%20by%20MoveBit.pdf) |

A final commit is labeled where the report explicitly identifies it. Otherwise, the reviewed revision or complete revision list is reproduced below. Each report applies to its stated code and scope.

## Scope and Findings

<a id="a22"></a>
### 2025-06-24 - RFQ - MoveBit

**Scope:** rfq: packages/validator and packages/mm_demo source files and manifests.

**Code revisions recorded in the report:**
- `6a932e56b3002310aec96ecd11704ccb4a6851ab`
- `ae5f9d6524823c7013933bb33ebc6eb6377e9ba0`
- `470430c51c5f1d7dc37762ccd492998fa8eb5a87`

**Source:** https://github.com/CetusProtocol/rfq

**Findings:** 7 findings: 6 fixed, 1 minor acknowledged

**Methodology:** Architecture review, unit testing and manual review, as listed in Project Information.

MDE-4 is acknowledged. MDE-1 is marked fixed with a caveat concerning signature replay across multiple vaults under the same address.

<a id="a23"></a>
### 2024-09-30 - LP Burn - MoveBit

**Scope:** cetus-lp-burn: Move.toml and sources/lp_burn.move.

**Code revisions recorded in the report:**
- `4f1857bec837fb197e001196b22eecad37f5ca4b`
- `f775c3c5520f93b62b1e25fce6ded16fb08d4b85`

**Source:** https://github.com/CetusProtocol/cetus-lp-burn

**Findings:** 2 acknowledged: 1 minor, 1 informational; 0 fixed

**Methodology:** Architecture review, unit testing and manual review, as listed in Project Information.

LBU-1 and LBU-2 are acknowledged.

<a id="a21"></a>
### 2023-07-20 - Launchpad - MoveBit

**Scope:** sui/IDO: config, duration, factory, lock, oversubscribe_pool, purchase_manager, whitelist and manifest.

**Code revisions recorded in the report:**
- `1effa6ac19e3b7cb2323eda3c684d1220f70a9e6`
- `7d828063fccde5664fc251768023cb928c2429c5`
- `e6cd9967c2e03dc1b4303055481db536358744d6`

**Source:** https://github.com/CetusProtocol/cetus-launchpad

**Findings:** 6 fixed: 2 major, 4 minor

**Methodology:** Architecture review, unit testing and manual review, as listed in Project Information.

The report is dated July 20, 2023; the supplied filename used July 2024. PDF content is unchanged.

<a id="a20"></a>
### 2023-04-26 - Token / xCETUS - MoveBit

**Scope:** cetus and xcetus packages, including conversion, locking, redemption and associated manifests.

**Code revisions recorded in the report:**
- `a89e1b353df7403dd59fb110611f5a95ce2cf73a`
- `a8548cc7a39cfaabe3076a473cdd5ae09d7252e0`

**Source:** https://github.com/CetusProtocol/cetus-token

**Findings:** 6 findings: 5 fixed, 1 medium acknowledged

**Methodology:** Architecture review, unit testing and manual review, as listed in Project Information.

CTS-02, concerning token minting/burning permissions, is acknowledged.

Acknowledged findings are recorded separately from fixed or resolved findings. Audit reports apply to the reviewed versions and do not cover subsequent changes automatically.
