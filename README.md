# Quantum Pipes Documentation

The official documentation for the [Quantum Pipes](https://github.com/quantumpipes) open-source ecosystem: offline-first AI with cryptographic accountability.

---

## Packages

Quantum Pipes is a composable ecosystem of independent packages. Use one, use all.

| Package | What It Does | Install |
|---|---|---|
| [**qp-capsule**](https://github.com/quantumpipes/capsule) | Tamper-evident audit records (protocol + reference impl) | `pip install qp-capsule` |
| [**qp-vault**](https://github.com/quantumpipes/vault) | Governed knowledge store with trust tiers and hybrid search | `pip install qp-vault` |
| [**qp-conductor**](https://github.com/quantumpipes/conductor) | Cognitive orchestration: goals to agent swarms | `pip install qp-conductor` |
| [**qp-scout**](https://github.com/quantumpipes/scout) | Trust-governed knowledge pipeline: crawl, verify, ingest | `pip install qp-scout` |
| [**capsule-litellm**](https://github.com/quantumpipes/capsule-litellm) | One-line audit trail for any LLM call via LiteLLM | `pip install capsule-litellm` |
| [**capsule-go**](https://github.com/quantumpipes/capsule-go) | Capsule verification in Go (stdlib only) | `go get github.com/quantumpipes/capsule-go` |
| [**conduit**](https://github.com/quantumpipes/conduit) | Internal DNS, TLS, and service routing for air-gapped deployments | Shell scripts |
| [**tunnel**](https://github.com/quantumpipes/tunnel) | WireGuard VPN with post-quantum TLS | Shell scripts |

## Quick Start

Pick a path based on what you need:

- **[I want cryptographic audit trails](getting-started/audit-trails.md)** -- Start with qp-capsule
- **[I want governed document intelligence](getting-started/document-intelligence.md)** -- Start with qp-vault
- **[I want AI orchestration](getting-started/orchestration.md)** -- Start with qp-conductor
- **[I want air-gapped networking](getting-started/networking.md)** -- Start with conduit + tunnel
- **[I want the complete platform](getting-started/full-platform.md)** -- Start with quantumpipes (Core)

## Documentation

### [Getting Started](getting-started/)
Installation guides and "pick your path" entry points for each package.

### [Architecture](architecture/)
System design: how packages compose, the trust model, dependency graph, cryptographic standards.

### [Guides](guides/)
Narrative walkthroughs explaining concepts from first principles: what Quantum Pipes is, the philosophy behind it, the five planes of the system, and deep dives into each major capability.

### [Packages](packages/)
Per-package documentation: architecture, API reference, configuration, and integration patterns.

### [Compliance](compliance/)
Regulatory framework mappings: how Quantum Pipes satisfies SOC 2, HIPAA, GDPR, NIST AI RMF, EU AI Act, FedRAMP, and more.

### [Reference](reference/)
API reference, CLI reference, and configuration reference for the platform.

### [Security](security/)
Security model, threat analysis, vulnerability disclosure policy, and cryptographic design rationale.

### [Examples](examples/)
Complete, runnable examples demonstrating common integration patterns.

---

## Three Properties of Trustworthy AI

Every package in this ecosystem is designed around three guarantees:

1. **Verified** -- claims are checked against sources
2. **Recorded** -- every action creates a cryptographically sealed Capsule
3. **Controllable** -- any agent can be stopped instantly

## The Foundation

```
forall action: exists capsule
```

A [Capsule](architecture/capsule-protocol.md) is a tamper-evident record with six sections: Trigger, Context, Reasoning, Authority, Execution, Outcome. Sealed with SHA3-256 + Ed25519 (+ optional ML-DSA-65 post-quantum). Hash-chained into an immutable temporal ordering. This is the irreducible foundation that makes autonomous AI auditable.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on contributing to Quantum Pipes documentation and code.

## Security

See [SECURITY.md](SECURITY.md) for our vulnerability disclosure policy.

## License

All Quantum Pipes packages are licensed under [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0).
