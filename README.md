# 저는 Quant Theodore Felix 입니다

> [English README](https://github.com/Quant-TheodoreFelix/Quant-TheodoreFelix/blob/main/README_EN.md)

저는 정보통신 기술의 진보와 양자 컴퓨팅의 부상에 대응하여 [보안의 패러다임을 재정의하고 있는 팀 **퀀트(Quant)** 에 소속](https://qu4nt.space/)되어 있습니다. 

고보안 인프라, 컴플라이언스, 양자-내성 암호(Post-Quantum Cryptography, PQC), 고전 암호 알고리즘 구현 등의 활동으로 미래 지향적인 보안 솔루션을 구축하는 데 주력하고 있습니다.

## 전문 분야 및 핵심 역량

* **컴플라이언스 및 아키텍처**: NIST FIPS 140-2/3 L2~4, CC(Common Criteria) EAL5+ 까지 인증 및 규정 준수 사항을 만족하는 아키텍처 설계가 가능합니다.
* **보안 엔지니어링**: Java JCA/JCE 기능에 대해 높은 이해도를 가집니다. 또한 Rust 언어를 네이티브로 사용하여 메모리 안정성 및 극도의 보안성을 가진 소프트웨어를 개발할 수도 있습니다.
* **양자정보과학기술 연구**: 빠른 습득력과 어릴 때부터 연마한 호기심을 통해 양자정보과학 이론의 기초가 단단합니다. 이는 단 6개월만에 습득한 지혜라고 자부할 수 있습니다.

## 진행 중인 주요 프로젝트

> [얽힘 라이브러리(EntanglementLib, Java)](https://github.com/Quant-Off/entanglementlib) - Team Quant (2025.12 ~ 진행 중) : **리드 개발자**
- 얽힘 라이브러리 엔지니어링, 금융 및 대규모 엔터프라이즈 적용을 위한 EAL2 이상의 보안 등급 설계, Project Panama 기술을 적용하여 Rust 네이티브를 Foreign Function & Memory API로 효율적으로 연결.
- 엄격한 Zero-Trust 원칙 구현, Java측 데이터 할당(Java-Owned, JO), Rust측 데이터 할당(Rust-Owned, RO) 패턴을 기술적으로 분석하여 외부 의존성 없이 안전한 Off-Heap 메모리 상호 작용 설계.
- FIPS 140-3에 의거한 단일 병목점 통과 기술 적용 및 Rust 측 보안 연산 수행 후 민감 데이터에 대한 물리적 소거(Zeroization) 구현.

> [entlib-native(Rust)](https://github.com/Quant-Off/entlib-native) - Team Quant (2026.1 ~ 진행 중) : **리드 개발자**
- 얽힘 라이브러리(Java) 와의 안전한 통신을 위해 Foreign Function Interface(FFI) 경계 통신 구축, JO, RO 각 패턴에서 사용 가능한 민감 데이터 래핑 구조체 설계.
- Base64, Hex 인/디코딩, HKDF, HMAC, SHA-2, 3, SHAKE 알고리즘, NIST SP 800-90Ar1에 따른 Hash DRBG 구현
- 안정적인 CC EAL4 구현, EAL5+ 확장을 위한 아키텍처 명세 작성.

## 기술 스택

저는 기본적으로 Java 및 Rust 언어를 다룹니다.

| 구분                     | 상세 내용                                                                                         |
|------------------------|-----------------------------------------------------------------------------------------------|
| **Languages**          | Java, Rust                                                                                    |
| **Tools & Ecosystems** | Gradle (Kotlin DSL), Cargo, Project Panama, Criterion, Valgrind, Git, CI/CD(보안 스캐닝), Postgres |
| **DevOps**             | AWS, Cloudflare                                                                               |

여유가 생긴다면 Go 언어를 사용해보고 싶습니다.

## 기술 철학

저는 시스템 개발의 모든 단계에서 **최고 수준의 보안 능력**과 **안정성 및 성능**(stability & performance)을 최우선으로 가치 판단을 내립니다. 어떠한 경우에도 '편의성'보단 '안정성'을 우선시합니다. 이러한 특성은 방어적 프로그래밍과 유사하지만, 성능 면에서도 좀 더 빠르고 효율적인 흐름을 가진 기술을 설계하기 위해 작성한 코드를 끊임없이 검토합니다.

'군사 및 국가기관급 보안' 이라는 목표를 가지고 있습니다. 이 목표는 저의 모든 기술 설계에 '아무것도 믿지 말고(Zero-Trust), 독립되어라(Air-Gapped)' 라는 원칙을 자연스레 심어주었습니다. 저는 자신이 지키고자 하는 정보가 어느 누구로부터든 안전하게 지켜졌으면 하는 바램에서 보안 엔지니어링 길을 선택했고, '자신'이라 함은 독립적이지 않을 수 있다는 것을 명확히 하기 때문에 시스템 관점에서 얻을 수 있는 모든 정보의 출처를 믿지 않기로 결정했습니다.

이런 철학으로 볼 때, 대단하다는 말을 자주 들었지만 스스로 부족한 점을 매일 깨닫습니다. 생각하는 것을 그려내고 모두에게 전달할 수 있도록 매 시간 생각을 멈추지 않으려 노력합니다.