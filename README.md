## Building InsumerAPI

On-chain attestation infrastructure for commerce across 32 blockchains. ECDSA-signed boolean proofs of wallet eligibility — token holdings, trust-line balances, NFT ownership, compliance credentials — without exposing raw balances.

### What It Does

A merchant calls `POST /v1/attest` with a wallet address and conditions. The API evaluates on-chain state and returns a signed pass/fail attestation with `id`, `pass`, `results` (per-condition booleans with `conditionHash`, `blockNumber`, `blockTimestamp`), `attestedAt`, and `expiresAt`. Anyone can verify the signature against the public key at `/.well-known/jwks.json`.

Works across EVM (30 chains), Solana, and XRPL (trust-line tokens like RLUSD, USDC, native XRP).

### Get a Free API Key

```bash
curl -X POST \
  https://api.insumermodel.com/v1/keys/create \
  -H "Content-Type: application/json" \
  -d '{"email": "you@example.com", "appName": "my-app", "tier": "free"}'
```

Returns an `insr_live_...` key instantly with 10 verification credits.

### Try It

- [XRPL Live Demo](https://insumermodel.com/demos/xrpl/) — Run a real RLUSD trust-line attestation in the browser

### Agent SDKs

- [MCP Server](https://www.npmjs.com/package/mcp-server-insumer) — 25 tools, Official MCP Registry
- [LangChain](https://pypi.org/project/langchain-insumer/) — 25 tools, PyPI
- [ElizaOS](https://www.npmjs.com/package/eliza-plugin-insumer) — 3 actions + dynamic provider, npm
- [OpenAI GPT](https://chatgpt.com/g/g-699c5e43ce2481918b3f1e7f144c8a49-insumerapi-verify) — 25 actions, GPT Store
- [OpenAPI Spec](https://insumermodel.com/openapi.yaml) — Full REST API documentation
- [insumer-verify](https://www.npmjs.com/package/insumer-verify) — Client-side signature verification

### Links

- [AI Agent Verification API](https://insumermodel.com/ai-agent-verification-api/) — Full guide: 32 chains, trust profiles, commerce, signatures
- [Developers](https://insumermodel.com/developers/) — API keys, pricing, docs
- [insumermodel.com](https://insumermodel.com)
