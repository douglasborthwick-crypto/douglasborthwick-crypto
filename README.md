## Building InsumerAPI

On-chain attestation infrastructure for commerce across 32 blockchains. ECDSA-signed boolean proofs of wallet eligibility — token holdings, trust-line balances, NFT ownership, compliance credentials — without exposing raw balances.

### What It Does

A merchant calls `POST /v1/attest` with a wallet address and conditions. The API evaluates on-chain state and returns a signed pass/fail attestation with `ledgerIndex`, `conditionHash`, `attestedAt`, and `expiresAt`. Anyone can verify the signature against the public key at `/.well-known/jwks.json`.

Works across EVM (30 chains), Solana, and XRPL (trust-line tokens like RLUSD, USDC, native XRP).

### Try It

- [XRPL Live Demo](https://insumermodel.com/demos/xrpl/) — Run a real RLUSD trust-line attestation in the browser

### Agent SDKs

- [MCP Server](https://www.npmjs.com/package/mcp-server-insumer) — 25 tools, Official MCP Registry
- [LangChain](https://pypi.org/project/langchain-insumer/) — 25 tools, PyPI
- [OpenAI GPT](https://chatgpt.com/g/g-699c5e43ce2481918b3f1e7f144c8a49-insumerapi-verify) — 25 actions, GPT Store
- [OpenAPI Spec](https://insumermodel.com/openapi.yaml) — Full REST API documentation
- [insumer-verify](https://www.npmjs.com/package/insumer-verify) — Client-side signature verification

### Links

- [Developers](https://insumermodel.com/developers/) — API keys, pricing, docs
- [insumermodel.com](https://insumermodel.com)
