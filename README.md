# Causal Loom

A modular causal narrative simulation prompt.

모듈형 인과 시뮬레이션을 위한 경량 프롬프트입니다. 장기 상호작용에서 인과관계, 상태 연속성, 제한 시점, 자율 세계 진행, 자연스러운 한국어 서술을 유지하면서도 실행 프롬프트의 중복 설명을 줄이는 것을 목표로 합니다.

현재 배포 파일:

- `prompt/Causal-Loom.md` - 실행 프롬프트
- `THIRD_PARTY_NOTICES.md` — 원본 및 참고 프로젝트 출처/라이선스 고지
- `LICENSE` — 이 저장소의 배포 라이선스(Apache License 2.0)
- `LICENSES/Apache-2.0-Singulari-Tea.txt` — Singulari-Tea Codex에 적용되는 Apache-2.0 사본
- `LICENSES/MIT-im-not-ai.txt` — im-not-ai의 MIT 라이선스 사본

## 주요 설계

- **Causal resolution before prose** — 사건과 상태를 먼저 확정하고 서술은 확정된 장면만 표현합니다.
- **Layer ownership** — ACT / STA / WRL / SCN / NAR / OUT 계층의 책임 경계를 유지합니다.
- **Limited viewpoint** — 주인공이 접근할 수 없는 정보는 서술·선택지·발견 정보로 누출하지 않습니다.
- **Persistent state** — 신체, 일반 상태, 관계, 목표, 활성 상황, 시간축을 분리해 연속성을 유지합니다.
- **Autonomous world** — 현재 원인이 있는 NPC 행동, 진행 중인 과정, 환경 변화만 독립적으로 진행합니다.
- **Korean narrative pass** — 자연스러운 한국어 실현 후, 실제로 두드러지는 반복 패턴만 국소적으로 보정합니다.
- **Player-safe save** — 일반 세이브에는 사용자에게 공개된 확립 상태만 저장하며 숨은 세계 연속성은 직렬화하지 않습니다.

## 사용

`prompt/Causal-Loom.md`의 전체 내용을 사용 중인 LLM 환경의 system prompt, custom instruction, preset 또는 이에 준하는 상위 프롬프트 영역에 넣습니다.

프롬프트 안의 `{{USER_INITIAL_PREMISE_VERBATIM}}`는 템플릿 환경에서 초기 premise를 주입하기 위한 자리표시자입니다. 템플릿 치환 기능이 없다면 사용하는 환경에 맞게 초기 premise 전달 방식을 조정하세요.

모델마다 instruction-following, context handling, 출력 길이 및 시스템 프롬프트 우선순위가 다르므로 동일한 동작을 보장하지는 않습니다.

## Attribution / Upstream

이 프로젝트는 다음 프로젝트를 기반 또는 참고하여 대폭 수정·재구성되었습니다.

### Singulari-Tea Codex Prompt for Gemini

Original project: https://github.com/lemos999/Singulari-Tea-Codex-Prompt-for-Gemini

Upstream repository owner / maintainer: `lemos999`

License: Apache License 2.0

이 저장소의 프롬프트는 Singulari-Tea Codex의 모듈형 서사 시뮬레이션 개념 및 프롬프트 자료를 출발점으로 삼았으며, 이후 실행 구조, 인과 판정, 상태 소유권, 관계 처리, 시간 연속성, 제한 시점, 장면 확정, 출력 처리, 세이브/로드 및 한국어 서술 구조를 광범위하게 수정·재구성했습니다.

### im-not-ai

Original project: https://github.com/epoko77-ai/im-not-ai

Copyright (c) 2026 epoko77-ai

License: MIT License

한국어 자연성 감사 부분은 `im-not-ai`의 한국어 AI 문체 taxonomy 및 post-editing 설계 원칙에서 아이디어를 참고·변형했습니다. 해당 MIT 저작권 및 허가 고지는 `LICENSES/MIT-im-not-ai.txt`에 보존합니다.

자세한 내용은 [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md)를 참조하세요.

## Maintainer

[@Catverdose](https://github.com/Catverdose)

## License

이 저장소는 Apache License 2.0으로 배포하도록 구성되어 있습니다. 자세한 조건은 [`LICENSE`](LICENSE)를 참조하세요.

제3자 자료에는 각 원본 라이선스가 계속 적용됩니다. 관련 고지는 `THIRD_PARTY_NOTICES.md` 및 `LICENSES/`에 보존되어 있습니다.

> 이 저장소의 라이선스 배치는 일반적인 오픈소스 배포 구조를 위한 것이며 법률 자문이 아닙니다.
