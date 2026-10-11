# Meta and Sierra propose an open standard for AI agents that act for customers

*11 October 2026*

On 6 October, Meta and Sierra announced the **Personal Agent Protocol (PAP)**, an open standard meant to define how a customer's personal AI agent identifies itself to a business and acts on that customer's behalf. Genesys, Instinct, Rocket, Shopify, Stripe and Walmart are named as participating organisations.

## Why it matters

As consumer agents start to look up accounts, ask about orders or make purchases, businesses face a practical problem: how do you tell a legitimate agent working for a real customer from an anonymous bot? PAP tries to give both sides a shared answer. Businesses get a way to recognise agents and see what they do. Customers get a say in how much access an agent has.

## What has been described so far

- **Authentication is built on OAuth.** Per the reporting, an agent can start as a guest and escalate to a signed-in session with read-only or write access.
- **Business systems stay reachable through existing standards.** Agents are expected to use APIs described by standards such as MCP and OpenAPI rather than a brand-new interface.
- **It is early.** Sierra says it will publish a v0.1 specification later in October, run design workshops and release a reference implementation. Detailed permissions, push notifications and payments are listed as possible later extensions.

## What to watch

1. **Adoption by other agent providers.** Coverage notes that OpenAI and Anthropic had not joined at the time of the announcement. A standard that only some agents speak solves only part of the problem.
2. **The v0.1 spec itself.** The interesting details, such as how consent is recorded, how write access is limited and how a business revokes an agent, will only be visible once the text is public.
3. **Payments.** Purchases are the highest-risk case and are on the roadmap rather than in the first version.

## My take

For anyone building or testing agent-driven systems, the useful signal is the direction: agent identity and scoped permissions are becoming a first-class concern, and they are being framed as familiar web auth (OAuth) rather than something exotic. That makes it testable with ordinary API and security test practice once the spec lands. Until then this is an announcement, not a deployed standard.

## Sources

- [Meta Joins Walmart, Shopify, Stripe to Back New AI Agent Standard for Business, Channel Insider](https://www.channelinsider.com/ai/news-meta-walmart-shopify-stripe-ai-agent-standard/)
- [Meta and Sierra Introduce Personal Agent Protocol for Business Interactions, Let's Data Science](https://letsdatascience.com/news/meta-and-sierra-introduce-personal-agent-protocol-for-busine-13aa4537)
