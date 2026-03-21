<div align="center">

# Quant Theodore Felix

**Redefining the Paradigm of Security in the Quantum Era**

[![Korean Badge](https://img.shields.io/badge/Read_in-Korean-blue?style=for-the-badge&logo=googletranslate&logoColor=white)](https://github.com/Quant-TheodoreFelix)
[![Quant Github](https://img.shields.io/badge/Quant_Off-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Quant-Off/)
[![Quant Front](https://img.shields.io/badge/Site-Quant_Off-FFFFFF?style=for-the-badge)](https://qu4nt.space/)

</div>

---

*“Abandon trust. Choose isolation.”*

I am a lead developer at **Team Quant**, redefining the paradigm of security in response to the advancements in information and communication technology and the rise of quantum computing. I focus on building future-oriented security solutions through high-security infrastructure, compliance, Post-Quantum Cryptography (PQC), and the secure implementation of classical cryptographic algorithms.

[![GitHub Streak](https://streak-stats.demolab.com?user=Quant-TheodoreFelix&theme=github-dark-blue&hide_border=true&locale=en&mode=weekly&card_width=1024)](https://streak-stats.demolab.com/demo/?user=Quant-TheodoreFelix&theme=github-dark-blue&hide_border=true&border_radius=4.5&locale=en&short_numbers=false&date_format=&mode=weekly&exclude_days=&sections=total%2Ccurrent%2Clongest&card_width=1024&card_height=195&type=svg&background-type=solid&properties=background)

## Core Competencies

- **Compliance & Architecture**
    - Capable of designing architectures that meet certification and compliance requirements up to NIST FIPS 140-2/3 L2~4 and Common Criteria (CC) EAL5+.
- **Security Engineering**
    - Possess a deep understanding of Java JCA/JCE functionalities. Also capable of developing software with memory safety and extreme security using Rust natively.
- **Quantum Information Science & Technology Research**
    - Have a solid foundation in quantum information science theory, thanks to rapid learning abilities and a curiosity honed from a young age. I am confident in calling this wisdom acquired in just six months.

## Key Projects

### [EntanglementLib (Java)](https://github.com/Quant-Off/entanglementlib) | `Lead Developer`

> High-security entanglement library for financial, large-scale enterprise, and military-grade applications (Dec 2025 ~ Present)
- **Tech**: Java 25, Gradle 9.2.0 (Kotlin DSL), Project Panama (Foreign Function & Memory API)
- **Features**:
    - Engineered the Entanglement Library, designed for security ratings of EAL2 and above for financial and large-scale enterprise applications, and efficiently connected Rust native code using Project Panama's Foreign Function & Memory API.
    - Implemented strict Zero-Trust principles, technically analyzed Java-Owned (JO) and Rust-Owned (RO) data allocation patterns to design secure Off-Heap memory interactions without external dependencies.
    - Applied single bottleneck pass-through technology based on FIPS 140-3 and implemented physical erasure (Zeroization) of sensitive data after performing security operations on the Rust side.

###  [entlib-native (Rust)](https://github.com/Quant-Off/entlib-native) | `Lead Developer`

> Native cryptographic module ensuring integrity communication with EntanglementLib (Jan 2026 ~ Present)
- **Tech**: Rust, FFI (Foreign Function Interface)
- **Features**:
    - Built a Foreign Function Interface (FFI) boundary for secure communication with EntanglementLib (Java), and designed sensitive data wrapping structures usable in both JO and RO patterns.
    - Implemented Base64, Hex en/decoding, HKDF, HMAC, SHA-2, 3, SHAKE algorithms, and a Hash DRBG according to NIST SP 800-90Ar1.
    - Implemented a stable CC EAL4 and wrote architectural specifications for EAL5+ extension.

<br>

## Tech Stack & Arsenal

<div align="center">


|                                               Languages                                                |                                               Tools & Ecosystems                                                |                                                     DevOps & Infra                                                     |                                                    OS & Arch                                                     |
|:------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------:|
| ![Java](https://img.shields.io/badge/Java_25-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)  |   ![Gradle](https://img.shields.io/badge/Gradle_9.2.0-02303A?style=for-the-badge&logo=gradle&logoColor=white)   |  ![AWS](https://img.shields.io/badge/amazon_Web_services-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)   |      ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)       |
| ![Rust](https://img.shields.io/badge/Rust_1.93.1-000000?style=for-the-badge&logo=rust&logoColor=white) |    ![Cargo](https://img.shields.io/badge/Cargo_1.93.1-000000?style=for-the-badge&logo=rust&logoColor=white)     |   ![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)    | ![Arch Linux](https://img.shields.io/badge/arch_linux-1793D1?style=for-the-badge&logo=archlinux&logoColor=white) |
|    ![Go](https://img.shields.io/badge/Go_1.26.1-00ADD8?style=for-the-badge&logo=go&logoColor=white)    | ![Postgres](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white) | ![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white) |        ![macos](https://img.shields.io/badge/macos-000000?style=for-the-badge&logo=macos&logoColor=white)        |
|                                                                                                        |          ![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)           |              ![CI/CD](https://img.shields.io/badge/CI%2FCD-Security_Scanning-4D4D4D?style=for-the-badge)               |                                                                                                                  |

</div>

<br>

## Philosophy

**The highest level of security does not compromise with convenience.**
I prioritize **top-tier security** and **stability & performance** at every stage of system development. Based on defensive programming, I continuously review code to create faster and more efficient data flows, but I never write code solely for convenience. Discomfort is the price paid for stronger security.

**All data must be protected without exception.**
This is why I chose the path of security engineering. Recognizing that individuals can never be completely independent, I do not trust the origin of any information collected from a system perspective, and I strive to design architectures that can operate independently.

To achieve my goal of **military- and government-grade security**, I embed the principle of *“Abandon trust (Zero-Trust), Choose isolation (Air-Gapped)”* into all of my technical designs.
This philosophy serves as the foundation for every stage, from architecture design to implementation.
I acknowledge my limitations every day and continuously work to transform complex abstract concepts into robust code that anyone can understand.

---

<div align="center">
  <i>Let's build an uncompromised future.</i><br>
  <i>Contact: <a href="mailto:qtfelix@qu4nt.space">qtfelix@qu4nt.space</a></i><br>
  <i><a href="https://qu4nt.space/docs/getting-started/onboarding">Team Quant Onboarding Guide</a></i>
</div>