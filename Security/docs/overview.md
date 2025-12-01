# EINCZ Protocol Documentation

Welcome to the official technical documentation for the EINCZ Protocol.

This repository contains the complete reference for the EINCZ ecosystem, including:  
- Smart-contract architecture  
- Token governance  
- Security configuration  
- Contract addresses  
- Tokenomics  
- Public audit artifacts  

Everything here is open for public verification and transparency.

---

## 1. Introduction

EINCZ is a decentralized, energy-aligned digital asset designed for programmable, permissionless and transparent value flow across the energy sector and emerging Web3 markets.

The protocol follows modern blockchain standards, prioritizing:

- Security  
- Transparent governance  
- Predictable emissions  
- Auditability  
- Community participation  

EINCZ is deployed on the Avalanche C-Chain.

---

## 2. Core Contracts

| Component | Address | Explorer |
|----------|---------|----------|
| **EINCZ Token (ERC-20)** | `0xf1cDA94f51B8757dd2C25b85eFbc8d4cF85656Ec` | https://routescan.io/address/0xf1cDA94f51B8757dd2C25b85eFbc8d4cF85656Ec |
| **Gnosis Safe Treasury** | `0x946C4392B557D43DBA9A37Ee082CB062360D1212` | https://routescan.io/address/0x946C4392B557D43DBA9A37Ee082CB062360D1212 |
| **Timelock Controller** | `0xa3f61e633275f6240FFc9cBB462093365655dEF4` | https://routescan.io/address/0xa3f61e633275f6240FFc9cBB462093365655dEF4 |
| **Governor Contract** | `0x645e50EB79769AF9f06290E3BB3773988E1fF6A1` | https://routescan.io/address/0x645e50EB79769AF9f06290E3BB3773988E1fF6A1 |
| **Staking & Incentives** | `0xa1d702962A8b476849045300A0bB55958b778d35` | https://routescan.io/address/0xa1d702962A8b476849045300A0bB55958b778d35 |

---

## 3. Token Specification

- **Name:** EINCZ  
- **Symbol:** EINCZ  
- **Standard:** ERC-20  
- **Decimals:** 18  
- **Total Supply:** 746,000,000 EINCZ  

### 3.1 Allocation Snapshot

- **Master Treasury (Multisig):** 634,100,000  
- **Staking / Incentives Contract:** 111,900,000  
- **Other allocations:** Released through governance-controlled vesting  

---

## 4. Governance Model

EINCZ adopts a **Timelock-secured governance architecture**, ensuring decentralization and institutional auditability.

### Governance Structure

- **Governor Contract:** Receives proposals and handles voting  
- **Timelock Controller:** Executes approved proposals after required delay  
- **Token Contract:** Enforces admin permissions and role restrictions  

### Governance Guarantees

- No externally owned account (EOA) has administrative power  
- No multisig controls token permissions  
- All admin actions must go through governance  
- Timelock ensures transparent and predictable security delays  

---

## 5. Roles & Security Model

The EINCZ token uses OpenZeppelin AccessControl.  
The following roles exist:

- `DEFAULT_ADMIN_ROLE`  
- `MINTER_ROLE`  
- `PAUSER_ROLE`  
- `BLACKLIST_ADMIN_ROLE`  

### Final Target Assignment (Model 1: Full Governance Control)

| Role | Holder |
|------|--------|
| DEFAULT_ADMIN_ROLE | Timelock |
| MINTER_ROLE | Timelock |
| PAUSER_ROLE | Timelock |
| BLACKLIST_ADMIN_ROLE | Timelock |
| Multisig | No roles |
| EOAs | No roles |

For full details, see:

👉 `docs/security/roles_configuration.json`

---

## 6. Incentive Architecture

The staking contract holds the incentives pool and distributes rewards according to emissions logic defined by governance.

Any changes must be passed through governance proposals.

---

## 7. Transparency & Verifiability

All documentation, governance settings and security artifacts are stored in:

