# Quantum Pipes Documentation

**Intelligence that belongs to you.**

Quantum Pipes is an offline-first AI platform with cryptographic accountability. 42 capabilities. 14 specialist agents. One sovereign platform. Runs on your hardware, proves what it did, and never phones home.

100% Local. Zero Cloud. Air-Gap Ready.

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.11%2B-blue.svg)](https://python.org)
[![Go](https://img.shields.io/badge/go-1.21%2B-00ADD8.svg)](https://go.dev)

---

## Why Quantum Pipes?

Most AI platforms ask you to trust them with your data. Quantum Pipes makes trust unnecessary by making everything provable.

**42 capabilities, not one chatbot.** Research, legal analysis, code generation, security audit, compliance checks, voice transcription, and 36 more. Each governed by policy, not just prompts.

**Honest AI.** Admits uncertainty. Confidence scores on every claim. Reasoning recorded before execution, not after.

**Complete sovereignty.** Zero egress firewall. Models run locally. Data physically cannot leave your infrastructure. Not by promise, by architecture.

**Cryptographic proof.** Post-quantum signatures on every decision. Hash-chained audit trail. 48 conformance test vectors. Verifiable from Python, TypeScript, or Go.

---

## The Sovereign Stack

Quantum Pipes is a composable ecosystem of independent packages. Use one, use all.

### Platform

| Package | Purpose | Install |
|---|---|---|
| [**quantumpipes**](https://github.com/quantumpipes/core) | Intelligence engine: 42 capabilities, 14 specialists, OODA loops, inference cascade | `pip install quantumpipes` |

### Specialist Packages

| Package | Purpose | Install |
|---|---|---|
| [**qp-capsule**](https://github.com/quantumpipes/capsule) | Audit protocol: CPS v1.0 spec, 6-section records, hash-chained, dual-signed | `pip install qp-capsule` |
| [**qp-vault**](https://github.com/quantumpipes/vault) | Knowledge store: 4 trust tiers, hybrid search (70% vector + 30% keyword), Merkle verification | `pip install qp-vault` |
| [**qp-conductor**](https://github.com/quantumpipes/conductor) | Orchestration: goal decomposition, 5 autonomy levels, agent swarms, adaptation engine | `pip install qp-conductor` |
| [**qp-scout**](https://github.com/quantumpipes/scout) | Knowledge pipeline: multi-provider crawling, SAFE fact-checking, 4-tier trust lifecycle | `pip install qp-scout` |
| [**capsule-litellm**](https://github.com/quantumpipes/capsule-litellm) | LLM bridge: one-line audit trail for any LLM call via LiteLLM | `pip install capsule-litellm` |

### Cross-Language

| Package | Purpose | Install |
|---|---|---|
| [**capsule-go**](https://github.com/quantumpipes/capsule-go) | Go verification: Capsule integrity, chain linkage, Ed25519 signatures (stdlib only) | `go get github.com/quantumpipes/capsule-go` |

### Infrastructure

| Package | Purpose | Install |
|---|---|---|
| [**conduit**](https://github.com/quantumpipes/conduit) | Internal infrastructure: auto-DNS, auto-TLS, service routing, GPU monitoring | Shell scripts |
| [**tunnel**](https://github.com/quantumpipes/tunnel) | Secure boundary: WireGuard + post-quantum TLS, 57 concurrent services, 9 CLI commands | Shell scripts |

---

## How It Works

```
┌─────────────────────────────────────────────────────────┐
│  You describe a goal in plain language                   │
└────────────────────────┬────────────────────────────────┘
                         v
┌─────────────────────────────────────────────────────────┐
│  CONDUCTOR decomposes it into capability-ordered tasks    │
│  Assigns autonomy level (L0-L4) based on risk            │
│  Dispatches specialist agents                            │
└────────────────────────┬────────────────────────────────┘
                         v
┌─────────────────────────────────────────────────────────┐
│  CORE agents execute: PERCEIVE > REASON > DECIDE > ACT   │
│  Each agent has tools, knowledge (Vault), and policies   │
│  Every iteration checks the kill switch                  │
└────────────────────────┬────────────────────────────────┘
                         v
┌─────────────────────────────────────────────────────────┐
│  Every action seals a CAPSULE                            │
│  Trigger > Context > Reasoning > Authority > Execution   │
│  > Outcome. SHA3-256 hashed. Ed25519 + ML-DSA-65 signed │
│  Hash-chained into immutable temporal ordering           │
└─────────────────────────────────────────────────────────┘
```

---

## Quick Start

### Prerequisites

- Linux or macOS
- Docker (with Compose)
- 16 GB+ RAM
- GPU optional (CPU inference works, GPU is faster)

### Three commands

```bash
git clone https://github.com/quantumpipes/core.git
cd core
make go
```

This pulls images, generates cryptographic keys, starts all services, and opens `https://qp.local`.

### First steps

1. **Create a Space** -- organize your work into isolated contexts
2. **Upload documents** -- Vault processes, chunks, embeds, and trust-scores them
3. **Ask Conductor** -- describe what you need in plain language

### Deployment tiers

| Tier | Users | Inference | Storage | Best for |
|---|---|---|---|---|
| **Solo** | 1-3 | Ollama | SQLite | Individual use, evaluation |
| **Team** | 10-50 | vLLM | PostgreSQL | Department deployment |
| **Enterprise** | Unlimited | NVIDIA NIMs | PostgreSQL + pgvector | Organization-wide, air-gapped |

---

## Package Deep Dives

### Capsule: The Audit Protocol

The irreducible foundation. Every AI action in the ecosystem seals a Capsule.

```
forall action: exists capsule
```

A Capsule is a tamper-evident record with six sections:

| Section | What It Captures |
|---|---|
| **Trigger** | What initiated this operation (type, source, timestamp, request, correlation ID) |
| **Context** | Environment at decision time (agent ID, session, environment) |
| **Reasoning** | Pre-execution analysis (options considered, selected option, confidence, model, prompt hash) |
| **Authority** | Who approved and under what policy (approver, policy reference, escalation reason) |
| **Execution** | What actions were taken (tool calls, duration, resources used) |
| **Outcome** | Results and side effects (status, result, summary, error, metrics) |

**Cryptographic sealing:**
- **SHA3-256** content hash (Keccak sponge construction)
- **Ed25519** digital signature (classical)
- **ML-DSA-65** post-quantum signature (FIPS 204)
- **Hash chain** linking each Capsule to its predecessor

**8 Capsule types:** agent, tool, system, kill, workflow, chat, vault, auth

**3 language SDKs:**

| Language | Package | Capabilities |
|---|---|---|
| Python | `qp-capsule` | Create, seal, verify, SQLite/PostgreSQL storage, CLI, FastAPI integration, `@capsules.audit` decorator |
| TypeScript | `@quantumpipes/capsule` | Create, seal, verify, chain validation, canonical JSON |
| Go | `capsule-go` | Verify hash, verify signature, chain checks, canonicalize |

**48 conformance test vectors** ensure cross-language interoperability.

**Content-addressable URI scheme:**

| Form | Example | Use case |
|---|---|---|
| Hash | `capsule://sha3_7f2a4b8c...` | Content-addressable lookup |
| Chain + Sequence | `capsule://chain/42` | Chain-relative reference |
| UUID | `capsule://550e8400-...` | Direct record lookup |
| Fragment | `capsule://sha3_...#reasoning/confidence` | JSON Pointer into sections |

### Vault: Governed Knowledge

Content-addressed storage with trust tiers that affect search ranking.

**4 trust tiers:**

| Tier | Search Boost | Purpose |
|---|---|---|
| **CANONICAL** | 1.5x | Source of truth. Verified, immutable reference documents. |
| **WORKING** | 1.0x | Active documents under development or revision. |
| **EPHEMERAL** | 0.7x | Temporary context. Automatically cleaned up. |
| **ARCHIVED** | 0.25x | Historical records. Searchable but deprioritized. |

**Hybrid search:** 70% pgvector semantic similarity + 30% pg_trgm keyword matching, multiplied by trust tier boost and freshness score.

**4 data classifications:** PUBLIC, INTERNAL, CONFIDENTIAL, RESTRICTED

**6 lifecycle states:** DRAFT, REVIEW, ACTIVE, SUPERSEDED, EXPIRED, ARCHIVED

**3 memory layers:** OPERATIONAL (fast, recent), STRATEGIC (organizational knowledge), COMPLIANCE (regulatory, immutable)

**Integrity verification:** Merkle tree verification, contradiction detection, staleness detection, duplicate identification. Content-addressed with SHA3-256.

### Conductor: Cognitive Orchestration

Decomposes natural language goals into capability-ordered execution plans.

**5 autonomy levels:**

| Level | Name | Oversight | When to use |
|---|---|---|---|
| L0 | BLOCKED | Full stop. Human must initiate. | Destructive operations on production systems |
| L1 | SUPERVISED | Every step reviewed. | Sensitive financial or legal tasks |
| L2 | CHECKPOINT_MAJOR | High-risk steps reviewed. | Mixed-risk workflows |
| L3 | CHECKPOINT_END | Final output reviewed. | Default. Most tasks. |
| L4 | FULL | Audit trail only. | Low-risk, high-confidence, established track record |

**42 capabilities across 9 domains:**

| Domain | Count | Examples |
|---|---|---|
| Analysis | 10 | Financial, market, risk, pattern detection, legal, accounting |
| Planning | 4 | Strategic, project, resource, task decomposition |
| Creation | 5 | Code generation, tests, content, documentation, formal documents |
| Investigation | 5 | Research, debugging, root cause, vision, performance analysis |
| Validation | 3 | Code review, compliance check, evidence collection |
| Communication | 2 | Stakeholder updates, progress reporting |
| Execution | 2 | Deployment, shell execution |
| Audio | 4 | Transcription, understanding, synthesis, diarization |
| Sysadmin | 5 | Health check, diagnosis, remediation, validation, learning |

**7 subsystems:**

| Subsystem | Function |
|---|---|
| **Goal Analyzer** | Natural language to capability requirements with intent classification |
| **Capability Composer** | Requirements to dependency-ordered execution plan via topological sort |
| **Autonomy Calculator** | Risk and confidence analysis to determine human oversight level |
| **Orchestrator** | Multi-agent dispatch with parallel execution and Capsule-sealed decisions |
| **Checkpoint Manager** | Human approval gates with async wait patterns for high-risk operations |
| **Adaptation Engine** | Signal capture, pattern mining, and safety-validated self-improvement |
| **Drift Detector** | Behavioral consistency monitoring via cosine distance on embedding fingerprints |

**4 hardcoded safety constraints:**

1. HIGH-risk tasks (deploy, delete, decision) never auto-approved. Hardcoded, not configurable.
2. Security agents (auditor, deployer) never receive prompt modifications from the adaptation engine.
3. Injection patterns (shell, SQL, path traversal, secret leakage) blocked at the safety gate.
4. Kill switch checked on every agent iteration. Once killed, stays killed.

### Conduit: Internal Infrastructure

One command registers a service with DNS + TLS + reverse proxy routing.

- **Auto-DNS** via dnsmasq for internal name resolution
- **Ed25519 TLS certificates** from an internal Caddy CA
- **GPU monitoring** (utilization, memory, temperature, processes)
- **Health checks** with structured JSON audit logging
- **Admin dashboard** with 6 views
- Air-gap compatible. No internet required.

### Tunnel: Secure Boundary

Double-encrypted remote access to any device, from anywhere.

**Dual encryption:**

| Layer | Protocol | Algorithms |
|---|---|---|
| Outer | WireGuard | X25519, ChaCha20-Poly1305 |
| Inner | PQ-Hybrid TLS 1.3 | X25519MLKEM768 (post-quantum key exchange) |

- 57 concurrent services supported
- Split-tunnel routing
- QR codes for mobile peer onboarding
- Instant key revocation (no grace period)
- 9 CLI commands for relay setup, peer management, key rotation, service exposure

**Conduit handles the inside (service mesh). Tunnel handles the outside (remote access).** Together they form a complete air-gapped networking layer.

### Scout: Knowledge Pipeline

Trust-governed ingestion from external sources.

**4-tier trust lifecycle:** POTENTIAL (discovered) > CANDIDATE (crawled) > VERIFIED (fact-checked) > CANONICAL (trusted)

**Dual-gate defense:** Content verification gate + fact verification gate before anything enters the knowledge store.

**Multi-provider crawling** with crawl4ai integration and HTTP fetching. Feeds verified content into Vault.

### capsule-litellm: LLM Audit Bridge

One line of code wraps every LLM call with a cryptographic audit trail:

```python
import litellm
from capsule_litellm import CapsuleLogger

litellm.callbacks = [CapsuleLogger()]

# Every litellm.completion() now seals a Capsule with:
# - Model selection and provider
# - Prompt hash (SHA3-256, not the full prompt)
# - Token counts (input, output, total)
# - Duration and latency
# - Errors and retries
```

Works with any provider LiteLLM supports: OpenAI, Anthropic, Ollama, vLLM, NVIDIA NIMs, and 100+ more.

---

## Architecture

### Dependency Graph

```
                    ┌─────────────┐
                    │   capsule   │  <-- Foundation (zero QP deps)
                    └──────┬──────┘
                           |
              ┌────────────┼────────────┐
              |            |            |
        ┌─────v─────┐ ┌───v────┐ ┌────v──────┐
        │   vault    │ │ scout  │ │ conductor │
        └─────┬──────┘ └───┬────┘ └────┬──────┘
              |            |            |
              └────────────┼────────────┘
                           |
                    ┌──────v──────┐
                    │    core     │  <-- Orchestrates all packages
                    └─────────────┘

  Independent:
  capsule-go (Go verifier)    conduit + tunnel (infrastructure pair)
  capsule-litellm (LLM bridge)
```

Every package optionally depends on Capsule for audit trails. Core depends on all specialist packages. Each package works independently.

### Cryptographic Standards

| Operation | Algorithm | Standard |
|---|---|---|
| Content hashing | SHA3-256 | FIPS 202 |
| Digital signatures | Ed25519 | RFC 8032 |
| Post-quantum signatures | ML-DSA-65 | FIPS 204 |
| Post-quantum key exchange | X25519 + ML-KEM-768 | RFC 7748 + FIPS 203 |
| Symmetric encryption | AES-256-GCM | FIPS 197 |
| Password hashing | Argon2id | RFC 9106 |

**Never used:** RSA, ECDSA P-256, MD5, SHA1, DES, 3DES, RC4.

### Three Properties of Trustworthy AI

Every package is designed around three guarantees:

1. **Verified** -- claims are checked against sources (Vault integrity checks, Scout fact-checking, Conductor verification)
2. **Recorded** -- every action creates a cryptographically sealed Capsule (`forall action: exists capsule`)
3. **Controllable** -- any agent can be stopped instantly (Kill Switch: SOFT for graceful shutdown, HARD for immediate termination, cannot be disabled)

---

## Compliance

Quantum Pipes maps to 11 regulatory frameworks:

| Framework | Scope | Key Capsule Mapping |
|---|---|---|
| [SOC 2](compliance/soc2.md) | Trust Services Criteria | Capsule audit trail satisfies CC6, CC7, CC8 |
| [HIPAA](compliance/hipaa.md) | Healthcare data protection | Vault data classification + Capsule access logging |
| [GDPR](compliance/gdpr.md) | EU data privacy | Data sovereignty (zero egress) + right-to-erasure support |
| [NIST AI RMF](compliance/nist-ai-rmf.md) | AI risk management | Conductor autonomy levels + Capsule reasoning records |
| [EU AI Act](compliance/eu-ai-act.md) | European AI regulation | Pre-execution reasoning capture + human oversight gates |
| [FedRAMP](compliance/fedramp.md) | Federal cloud security | Air-gap deployment + post-quantum cryptography |
| [NIST SP 800-53](compliance/nist-sp-800-53.md) | Federal security controls | Kill Switch (SI-17), Capsule (AU-2, AU-3, AU-10) |
| [ISO 27001](compliance/iso27001.md) | Information security management | Vault trust tiers + Capsule chain integrity |
| [CMMC](compliance/cmmc.md) | DoD cybersecurity maturity | Zero egress + cryptographic audit + network isolation |
| [FINRA](compliance/finra.md) | Financial industry regulation | Capsule immutability + Vault record retention |
| [PCI DSS](compliance/pci-dss.md) | Payment card data security | Vault data classification + encryption at rest |

---

## Documentation

### [Getting Started](getting-started/)

Pick a path based on what you need:

- [I want cryptographic audit trails](getting-started/audit-trails.md) -- start with qp-capsule
- [I want governed document intelligence](getting-started/document-intelligence.md) -- start with qp-vault
- [I want AI orchestration](getting-started/orchestration.md) -- start with qp-conductor
- [I want air-gapped networking](getting-started/networking.md) -- start with conduit + tunnel
- [I want the complete platform](getting-started/full-platform.md) -- start with quantumpipes (Core)

### [Architecture](architecture/)

System design: how packages compose, the trust model, dependency graph, cryptographic standards.

### [Guides](guides/)

Narrative walkthroughs explaining concepts from first principles: what Quantum Pipes is, the philosophy behind it, and deep dives into each major capability.

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

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on contributing to Quantum Pipes documentation and code.

## Security

To report vulnerabilities, see [SECURITY.md](SECURITY.md). Do not open public issues for security concerns.

## License

All Quantum Pipes packages are licensed under [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0).

Copyright 2024-2026 Quantum Pipes Technologies, LLC.
