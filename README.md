# Landing Page Design Skill

AI가 만든 랜딩 페이지가 "AI 티" 없이, 실제 디자이너가 설계한 것처럼 나오게 하는 **규칙 문서(스킬)** 와 그 규칙으로 만든 **데모**를 모아둔 저장소입니다.

## 📄 핵심 파일

| 파일 | 설명 |
|---|---|
| [`landing-design.md`](./landing-design.md) | **메인 스킬** — 랜딩 전용 디자인 규칙 (타이포·컬러·여백·레이아웃·컴포지션·행간·줄바꿈까지 고정값으로 명시) |
| [`index.html`](./index.html) · [`demo/flowtime.html`](./demo/flowtime.html) | 이 스킬만으로 만든 데모 랜딩 **"Flowtime"** (가상 집중 타이머 서비스) |

## 📚 docs

| 파일 | 설명 |
|---|---|
| [`docs/human-like-web-design-skill.md`](./docs/human-like-web-design-skill.md) | 최초 범용 규칙 원본 |
| [`docs/human-like-web-design-skill-public.md`](./docs/human-like-web-design-skill-public.md) | 공유용(외부 레퍼런스 명칭 제거) 버전 |
| [`docs/ondo-workflow.md`](./docs/ondo-workflow.md) | 카페 랜딩 "ONDO" 제작 과정 상세 워크플로우 (이미지 삽입 타임라인 포함) |
| [`docs/ondo-conversation-log.md`](./docs/ondo-conversation-log.md) | 전체 작업 대화 로그 정리본 |

## 스킬 요약

- **타이포**: 폰트 2개 이하, 세리프 없음, 14px↑, 정해진 스케일(t4~t14)
- **행간(고정값)**: 제목 1.25 / Heading 1.35 / 서브 1.45 / 본문 1.6 / 캡션 1.4 (임의값 금지)
- **한국어**: `word-break: keep-all`(음절 쪼개짐 방지), 제목 1.2↓ 금지
- **컬러**: Primary는 S55–85 / L40–58, 톤은 Hue로. Neutral은 거의 무채색(Primary 쪽으로 살짝만)
- **대비**: 본문 4.5:1 / 버튼·큰 글자 3:1
- **서피스**: Border·Shadow 지양, 명도차로 구분
- **Radius**: 8–20px / **Padding**: 4·8·16·24
- **레이아웃**: 콘텐츠 최대폭 + 섹션 세로 여백 크게(80~120px) + 모바일 1열
- **컴포지션**: 히어로→가치→증거→CTA(1개·반복), 3초 스캔
- **이미지**: 상업용 사용권 확인 필수

> 데모·규칙 모두 데모용 가상 서비스를 기준으로 작성되었습니다.
