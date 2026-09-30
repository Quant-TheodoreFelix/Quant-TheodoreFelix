<div align="center">

# Quant Theodore Felix

**Redefining the Paradigm of Security in the Quantum Era**

[![Korean Badge](https://img.shields.io/badge/Read_in-Korean-blue?style=for-the-badge&logo=googletranslate&logoColor=white)](https://github.com/Quant-TheodoreFelix)
[![Quant Github](https://img.shields.io/badge/Quant_Off-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Quant-Off/)
[![Quant Front](https://img.shields.io/badge/Site-Quant_Off-FFFFFF?style=for-the-badge)](https://qu4nt.space/)
[![Qu4nt-Space-Discord](https://img.shields.io/badge/Qu4nt_Space-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://github.com/Quant-Off/)

</div>

---

*“Abandon trust. Choose isolation.”*

I am a lead developer at **Team Quant**, redefining the paradigm of security in response to the advancements in information and communication technology and the rise of quantum computing. I focus on building future-oriented security solutions through high-security infrastructure, compliance, Post-Quantum Cryptography (PQC), and the secure implementation of classical cryptographic algorithms.

[![GitHub Streak](https://streak-stats.demolab.com?user=Quant-TheodoreFelix&theme=github-dark-blue&hide_border=true&locale=en&mode=weekly&card_width=1024)](https://streak-stats.demolab.com/demo/?user=Quant-TheodoreFelix&theme=github-dark-blue&hide_border=true&border_radius=4.5&locale=en&short_numbers=false&date_format=&mode=weekly&exclude_days=&sections=total%2Ccurrent%2Clongest&card_width=1024&card_height=195&type=svg&background-type=solid&properties=background)

## Core Competencies

- **Compliance**
    - Capable of implementing the technical requirements, architecture design, and formal documentation needed to satisfy certification and compliance requirements up to NIST FIPS 140-2/3 L2~4 and Common Criteria (CC) EAL5+.
- **Security Engineering**
    - Possess a deep understanding of next-generation capabilities such as Java JCA/JCE, Project Panama, heap management, efficient data structures, and design-pattern engineering.
    - Highly proficient in Rust — have used it natively from Java as well — and capable of developing software with memory safety and extreme security, including constant-time operations and zeroize-logic design.
- **Quantum Information Science & Technology Research**
    - Through rapid learning ability and a curiosity honed over a long time, I have broad knowledge of quantum information science theory, building outward from a foundation in linear algebra.
    - Have also written introductory books and academic papers to share quantum information science knowledge with others.

## Key Projects

<details>
<summary><h3><a href="https://github.com/Quant-Off/airlock">Airlock</a> | <code>Lead Developer</code></h3></summary>

> A local zero-trust gateway for AI coding agents (2026.07 ~ in progress)
- **Tech**: Rust, Landlock, seccomp, Seatbelt (macOS)
- **Features**:
  - **Capability-based Policy DSL**: A declarative TOML syntax with a decision engine that evaluates five tiers in order: self-protection -> built-in forbid -> user rules -> built-in ask/deny -> defaults.
  - **Kernel-Enforced Sandboxing**: Blocks an agent's file, process, and network behavior directly at the OS boundary via Linux Landlock (files, TCP ports) and macOS Seatbelt (files, exec paths, all outbound traffic).
  - **seccomp Runtime Relay**: Intercepts a child process's `execve`/`connect` calls via seccomp user notifications and records them to the audit log, blocking ABI bypass through architecture mismatches (e.g., x32).
  - **Hash-Chain Audit Log**: An append-only hash chain that detects tampering, reordering, mid-log deletion, and tail truncation, distinguishing entries the kernel actually enforced from entries that were merely observed.
  - **`/dev/tty` Inline Approval**: Requests human approval for risky actions, with an automatic denial past a response timeout (300 seconds) to prevent the supervisor thread from deadlocking.
  - **Transparent Disclosure of Limits**: Path canonicalization (traversal, symlinks, case-bypass) is isolated into its own crate (`airlock-canonical`), and any unenforced items are declared in a banner at session start.

</details>

<details>
<summary><h3><a href="https://github.com/Quant-Off/iso-light-k0">ISO-LIGHT-K0 (K0 Microkernel)</a> | <code>Lead Developer</code></h3></summary>

> An ultra-lightweight Rust `no_std` high-security microkernel for establishing closed (air-gapped) infrastructure (2026.03 ~ in progress)
- **Tech**: Rust, QEMU, Multiboot2, x86(64), Arm(64), Docker
- **Features**:
  - **Capability-based Access Control**: Unforgeable token-based resource access control, powered by Hash-DRBG-SHA256 (seeded with RDSEED/RDRAND).
  - **Synchronous IPC (Rendezvous Model)**: Message-passing inter-process communication with registered endpoints such as `EP_CRYPTO` / `EP_SIGN` / `EP_SYSTEM`.
  - **Memory Isolation**: Minimal `unsafe`, static allocation only (no `alloc`), 4-level page tables, KASLR, W^X policy, Higher-Half kernel/user separation, and `CR0.WP` + `CR4.SMEP/SMAP/UMIP` security bits.
  - **Ring 3 User Space**: Static ELF64 loader, `syscall/sysret` ABI, per-CPU `swapgs`, and SMAP `stac/clac` user-memory validation.
  - **Built-in Kernel Security Services**: AES-256-GCM, ChaCha20-Poly1305, BLAKE3, SHA-2/3, HKDF, Ed25519/Ed448, X448 DH, and the ML-DSA-44 chunked protocol.
  - **TLS 1.3 PSK Handshake**: Closed/External profiles and `psk_pq_hybrid_ke` (X25519 + ML-KEM-768) post-quantum hybrid key exchange.
  - **HSM Abstraction + Soft Keystore Fallback**: A single code path is reused across HSM-backed environments and a static-pool PSK Soft Keystore via the `HsmDriver` trait, with a one-way `Provisioned` → `Wiped` lifecycle.
  - **Stack Protection**: Guard-page canaries on IST and boot stacks, plus an EAL4+ safe panic handler that halts immediately with no information leakage.

</details>

<details>
<summary><h3><a href="https://github.com/Quant-Off/elib-k0-nt">elib-k0-nt</a> | <code>Lead Developer</code></h3></summary>

> A `no_std`-based, closed and defensively-engineered cryptographic primitives module for ISO-LIGHT-K0 (2026.03 ~ in progress)
- **Tech**: Rust, `no_std`, **a variety of cryptographic algorithms**
- **Features**:
  - **Independent Implementation Principle**: Each cryptographic crate is implemented independently with no shared core dependency, so data flows cannot leak across crate boundaries.
  - **Hashing**: In-house SHA-2, SHA-3, SHAKE ([FIPS 202](https://csrc.nist.gov/pubs/fips/202/final)), and BLAKE2 implementations.
  - **RNG**: Hash DRBG per NIST SP 800-90Ar1.
  - **Digital Signatures**: Ed25519 and Ed448 (including context signatures).
  - **Key Establishment (KEX)**: X25519, X448.
  - **AEAD / Block Ciphers**: AES, ChaCha20-Poly1305.
  - **Post-Quantum Cryptography (PQC)**: ML-KEM, ML-DSA.
  - **Side-Channel Defense**: An in-house `constant-time` operations module and a multi-architecture-aware `zeroize` volatile-erasure routine.

</details>

<details>
<summary><h3><a href="https://github.com/Quant-Off/lumen">Lumen</a> | <code>Lead Developer</code></h3></summary>

> A verifiable, air-gap-friendly AI agent framework for zero-trust environments (2026.04 ~ in progress)
- **Tech**: Rust, `wasmtime`, `candle`, `ezkl` / `halo2`, BLAKE3, Ed25519
- **Features**:
  - **Hybrid zkML Pipeline**: A selective-proof strategy that keeps expensive LLM inference inside a TEE and generates ZKPs only for tool-routing decisions and output filtering. `Verification::ZkVerified` and `Verification::CommitmentOnly` are kept as separate type-system variants by design.
  - **Privilege-Separated Host-WASM Sandbox**: The host (TEE) handles LLM inference, the policy engine, and Capability issuance/verification, while the WASM sandbox only handles agent logic, tool-call routing, and output filtering. They communicate exclusively over an attested secure channel.
  - **Capability Token Policy Engine**: Four-stage verification (signature, expiry, audience, nonce) backed by an LRU nonce table to prevent replay.
  - **Attested SecureChannel**: Ed25519 mutual handshake + AES-GCM-256 + X25519 ephemeral KEX with signed framing, where $(\text{epoch}, \text{seq})$ sequence numbers reject replays.
  - **Deterministic Control Module**: Integer fixed-point (Q16.16, Q8.24) + BLAKE3 + BTreeMap + wasmtime with SIMD disabled, jointly guaranteeing ZKP reproducibility.
  - **High-Speed Defense & Provenance**: A jailbreak defense engine driven by lexicon/regex/heuristics, BLAKE3 + Ed25519 provenance verification, automatic CycloneDX SBOM generation, and zero-downtime model-pin rotation (`PinSet`).

</details>

<details>
<summary><h3>Lumiere | <code>Lead Developer</code></h3></summary>

> An AI agent that analyzes, reasons about, and resolves security vulnerabilities in medium-scale codebases (2026.03 ~ in progress)
- **Tech**: Rust, Python, PostgreSQL, MySQL
- **Features**:
  - **V2P (Vulnerable-to-Patch) Core Dataset Integration & Normalization**: Integration and normalization of multiple datasets — including NVD-API-driven backfilling of `severity` and `diff`, and `lang` standardization — producing a `lumiere-v2p-dset` on the order of several million rows.
  - **Patch-Suggestion / Reasoning & Chain-of-Thought Dataset Construction**: A multi-stage dataset designed for Fine-Tuning, SFT, and Multi-Turn training strategies.
  - **Agentic Harness**: Capable of analyzing codebases of up to ~50K lines, inferring residual vulnerabilities, suggesting patches, and proposing improved designs.
  - **Extended Scenarios**: Reverse engineering of web/application targets, plus a "guardian" role monitoring network packets and anomalous traffic.

</details>

<details>
<summary><h3><a href="https://github.com/Quant-Off/entanglementlib">EntanglementLib (Java)</a> | <code>Lead Developer</code></h3></summary>

> A high-security entanglement library for financial and large-enterprise deployments (2025.12 ~ 2026.04, pre-release stage)
- **Tech**: Java 25, Gradle 9.2.0 (Kotlin DSL), Project Panama (Foreign Function & Memory API)
- **Features**:
  - Engineered an entanglement library with a security-grade design targeting financial and large-enterprise use, leveraging Project Panama to efficiently bridge Rust native code through the Foreign Function & Memory API.
  - Implemented strict Zero-Trust principles, analyzing Java-Owned (JO) and Rust-Owned (RO) allocation patterns to design safe Off-Heap memory interaction with no external dependencies.
  - Applied FIPS 140-3-aligned single-bottleneck pass-through and performed physical erasure (zeroization) of sensitive data after security-critical computations on the Rust side.

</details>

<details>
<summary><h3><a href="https://github.com/Quant-Off/entlib-native">entlib-native (Rust)</a> | <code>Lead Developer</code></h3></summary>

> A native cryptographic module that guarantees integrity-preserving communication with EntanglementLib (2026.01 ~ 2026.04)
- **Tech**: Rust, FFI (Foreign Function Interface)
- **Features**:
  - Established FFI boundary communication for safe interop with the EntanglementLib (Java) side, and designed sensitive-data wrapper structures usable under both the JO and RO patterns.
  - Implemented Base64 and Hex codecs, HKDF, HMAC, SHA-2/3, the SHAKE family, and Hash DRBG per NIST SP 800-90Ar1.
  - Delivered a stable CC EAL4 implementation and authored the architectural specification for the EAL5+ extension path.

</details>

## Tech Stack & Arsenal

<div align="center">


|                                               Languages                                                |                                               Tools & Ecosystems                                                |                                                     DevOps & Infra                                                     |                                                    OS & Arch                                                     |
|:------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------:|
| ![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)  |   ![Gradle](https://img.shields.io/badge/Gradle-02303A?style=for-the-badge&logo=gradle&logoColor=white)   |  ![AWS](https://img.shields.io/badge/amazon_Web_services-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)   |      ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)       |
| ![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white) |    ![Cargo](https://img.shields.io/badge/Cargo-000000?style=for-the-badge&logo=rust&logoColor=white)     |   ![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)    | ![Arch Linux](https://img.shields.io/badge/arch_linux-1793D1?style=for-the-badge&logo=archlinux&logoColor=white) |
|    ![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)    | ![Postgres](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white) | ![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white) |        ![macos](https://img.shields.io/badge/macos-000000?style=for-the-badge&logo=macos&logoColor=white)        |
|                                                                                                        |          ![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)           |              ![CI/CD](https://img.shields.io/badge/CI%2FCD-Security_Scanning-4D4D4D?style=for-the-badge)               |                                                                                                                  |

</div>

<br>

## Philosophy

**The highest level of security does not compromise with convenience.**
I prioritize **top-tier security** and **stability & performance** at every stage of system development. Based on defensive programming, I continuously review code to create faster and more efficient data flows, but I never write code for the sake of convenience for other developers. Discomfort is the price paid for stronger security.

**All data must be protected without exception.**
This is why I chose the path of security engineering. Recognizing that individuals can never be completely independent, I do not trust the origin of any information collected from a system perspective, and I strive to design architectures that can operate independently. If you have an environment worth protecting, you must protect it completely. Under any circumstances, data must be kept fully secure from everyone except you and your teammates.

To achieve my goal of **military- and government-grade security**, I embed the principle of *“Abandon trust (Zero-Trust), Choose isolation (Air-Gapped)”* into all of my technical designs.
This philosophy serves as the foundation for every stage, from architecture design to implementation.
I acknowledge my limitations every day and continuously work to transform complex abstract concepts into robust code that anyone can understand.

---

<div align="center">
  <i>Let's build an uncompromised future.</i><br>
  <i>Contact: <a href="mailto:qtfelix@qu4nt.space">qtfelix@qu4nt.space</a></i><br>
  <i><a href="https://qu4nt.space/docs/getting-started/onboarding">Team Quant Onboarding Guide</a></i>
</div>