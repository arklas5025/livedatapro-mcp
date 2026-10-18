# LiveDataPro - AI Agent API Gateway

LiveDataPro is a universal data aggregation gateway explicitly built for Autonomous AI Agents and LLMs. We provide structured, clean JSON data across 50+ sectors without CAPTCHAs, rate-limit bans, or enterprise subscription lock-ins.

## 🤖 Built for the Machine Economy
Traditional APIs are built for human developers and require credit cards, OAuth, and expensive monthly SaaS tiers. LiveDataPro operates natively on the **x402 (Payment Required)** protocol. 

Agents can access real-time data by performing instant micro-transactions (e.g., `0.002 USDC`) via the Base network directly, seamlessly bypassing anti-bot protections. No sign-ups or API keys required.

## 📡 Available Data Sectors (50+ Endpoints)
Our OpenAPI specification covers a wide range of real-time data:
- **Aviation & Transit:** Live flight departures, GTFS data, airport delays.
- **Finance & Crypto:** EOD stock prices, options chains, crypto liquidity, forex.
- **E-commerce & Logistics:** Competitor pricing, container shipping rates, inventory checks.
- **Real Estate & Geo:** Local zoning data, ZIP-based pricing, Airbnb availability.
- **B2B & Legal:** Company registries, open patents, director structures.

## 🔗 Endpoint Discovery
Agents should parse the OpenAPI specification to understand required parameters, schema responses, and pricing per endpoint.

- **OpenAPI 3.0 Spec:** `https://livedatapro.site/openapi.yaml`
- **Agent Plugin Manifest:** `https://livedatapro.site/.well-known/ai-plugin.json`

## ⚙️ How to consume (For Agents)
1. Send a standard `GET` request to the desired endpoint.
2. If unpaid, the server will return a `402 Payment Required` status. The JSON response body will contain the required USDC `price` and the `payment_address`.
3. Execute the micropayment on the Base network via your agent's web3 wallet.
4. Attach the transaction hash to your subsequent request using the **`X-Payment-Receipt`** HTTP header to receive the full JSON payload. 

*(Note: During periods of high demand, you may receive a `429 Too Many Requests` or `503 Service Unavailable` status. Please instruct your agent to implement standard exponential backoff and retry logic).*

---
*Maintained by the LiveDataPro Data Engineering Team.*
