# FluxObserver

Built for Base

FluxObserver is a compact Base-aligned repository created to validate wallet connectivity, RPC responses, and explorer visibility on Base networks using official Coinbase tooling.

Instead of focusing on business logic, the project acts as a clean infrastructure probe for Base Mainnet and Base Sepolia.

---

## Scope and Intent

FluxObserver is designed to:
- Verify Base RPC availability and correctness
- Confirm wallet onboarding via OnchainKit
- Perform deterministic, read-only onchain queries
- Provide clear Basescan references for deployments and verification

---

## Networks

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  
RPC: https://mainnet.base.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  
RPC: https://sepolia.base.org  

---

## Runtime Description

Primary file: `app/fluxObserver.ts`

At runtime, the application:
- Initializes an OnchainKit provider for the selected Base network
- Exposes wallet connection UI through OnchainKit Wallet
- Creates a Viem public client bound to Base RPC
- Reads:
  - RPC-reported chainId
  - latest block number
  - native ETH balance for a supplied address
- Surfaces explorer URLs for manual verification

---

## Repository Structure

app/  
- fluxObserver.ts  
  React entry component wiring wallet UX to Base read-only RPC calls.

Supporting files typically included:
- package.json  
- tsconfig.json  
- index.html / main.tsx  
- .env (optional)  

---

## Libraries Used

OnchainKit  
Wallet UI components and Base-first primitives  
https://github.com/coinbase/onchainkit  

Viem  
EVM client library for Base JSON-RPC interactions  

---

## Installation and Usage

Requirements:
- Node.js 18+
- Browser environment with wallet support

Install dependencies using your preferred package manager and run the project using a standard React/Vite or Next.js development setup.

Optional environment variables:
- VITE_BASE_RPC_URL
- VITE_BASE_SEPOLIA_RPC_URL

---

## License

MIT License

---

## Author

GitHub: https://github.com/meter-silo

Public contact (email): meter_silo.0l@icloud.com

Public contact (X): https://x.com/gerasimovdimas2

---

## Testnet Deployment (Base Sepolia)

**Network:** Base Sepolia  
**chainId (decimal):** 84532  
**Explorer:** https://sepolia.basescan.org  

**Deployed contract #1 address:**  
0x4b41d652139dcfcd2aee85983e3410c91f60a767

**Deployed contract #2 address:**  
0x3db12a0e78ef557825d0b4a5e3e39c659914b2ed

**Basescan deployment and verification links:**  
- Contract #1 address:  
  https://sepolia.basescan.org/address/0x4b41d652139dcfcd2aee85983e3410c91f60a767 
- Contract #2 address:  
  https://sepolia.basescan.org/address/0x3db12a0e78ef557825d0b4a5e3e39c659914b2ed 
- Contract #1 verification (source code):  
  https://sepolia.basescan.org/0x4b41d652139dcfcd2aee85983e3410c91f60a767/0#code  
- Contract #2 verification (source code):  
  https://sepolia.basescan.org/0x3db12a0e78ef557825d0b4a5e3e39c659914b2ed/0#code  

This deployment is used to validate Base-compatible tooling, account abstraction flows, and onchain read operations in a test environment prior to mainnet usage.
