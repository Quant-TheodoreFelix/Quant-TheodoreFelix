<div align="center">

# Quant Theodore Felix

**Redefining the Paradigm of Security in the Quantum Era**

[![English Badge](https://img.shields.io/badge/Read_in-English-blue?style=for-the-badge&logo=googletranslate&logoColor=white)](https://github.com/Quant-TheodoreFelix/Quant-TheodoreFelix/blob/main/README_EN.md)
[![Quant Github](https://img.shields.io/badge/Quant_Off-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Quant-Off/)
[![Quant Front](https://img.shields.io/badge/Site-Quant_Off-FFFFFF?style=for-the-badge)](https://qu4nt.space/)
[![Qu4nt-Space-Discord](https://img.shields.io/badge/Qu4nt_Space-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://github.com/Quant-Off/)

</div>

---

*“신뢰를 버리고 고립을 선택하라.”*

정보통신 기술의 진보와 양자 컴퓨팅의 부상에 대응하여 보안의 패러다임을 재정의하고 있는 **팀 퀀트(Quant)** 소속 리드 개발자입니다. 고보안 인프라, 컴플라이언스, 고전 및 양자-내성 암호(Post-Quantum Cryptography) 알고리즘의 안전한 구현을 통해 미래 지향적인 보안 솔루션을 구축하는 데 주력하고 있습니다.

[![GitHub Streak](https://streak-stats.demolab.com?user=Quant-TheodoreFelix&theme=github-dark-blue&hide_border=true&locale=ko&mode=weekly&card_width=1024)](https://streak-stats.demolab.com/demo/?user=Quant-TheodoreFelix&theme=github-dark-blue&hide_border=true&border_radius=4.5&locale=ko&short_numbers=false&date_format=&mode=weekly&exclude_days=&sections=total%2Ccurrent%2Clongest&card_width=1024&card_height=195&type=svg&background-type=solid&properties=background)

## Core Competencies

- **컴플라이언스 및 아키텍처**
  - NIST FIPS 140-2/3 L2~4, CC(Common Criteria) EAL5+ 까지 인증 및 규정 준수 사항을 만족하는 아키텍처 설계가 가능합니다.
- **보안 엔지니어링**
  - Java JCA/JCE 기능에 대해 높은 이해도를 가집니다. 또한 Rust 언어를 네이티브로 사용하여 메모리 안정성 및 극도의 보안성을 가진 소프트웨어를 개발할 수도 있습니다.
- **양자정보과학기술 연구**
  - 빠른 습득력과 어릴 때부터 연마한 호기심을 통해 양자정보과학 이론의 기초가 단단합니다. 이는 단 6개월만에 습득한 지혜라고 자부할 수 있습니다.

## Key Projects

### [ISO-LIGHT-K0 (K0 Microkernel)](https://github.com/Quant-Off/iso-light-k0) | `Lead Developer`

> 폐쇄형 인프라 확립을 위한 Rust `no_std` 초경량 보안 마이크로커널 (2026.03 ~ 진행 중)
- **Tech**: Rust, QEMU, Multiboot2, x86_64, Docker
- **Features**:
  - **Capability-based Access Control**: 위조 불가 토큰 기반 자원 접근 제어, Hash-DRBG-SHA256(RDSEED/RDRAND 시드) 적용.
  - **동기 IPC (Rendezvous Model)**: 메시지 패싱 기반 프로세스 간 통신, `EP_CRYPTO` / `EP_SIGN` / `EP_SYSTEM` 엔드포인트 등록.
  - **메모리 격리**: `unsafe` 최소화, `alloc` 미사용 정적 할당만 사용, 4단계 페이지 테이블, KASLR, W^X 정책, Higher-Half 분리, `CR0.WP` + `CR4.SMEP/SMAP/UMIP` 보안 비트.
  - **Ring 3 사용자 공간**: 정적 ELF64 로더, `syscall/sysret` ABI, per-CPU `swapgs` + SMAP `stac/clac` 사용자 메모리 검증.
  - **커널 내장 보안 서비스**: AES-256-GCM, ChaCha20-Poly1305, BLAKE3, SHA-2/3, HKDF, Ed25519/Ed448, X448 DH, ML-DSA-44 청크 프로토콜.
  - **TLS 1.3 PSK 핸드셰이크**: Closed/External 프로필, `psk_pq_hybrid_ke` (X25519 + ML-KEM-768) 양자 내성 하이브리드 키 교환.
  - **HSM 추상화 + Soft Keystore 폴백**: `HsmDriver` 트레이트 기반으로 HSM 환경과 정적 풀 PSK Soft Keystore 양쪽에서 동일 코드 경로 재사용, `Provisioned` → `Wiped` 단방향 lifecycle.
  - **스택 보호**: IST 및 부트 스택 가드 페이지 캐너리, EAL4+ 안전 패닉 핸들러(정보 유출 없는 즉각 halt).

### [elib-k0-nt](https://github.com/Quant-Off/elib-k0-nt) | `Lead Developer`

> ISO-LIGHT-K0 를 위한 `no_std` 기반 폐쇄·방어적 암호 프리미티브 모듈 (2026.03 ~ 진행 중)
- **Tech**: Rust, `no_std`
- **Features**:
  - **독립 구현 원칙**: 각 암호 알고리즘 크레이트가 공유 코어 의존성 없이 독립적으로 구현되어 데이터 흐름이 외부로 누설되지 않도록 설계.
  - **해시**: SHA-2, SHA-3, SHAKE([FIPS 202](https://csrc.nist.gov/pubs/fips/202/final)), BLAKE2 자체 구현.
  - **난수**: NIST SP 800-90Ar1 기반 Hash DRBG.
  - **전자 서명**: Ed25519, Ed448 (컨텍스트 서명 포함).
  - **키 합의 (KEX)**: X25519, X448.
  - **AEAD/블록 암호**: AES, ChaCha20-Poly1305.
  - **양자 내성 암호 (PQC)**: ML-KEM, ML-DSA.
  - **부채널 방어**: 자체 구현 `constant-time` 연산 모듈 및 다중 아키텍처 대응 `zeroize` 휘발성 소거 로직.

### [Lumen](https://github.com/Quant-Off/lumen) | `Lead Developer`

> 제로 트러스트 환경을 위한 검증 가능한 폐쇄 친화적 AI 에이전트 프레임워크 (2026.04 ~ 진행 중)
- **Tech**: Rust, `wasmtime`, `candle`, `ezkl` / `halo2`, BLAKE3, Ed25519
- **Features**:
  - **하이브리드 zkML 파이프라인**: 비용이 큰 LLM 추론은 TEE 내부에 두고, 도구 라우팅 결정 및 출력 필터링에만 ZKP 를 생성하는 선택적 증명 전략. `Verification::ZkVerified` 와 `Verification::CommitmentOnly` 가 타입 시스템 차원에서 분리.
  - **권한 분리형 Host-WASM 샌드박스**: 호스트(TEE)는 LLM 추론, 정책 엔진, Capability 발급/검증을 담당하고 WASM 샌드박스는 에이전트 로직, 도구 호출 라우팅, 출력 필터링만 담당. Attested 보안 채널로만 통신.
  - **Capability 토큰 정책 엔진**: 서명, 만료, audience, nonce 4단 검증, 리플레이 방지 nonce LRU 테이블.
  - **Attested SecureChannel**: Ed25519 mutual handshake + AES-GCM-256 + X25519 ephemeral KEX, signed framing, $(\text{epoch}, \text{seq})$ 시퀀스로 리플레이 거부.
  - **결정론적 제어 모듈**: 정수 fixed-point(Q16.16, Q8.24) + BLAKE3 + BTreeMap + wasmtime SIMD off 조합으로 ZKP 재현성 보장.
  - **고속 방어 및 Provenance**: lexicon/regex/heuristic 기반 jailbreak 방어 엔진, BLAKE3 + Ed25519 provenance 검증, CycloneDX SBOM 자동 생성, 모델 핀 자동 회전(`PinSet`).

### Lumiere | `Lead Developer`

> 중간 규모 코드베이스 보안 취약점 분석-추론-해결 AI 에이전트 (2026.03 ~ 진행 중)
- **Tech**: Rust, Python, PostgreSQL, MySQL
- **Features**:
  - **V2P (Vulnerable-to-Patch) 코어 데이터셋 통합/정제**: 각종 데이터셋 통합·정제, NVD API 기반 `severity` 및 `diff` 정규화, `lang` 표준화 등 약 수백 만 행 규모의 `lumiere-v2p-dset` 구축.
  - **패치 제안 및 추론 데이터셋, 연쇄 사고(Chain-of-Thought) 데이터셋 구축**: Fine-Tuning + SFT + Multi-Turn 전략 적용을 위한 다단계 데이터셋 설계.
  - **Agentic Harness**: 최대 ~5만 줄 규모 코드베이스 분석, 잔존 보안 취약점 추론, 패치 제안, 더 나은 설계 제안 능력 제공.
  - **확장 시나리오**: 웹/애플리케이션 리버스 엔지니어링, 네트워크 패킷·이상 트래픽 감시 등 '수호자' 역할 수행.

### [EntanglementLib (Java)](https://github.com/Quant-Off/entanglementlib) | `Lead Developer`

> 금융 및 대규모 엔터프라이즈 적용을 위한 고보안 얽힘 라이브러리 (2025.12 ~ 2026.04, 정식 릴리스 전 단계)
- **Tech**: Java 25, Gradle 9.2.0 (Kotlin DSL), Project Panama (Foreign Function & Memory API)
- **Features**:
    - 얽힘 라이브러리 엔지니어링, 금융 및 대규모 엔터프라이즈 적용을 위한 높은 수준의 보안 등급 설계, Project Panama 기술을 적용하여 Rust 네이티브를 Foreign Function & Memory API 로 효율적으로 연결.
    - 엄격한 Zero-Trust 원칙 구현, Java 측 데이터 할당(Java-Owned, JO), Rust 측 데이터 할당(Rust-Owned, RO) 패턴을 기술적으로 분석하여 외부 의존성 없이 안전한 Off-Heap 메모리 상호 작용 설계.
    - FIPS 140-3 에 의거한 단일 병목점 통과 기술 적용 및 Rust 측 보안 연산 수행 후 민감 데이터에 대한 물리적 소거(Zeroization) 구현.

### [entlib-native (Rust)](https://github.com/Quant-Off/entlib-native) | `Lead Developer`

> EntanglementLib 과의 무결성 통신을 보장하는 네이티브 암호화 모듈 (2026.01 ~ 2026.04)
- **Tech**: Rust, FFI (Foreign Function Interface)
- **Features**:
    - 얽힘 라이브러리(Java) 와의 안전한 통신을 위해 Foreign Function Interface(FFI) 경계 통신 구축, JO, RO 각 패턴에서 사용 가능한 민감 데이터 래핑 구조체 설계.
    - Base64, Hex 인/디코딩, HKDF, HMAC, SHA-2, 3, SHAKE 알고리즘, NIST SP 800-90Ar1 에 따른 Hash DRBG 구현.
    - 안정적인 CC EAL4 구현, EAL5+ 확장을 위한 아키텍처 명세 작성.

## Tech Stack & Arsenal

<div align="center">


|                                               Languages                                                |                                               Tools & Ecosystems                                                |                                                     DevOps & Infra                                                     |                                                    OS & Arch                                                     |
|:------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------:|
| ![Java](https://img.shields.io/badge/Java_25-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)  |   ![Gradle](https://img.shields.io/badge/Gradle_9.2.0-02303A?style=for-the-badge&logo=gradle&logoColor=white)   |  ![AWS](https://img.shields.io/badge/amazon_Web_services-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)   |      ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)       |
| ![Rust](https://img.shields.io/badge/Rust_1.93.1-000000?style=for-the-badge&logo=rust&logoColor=white) |    ![Cargo](https://img.shields.io/badge/Cargo_1.93.1-000000?style=for-the-badge&logo=rust&logoColor=white)     |   ![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)    | ![Arch Linux](https://img.shields.io/badge/arch_linux-1793D1?style=for-the-badge&logo=archlinux&logoColor=white) |
|    ![Go](https://img.shields.io/badge/Go_1.26.1-00ADD8?style=for-the-badge&logo=go&logoColor=white)    | ![Postgres](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white) | ![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white) |        ![macos](https://img.shields.io/badge/macos-000000?style=for-the-badge&logo=macos&logoColor=white)        |
|                                                                                                        |          ![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)           |              ![CI/CD](https://img.shields.io/badge/CI%2FCD-Security_Scanning-4D4D4D?style=for-the-badge)               |                                                                                                                  |

</div>

## Philosophy

**최고의 보안은 편의성과 타협하지 않습니다.**  
저는 시스템 개발의 모든 단계에서 **최고 수준의 보안**과 **안정성 및 성능(Stability & Performance)** 을 최우선 가치로 삼습니다. 방어적 프로그래밍을 바탕으로, 더 빠르고 효율적인 데이터 흐름을 만들어내기 위해 끊임없이 코드를 검토하지만 단순한 편의를 위한 코드는 작성하지 않습니다. 불편함은 더 강한 보안을 위한 대가입니다.

**어떤 데이터든 완벽하게 보호되어야 합니다.**  
이는 제가 보안 엔지니어링의 길을 선택한 이유입니다. 개인은 결코 완전히 독립적일 수 없다는 점을 전제로 시스템 관점에서 수집되는 모든 정보의 출처를 신뢰하지 않으며, 독립적으로 운용 가능한 구조를 설계해야 하고자 합니다.

목표인 '군사 및 국가기관급 보안'을 달성하기 위해 저의 모든 기술 설계에 *'신뢰를 버리고(Zero-Trust), 고립을 선택하라(Air-Gapped)'* 라는 원칙을 심었습니다.  
이러한 철학은 아키텍처 설계부터 구현에 이르기까지 모든 과정의 기준이 됩니다.
매일 부족함을 인식하고 복잡한 추상적 개념을 누구나 이해할 수 있는 견고한 코드를 구현하기 위해 끊임없이 고민해야 합니다.

---

<div align="center">
  <i>Let's build an uncompromised future.</i><br>
  <i>Contact: <a href="mailto:qtfelix@qu4nt.space">qtfelix@qu4nt.space</a></i><br>
  <i><a href="https://qu4nt.space/docs/getting-started/onboarding">Team Quant Onboarding Guide</a></i>
</div>