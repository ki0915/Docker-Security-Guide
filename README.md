# 🐳 Docker 컨테이너 보안 가이드

## 🏷 프로젝트 소개

OWASP Docker Top 10, CIS Docker Benchmark v1.8.0, NIST SP 800-190 기준을 위험도와 구현 비용 순으로 재구성한 컨테이너 보안 실무 레퍼런스입니다.

- **작성:** 2026, 단독 저술
- **문서:** [`보안_모범_사례_가이드_Docker.pdf`](./보안_모범_사례_가이드_Docker.pdf)

## ✅ 배경

실무에서 대응한 침해사고 2건이 모두 오래된 프레임워크·라이브러리 같은 의존성에서 시작되었다는 공통점을 확인한 뒤, 컨테이너 환경의 보안을 체계적으로 정리할 필요를 느꼈습니다. OWASP·CIS·NIST 세 기준을 각각 따로 참고하면 무엇부터 손대야 할지 판단하기 어려워, 위험도와 구현 비용 기준으로 우선순위를 재구성했습니다.

## 📋 다루는 내용

- **이미지 보안** — 최소 이미지, digest 고정, Trivy로 CI 빌드 단계에서 취약점 차단
- **최소권한 실행** — non-root, capability drop, rootless
- **시크릿 관리** — BuildKit secret으로 이미지 레이어에 자격증명이 남지 않도록 처리
- **네트워크 격리** — internal 네트워크로 컨테이너 간 lateral movement 차단
- **런타임 탐지** — cAdvisor, Falco로 실행 중 이상 행위 탐지

## 🔗 관련

- [침해사고 대응 사례 (Kiosk → wiki-backend 성장 궤적)](https://github.com/ki0915/wiki-backend)
