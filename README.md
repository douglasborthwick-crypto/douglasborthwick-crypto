Thirty years in global markets, trading currencies and macro at Morgan Stanley, Merrill Lynch and Standard Chartered, then a pioneer of SEC-registered security tokens. Founder of The Insumer Model, the company behind [InsumerAPI](https://insumermodel.com). CEO of [Skye Meta](https://skyemeta.com) and [TokenCapStack](https://tokencapstack.com). Co-host of [Old Men, New Money](https://oldmennewmoney.com/).

Author of [**Secrets and Agents**](https://www.amazon.com/dp/B0HJPBL8FL): *Why AI Agents Cannot Hold Secrets, and How the Blockchain Becomes the Way They Prove Anything*. Book 3 of the Insumer Revolution series, after *The Insumer Model* and *Your Equity in Your Pocket*.

## Building InsumerAPI

Wallet auth for developers and AI agents. Send a wallet and conditions, get a signed boolean, across 37 blockchains. No secrets, no identity, no static credentials: access depends on what a wallet holds, right now.

Wallet auth is the primitive: read, evaluate, sign, keep. [Condition-based access](https://insumermodel.com/blog/there-is-no-key.html) is the category.

### Hosted MCP server

Connect any MCP client to `https://api.insumermodel.com/mcp`. No install, no key: 10 tools for attestations, wallet trust profiles, merchant and discount checks, and signature keys.

### What It Does

A caller sends `POST /v1/attest` with a wallet address and up to 10 conditions: token balance, NFT ownership, EAS attestations, Farcaster, view calls, ratio rules, account code (plain key, EIP-7702 delegation, or contract) and agent standing (ERC-8004, ERC-7710). The API returns a signed pass/fail attestation with `id`, `pass`, `results` (per-condition booleans with `conditionHash`, `blockNumber`, `blockTimestamp`), `attestedAt` and `expiresAt`, never the balance. Each result carries an ECDSA signature and a post-quantum ML-DSA-65 companion; anyone can verify both against the public keys at `/.well-known/jwks.json`.

[Wallet trust profiles](https://insumermodel.com/developers/trust/) (`POST /v1/trust`) return 155 signed presence checks across 27 chains in 10 dimensions, up to 176 with optional Solana, XRPL, Bitcoin and Tron wallets. No score, no opinion: signed evidence.

Works across 31 EVM chains plus Solana, XRPL, Bitcoin, Tron, Stellar and Sui. [Skye Meta](https://skyemeta.com) builds its commerce, content and agent products on it.

### Get a Free API Key

```bash
curl -X POST \
  https://api.insumermodel.com/v1/keys/create \
  -H "Content-Type: application/json" \
  -d '{"email": "you@example.com", "appName": "my-app", "tier": "free"}'
```

Returns an `insr_live_...` key instantly, shown once, so save it: 10 free verifications plus 100 requests a day.

### Pay Per Call with x402

No key, no account. x402 moves the money. InsumerAPI checks the conditions. Call `POST /v1/attest`, `/v1/trust` or `/v1/trust/batch` without a key, get a `402` with the price, pay in USDC on Base, Polygon, Arbitrum, Arc, or Solana, and retry with the payment. The payer is charged only for a successful answer, and the payer sees the answer only after the payment settled.

### Verify the Signatures

Every result verifies against the published public keys, offline with a saved copy of them. `insumer-verify` checks the ECDSA signature and its ML-DSA-65 post-quantum companion, condition hashes, block freshness and expiry. Same specification, same published test vectors, in JavaScript and Python.

```bash
npm install insumer-verify
pip install "insumer-verify[pq]"
```

[npm](https://www.npmjs.com/package/insumer-verify) · [PyPI](https://pypi.org/project/insumer-verify/) · [source](https://github.com/insumerapi/insumer-verify)

### Agent SDKs

- [MCP Server](https://www.npmjs.com/package/mcp-server-insumer): 27 tools on your own key, Official MCP Registry
- [LangChain](https://pypi.org/project/langchain-insumer/): 26 tools, PyPI
- [LlamaIndex](https://pypi.org/project/llama-index-tools-insumer/): PyPI
- [ElizaOS](https://www.npmjs.com/package/@insumermodel/plugin-eliza): 10 actions, npm
- [OpenAI GPT](https://chatgpt.com/g/g-699c5e43ce2481918b3f1e7f144c8a49-insumerapi-wallet-auth): 28 actions, GPT Store
- [OpenAPI Spec](https://insumermodel.com/openapi.yaml): full REST API documentation

### Try It

- [XRPL Live Demo](https://insumermodel.com/demos/xrpl/): run a real RLUSD trust-line attestation in the browser

### Links

- [AI Agent Verification API](https://insumermodel.com/ai-agent-verification-api/): full guide to chains, trust profiles, commerce and signatures
- [Developers](https://insumermodel.com/developers/): API keys, pricing, docs
- [There Is No Key](https://insumermodel.com/blog/there-is-no-key.html): the condition-based access argument
- [insumermodel.com](https://insumermodel.com)
