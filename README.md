# PaymentSentinel

> Real-Time Transaction Defense for AI Agent Payments

## What This Is

PaymentSentinel is an open-source transaction monitoring system that protects payment systems from errors and fraud when AI agents are initiating transactions. It sits between your AI agents and payment networks, validating every transaction before it goes through.

## The Current Landscape

Payment systems are getting faster. Real-time payments (like FedNow, RTP) settle instantly - there's no going back once a payment is processed. At the same time, companies are starting to let AI agents initiate payments automatically - for customer service, bill pay, treasury management, etc.

This creates a new risk: what if an AI agent makes a mistake? Or gets compromised? Or gets tricked into sending money to the wrong place? With real-time payments, you can't just reverse it later. You need to catch problems before they happen.

Traditional fraud prevention tools were built for human-initiated transactions. They look for patterns like "user logged in from new location" or "unusual spending amount." But AI agents have different patterns - they might process thousands of transactions quickly, or they might have access to multiple accounts. We need new tools that understand AI agent behavior.

## Why We Built This

We built PaymentSentinel because we saw payment systems and AI agents converging, but the safety tools weren't keeping up. Real-time payments are great for users, but they require real-time protection.

By open-sourcing this:
- **Organizations can deploy AI payment features safely** - Knowing transactions are being validated
- **The community can improve detection** - More use cases means better fraud patterns
- **Transparency builds trust** - Payment security should be open and auditable
- **Smaller companies can benefit** - Not everyone can build this from scratch

This is about making AI-powered payments safer, not stopping innovation.

## What PaymentSentinel Does

PaymentSentinel intercepts every payment instruction from AI agents and validates it in real-time (under 50ms). It checks:
- Is this transaction consistent with the customer's history?
- Is the amount unusual?
- Is the destination suspicious?
- Is the AI agent behaving normally?
- Does this violate any business rules?

If something looks risky, it can hold the transaction for review, block it entirely, or escalate it. It works with major payment networks (ACH, FedNow, RTP, SWIFT) and can integrate with your existing fraud prevention systems.

## How We're Different

### vs. Traditional Fraud Prevention (FICO Falcon, Featurespace)

**What They Do**: Fraud detection for human-initiated transactions, card-based patterns.

**What We Do**: Real-time validation specifically for AI agent transactions.

**Our Advantage**:
- **Agent-Aware**: We know which AI agent initiated each transaction and their behavior patterns
- **Real-Time Payment Rails**: Pre-integrated with ACH, FedNow, RTP, SWIFT (they focus on cards)
- **Sub-50ms Latency**: Fast enough for real-time payments (they're batch-oriented)
- **AI Agent Patterns**: Understands agent behavior, not just user behavior
- **Circuit Breakers**: System-wide protection, not just per-transaction

**The Reality**: FICO Falcon is great for credit card fraud. But when an AI agent processes 10,000 payments in 5 minutes, FICO sees "normal transactions." We see "agent velocity anomaly - potential compromise."

### vs. Payment Processor Native Tools (Stripe Radar, Adyen)

**What They Do**: Fraud prevention for their own payment network.

**What We Do**: Vendor-agnostic, works across all payment networks, AI agent-specific.

**Our Advantage**:
- **Multi-Network**: Works with ACH, FedNow, RTP, SWIFT, not just one processor
- **Independent**: Not tied to a payment processor, so you're not locked in
- **AI-Focused**: Built for agent transactions, not retrofitted
- **Custom Policies**: Banking-specific rules they don't offer

**The Reality**: Stripe Radar protects Stripe payments. We protect ALL your payment rails, regardless of processor.

### vs. Build-It-Yourself

**What They Do**: Internal teams building custom fraud systems.

**What We Do**: Open-source, pre-built integrations, community-maintained.

**Our Advantage**:
- **Save 12-18 Months**: Don't rebuild payment network integrations
- **Proven Patterns**: Battle-tested fraud detection, not experimental
- **Always Updated**: New payment networks? We add support. New fraud patterns? We add detection.
- **Cost**: Free vs. $500K+ internal development

**The Reality**: You could build this. But payment network integrations are complex. We've already done the hard work.

## Who This Is For

This is for:
- **Developers** building AI-powered payment features
- **Risk teams** managing payment fraud
- **Operations teams** handling payment processing
- **Organizations** deploying AI agents that touch money
- **Mid-market fintech** who can't afford $500K+ fraud platforms

## Current Status

This is an open-source project in active development. We're building this in public because we believe payment systems need better protection for the AI era.

## Getting Started

1. Check out the [product specification](product-specification.md) for detailed technical information
2. Review the [Cursor AI prompts](CURSOR_AI_PROMPTS_COMPLETE.md) if you want to build your own version
3. Read the [executive brief](EXECUTIVE_BRIEF.md) for a high-level overview
4. Contribute, fork, or use this however it helps you

## Related Projects

This is part of a suite of 10 open-source tools for AI agent security in finance:

1. [AgentGuard](../agentguard) - Unified AI Agent Security & Governance
2. [CodeShield AI](../codeshield-ai) - Secure Development Gateway
3. [PaymentSentinel](../paymentsentinel) - Real-Time Transaction Defense
4. [LegacyBridge](../legacybridge-ai-gateway) - Legacy Core Protection
5. [ModelWatch](../modelwatch) - AI Model Integrity Monitoring
6. [FleetCommand](../fleetcommand) - Multi-Agent Orchestration
7. [PromptShield](../promptshield) - Input Validation System
8. [IdentityVault](../identityvault-agents) - Non-Human IAM
9. [SupplyChainGuard](../supplychainguard) - Development Tool Security
10. [ComplianceIQ](../complianceiq) - Regulatory Reporting

## Contributing

We welcome contributions! Whether it's:
- Bug reports
- Feature suggestions
- Code improvements
- Documentation fixes
- New fraud patterns to detect

Everything helps make these tools better for everyone.

## License

MIT License - Use it however you want.

## Disclaimer

This is open-source software provided as-is. Use at your own risk. We're not responsible for any losses or damages. This is a community project, not a commercial product.

---

**Built with the hope that open collaboration can make AI-powered payments safer for everyone.**
