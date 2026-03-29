30 years on Wall Street — ran FX derivatives trading at Morgan Stanley (New York & London), ran the strategic trading desk at Merrill Lynch, ran LatAm FX trading at Standard Chartered, built the electronic FX business at TP-ICAP. Helped execute the [first SEC-registered security token IPO](https://www.intelligenthq.com/interview-with-douglas-borthwick-cmo-inx-limited-the-first-sec-registered-security-token-ipo/) ($85M) as CMO/CBO at INX Limited. Author of *The Insumer Model*, *Your Equity in Your Pocket*, *Bitcoin, Blockchain & Tokenization*, *Tokenized Tomorrow*, and *Bitcoin: The Capital Singularity*. Co-host of [Old Men, New Money](https://oldmennewmoney.com/) (38K+ followers). Carnegie Mellon University. Yale School of Management (financial engineering).

CEO of [Skye Meta Corp.](https://skyemeta.com) and [TokenCapStack](https://tokencapstack.com). Now building condition-based access infrastructure.

## Building InsumerAPI

Condition-based access infrastructure across 33 blockchains. Send a wallet and conditions, get a signed boolean. No secrets, no identity, no static credentials — access depends on what a wallet holds, right now.

Wallet auth is the implementation. [Condition-based access](https://insumermodel.com/blog/there-is-no-key.html) is the category.

### What It Does

A caller sends `POST /v1/attest` with a wallet address and conditions. The API evaluates on-chain state and returns a signed pass/fail attestation with `id`, `pass`, `results` (per-condition booleans with `conditionHash`, `blockNumber`, `blockTimestamp`), `attestedAt`, and `expiresAt`. Anyone can verify the signature against the public key at `/.well-known/jwks.json`.

Works across EVM (30 chains), Solana, XRPL, and Bitcoin. Proven across commerce (SkyeWoo), content gating (SkyeGate), agent trust (AgentTalk), and API access control.

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

- [MCP Server](https://www.npmjs.com/package/mcp-server-insumer) — 26 tools, Official MCP Registry
- [LangChain](https://pypi.org/project/langchain-insumer/) — 26 tools, PyPI
- [ElizaOS](https://www.npmjs.com/package/eliza-plugin-insumer) — 10 actions, npm
- [OpenAI GPT](https://chatgpt.com/g/g-699c5e43ce2481918b3f1e7f144c8a49-insumerapi-verify) — 26 actions, GPT Store
- [OpenAPI Spec](https://insumermodel.com/openapi.yaml) — Full REST API documentation
- [insumer-verify](https://www.npmjs.com/package/insumer-verify) — Client-side signature verification

### Links

- [AI Agent Verification API](https://insumermodel.com/ai-agent-verification-api/) — Full guide: 33 chains, trust profiles, commerce, signatures
- [Developers](https://insumermodel.com/developers/) — API keys, pricing, docs
- [There Is No Key](https://insumermodel.com/blog/there-is-no-key.html) — The condition-based access argument
- [insumermodel.com](https://insumermodel.com)
