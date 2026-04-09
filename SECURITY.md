# Security Policy

## Reporting Vulnerabilities

If you discover a security vulnerability in any Quantum Pipes package, please report it responsibly.

**Email:** security@quantumpipes.com

**Do not** open a public GitHub issue for security vulnerabilities.

### What to Include

- Package name and version
- Description of the vulnerability
- Steps to reproduce
- Potential impact assessment

### Response Timeline

- **Acknowledgment:** Within 48 hours
- **Initial assessment:** Within 5 business days
- **Fix or mitigation:** Depends on severity, but we prioritize security above all else

## Supported Versions

We provide security updates for the latest minor version of each package.

| Package | Supported Version |
|---|---|
| qp-capsule | 1.5.x |
| qp-vault | 1.5.x |
| qp-conductor | 0.9.x |
| qp-scout | 0.1.x |
| capsule-litellm | 0.1.x |

## Cryptographic Standards

All Quantum Pipes packages use post-quantum cryptography:

- SHA3-256 (FIPS 202)
- Ed25519 (RFC 8032)
- ML-DSA-65 (FIPS 204) for post-quantum signatures
- ML-KEM-768 (FIPS 203) for post-quantum key exchange
- AES-256-GCM (FIPS 197) for symmetric encryption
- Argon2id (RFC 9106) for password hashing

**Never used:** RSA, ECDSA P-256, MD5, SHA1, DES, 3DES, RC4.
