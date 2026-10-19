# Landing Page Design Skill

AI가 생성한 랜딩 페이지가 획일적이고 인공적인 느낌을 주지 않도록,
실제 제품 디자이너가 설계한 것처럼 자연스럽고 일관되며 "시선을 끄는" 랜딩을 생성한다.

> 이 문서는 **랜딩 페이지 전용**이다. 복잡한 디자인 시스템이나 수많은 컴포넌트가 아니라,
> 랜딩에 필요한 타이포·컬러·여백·레이아웃·구성만 집중해서 다룬다.

---

## 1. Typography

### Font Family

- 한 화면에서 사용하는 Font Family는 최대 2개로 제한한다.
- Korean: `Pretendard`를 기본 폰트로 사용한다.
- English: `Inter`를 기본 폰트로 사용한다.
- Korean fallback이 필요한 경우 고딕 계열 시스템 폰트를 사용한다.
- Serif / 명조 계열 폰트는 사용하지 않는다. (좋은 디스플레이 세리프를 직접 세팅할 수 없는 환경에서는 기본 시스템 명조로 떨어져 올드해지기 쉽기 때문)
- 별도의 장식용 폰트나 개성 강한 Display Font를 추가하지 않는다.

### Typography Scale

아래 타이포그래피 스케일을 기본 기준으로 사용한다.

| Token | Font Size | Line Height |
|------|-----------|-------------|
| t4 | 14px | 19px |
| t5 | 16px | 22px |
| t6 | 18px | 24px |
| t7 | 20px | 27px |
| t8 | 22px | 30px |
| t9 | 24px | 32px |
| t10 | 26px | 35px |
| t11 | 28px | 38px |
| t12 | 32px | 42px |
| t13 | 40px | 52px |
| t14 | 48px | 60px |

- 14px 미만의 텍스트는 사용하지 않는다.
- 본문 텍스트는 최소 14px을 사용한다.
- Header navigation 및 menu text도 최소 14px을 사용한다.
- 과도하게 큰 제목을 사용하지 않는다.
- 화면의 콘텐츠 양과 목적에 비해 지나치게 큰 Display Typography를 사용하지 않는다.
- 대형 제목은 실제로 큰 시각적 위계가 필요한 경우(예: 히어로 메시지)에만 제한적으로 사용한다.

### Font Weight

- Regular: `400`
- Medium: `500`
- Bold: `700`
- 불필요하게 다양한 Font Weight를 사용하지 않는다.

### Line Height (행간) — 역할별 고정값

행간은 **역할별로 아래 고정값만 사용한다.** 임의로 더 조이거나 늘리지 않는다. (범위가 아니라 딱 이 값)

| 역할 | 크기 | line-height |
|---|---|---|
| 대형 제목 (Display) | 28px↑ | **1.25** |
| 제목 (Heading) | 20–26px | **1.35** |
| 서브헤드 / 리드 (짧은 1~3줄) | 16–20px | **1.45** |
| 본문 (여러 줄 문단) | 14–16px | **1.6** |
| 캡션 / 라벨 | 14px | **1.4** |

- **우선순위:** Typography Scale 표의 토큰 크기를 그대로 쓰면 **표의 line-height가 1순위**다. 반응형(`clamp()` 등)으로 토큰 밖 크기를 쓸 땐 **위 고정값**을 쓴다.
- 반응형으로 크기가 변해도 **같은 고정값을 유지**한다. 크기가 애매하면 **더 큰 역할 쪽** 값을 쓴다.
- **스케일/위 표 값을 무시하고 즉흥값(`1.0~1.1` 등)으로 조이지 않는다.** (큰 제목이 답답해지는 주원인)
- **한국어 최소선:** 어떤 제목도 `1.2` 밑으로 내리지 않는다. (위 고정값은 모두 이를 충족)
- **짧은 서브 설명(2~3줄)에 본문 행간(1.6)을 그대로 쓰지 않는다** → 서브헤드 값(1.45)을 쓴다. (안 그러면 줄 사이가 떠 보임)
- 전역(body)에 본문 행간을 걸었다면, 제목·서브헤드는 **각자 위 고정값으로 반드시 덮어쓴다.**

### Letter Spacing

- AI가 자주 생성하는 지나치게 타이트한 Letter Spacing을 피한다.
- 대형 제목은 살짝 좁혀도 좋다(`-0.01 ~ -0.02em`). 본문은 기본(0)을 유지한다.
- 대문자 라벨(eyebrow 등)은 약간 넓힌다(`+0.06 ~ +0.1em`).
- 구체 값은 실제 결과를 확인하며 조정한다.

### Korean Line Break (한국어 줄바꿈)

- 한국어 텍스트에는 `word-break: keep-all`을 적용해 **음절 단위로 쪼개지지 않게** 한다. (예: "한눈에"가 "한 / 눈에"로 끊기는 것 방지 → **어절(단어) 단위로만** 줄바꿈)
- 아주 긴 영문·URL 등이 영역을 넘칠 수 있으니 `overflow-wrap: break-word`를 함께 둔다.
- 제목은 `text-wrap: balance`로 줄 길이를 고르게 맞춘다.
- 반드시 붙어 있어야 하는 짧은 구(숫자+단위, 브랜드명 등)는 `white-space: nowrap` 또는 `&nbsp;`로 줄바꿈을 막는다.
- 기본 적용 예: `body { word-break: keep-all; overflow-wrap: break-word; }`

### Content

- 메뉴 항목·섹션마다 의미 없는 설명 문구를 추가하지 않는다.
- 실제 기능이나 콘텐츠와 관련 없는 placeholder 문구를 생성하지 않는다.
- 장식적인 텍스트를 불필요하게 추가하지 않는다.
- 모든 텍스트는 실제 사용자에게 전달할 정보나 인터페이스의 기능적 목적을 가져야 한다.

---

## 2. Color

### Color Direction

Primary Color는 트렌디하면서도 장시간 사용해도 눈에 부담이 적은 색상을 사용한다.

- 명도와 채도가 지나치게 낮아 탁하고 칙칙해 보이는 색상을 피한다.
- 반대로 지나치게 높은 채도와 명도로 인해 형광색처럼 자극적인 색상도 피한다.
- 브랜드의 개성이 느껴지면서도 편안한 색감을 우선한다.
- 전체 UI가 무채색처럼 보이지 않도록 Primary Color를 적절하게 사용한다.

### Primary Color Range

Primary Color를 선택할 때 다음 HSL 범위를 권장한다.

- Saturation: `55–85%`
- Lightness: `40–58%`
- 권장 중심 범위: `S 65–75% / L 45–52%`
- 브랜드 톤(웜/쿨)은 **Hue로 표현한다.** 따뜻한 브랜드면 브라운·앰버 계열 Hue를, 차가운 브랜드면 블루·틸 계열 Hue를 쓰되, **S/L 규율은 동일하게 지킨다.** (톤을 바꾸려고 규칙을 깨지 않는다)

#### Avoid

- Saturation `< 45%` — 지나치게 Muted되어 탁하고 생기 없는 인상을 줄 수 있다.
- Saturation `> 90%` — 지나치게 강하고 자극적인 색으로 보일 수 있다.
- Lightness `< 35%` — Primary Color가 지나치게 어둡고 무거워질 수 있다.
- Lightness `> 65%` — 색이 지나치게 흐려지고 존재감이 약해질 수 있다.

### Visual Check

수치 범위에 포함되더라도 다음 조건을 만족하지 않으면 사용하지 않는다.

- 회색이 섞인 듯 탁해 보이지 않아야 한다.
- 형광색처럼 지나치게 강하게 튀지 않아야 한다.
- 밝은 배경에서 충분한 시각적 존재감이 있어야 한다.
- 장시간 바라보아도 지나치게 자극적이지 않아야 한다.
- Primary Color 하나만으로 화면이 과도하게 화려해지지 않아야 한다.

### Color Palette

Palette는 다음 구조로 단계별로 관리한다.

- Neutral: 배경, Surface, 텍스트, 보조 UI
- Primary: 서비스의 핵심 브랜드 컬러
- Blue: 정보 및 보조 강조
- Green: 성공 및 긍정 상태
- Yellow: 주의 및 경고 상태
- Red: 오류 및 위험 상태
- Purple: 보조적인 강조 및 특수 상태

각 컬러는 밝은 단계부터 어두운 단계까지 여러 단계로 구성한다.

### Color Token Naming

팔레트 구조는 따르되, 특정 디자인 시스템의 이름을 그대로 복제하지 않는다. 짧고 직관적인 자체 명칭을 사용한다.

예: `neutral-100` `neutral-200` `neutral-500` `neutral-900` `primary-100` `primary-500` `primary-700` `success-500` `warning-500` `danger-500` `info-500`

### Neutral Color

- Neutral Palette는 **거의 무채색**을 기본으로 한다.
- 단, **Primary의 Hue 방향으로 아주 살짝만** 치우칠 수 있다. (웜 브랜드 → 미세한 웜 그레이, 쿨 브랜드 → 쿨 그레이) — Primary와 Neutral의 온도를 맞춰 따로 놀지 않게 한다.
- 치우침은 **채도를 최소한으로** 한다. Beige·Brown처럼 색이 또렷하게 보이는 Gray는 기본 Neutral로 사용하지 않는다.
- Pure Black `#000000`은 사용하지 않는다.
- 가장 어두운 Neutral은 `#1A1C20`(쿨 기준) 수준의 명도를 기준으로 하고, 그보다 어둡게 생성하지 않는다. 웜 브랜드면 **같은 명도의 웜 다크 뉴트럴**을 쓴다.
- 검은색이 필요한 경우에도 Pure Black 대신 Dark Neutral을 사용한다.

### Neutral Hierarchy

Neutral Color는 명확한 명도 단계를 만들어 정보의 위계를 구분한다.

- Primary Text: 가장 진한 Neutral
- Secondary Text: 한 단계 낮은 Neutral
- Tertiary Text: 보조 정보에 사용하는 낮은 명도의 Neutral
- Background: 가장 밝은 Neutral
- Surface: Background와 구분되는 밝기의 Neutral

### Contrast (대비 · 필수)

- 본문 텍스트와 배경의 명도 대비는 **최소 4.5:1**.
- 큰 텍스트(약 24px 이상)·버튼·아이콘 등은 **최소 3:1**.
- Primary 위에 올라가는 글자(버튼 텍스트 등)는 **반드시 대비를 확인**한다. Primary가 밝으면 어두운 글자, 어두우면 밝은 글자.
- 대비가 애매하면 **색을 바꾸기보다 글자색(흰/검 계열)을 바꿔** 맞춘다.
- 서로 인접한 영역은 충분한 명도 차이를 확보해 시각적 계층이 사라지지 않게 한다.

### Color Usage

- Primary Color를 모든 요소에 과도하게 적용하지 않는다.
- CTA, 선택 상태, 핵심 인터랙션 등 사용자의 시선이 필요한 영역에 우선적으로 사용한다.
- Primary와 Neutral의 비율을 조절하여 화면이 과하게 화려하거나 밋밋해지지 않도록 한다.
- 의미 없는 장식을 위해 추가적인 색상을 생성하지 않는다.
- 의미 없는 Gradient를 사용하지 않는다.

---

## 3. Surfaces & Cards

### Card Usage

- 모든 콘텐츠를 Card로 감싸지 않는다.
- 실제로 그룹화가 필요한 경우에만 Card를 사용한다.
- 단순히 영역을 구분하기 위해 Card를 반복적으로 사용하지 않는다.
- Card 안에 Card를 중첩하는 구조를 최대한 피한다. (`Card > Card > Card` 금지)
- 페이지 전체가 여러 개의 동일한 Card로 채워지는 구성을 피한다.
- 콘텐츠의 관계가 명확하다면 Card 대신 여백, Background, Typography로 그룹을 표현한다.

### Background & Surface

영역을 구분할 때 외곽선보다 Background와 Surface의 명도 차이를 우선적으로 사용한다.

- **Light**: 연한 Gray Background 위에 White Surface/Card. (`Gray Background → #FFFFFF Card`) Border·Shadow 없이 명도차로 구분.
- **Dark**: 진한 Background 위에 상대적으로 밝은 Surface. 충분한 명도 차이 확보.
- **Surface Hierarchy**: 비슷한 명도의 Surface를 여러 겹 중첩하지 않는다.

### Border

- Border는 기본적으로 사용하지 않는다.
- Card와 Background 구분에 Border를 우선 사용하지 않는다. 가능하면 명도 차이로 구분.
- 장식적인 Border, 한 화면에 반복되는 과한 외곽선을 피한다.

### Shadow

- Card에는 기본적으로 Shadow를 사용하지 않는다. (장식용 드롭섀도는 대표적인 "싸보임" 신호)
- Card를 띄워 보이게 하는 장식적 Shadow, 여러 단계의 Shadow를 사용하지 않는다.
- 특별한 인터랙션이나 명확한 Elevation이 필요할 때만 **아주 미세한 1단계**로 제한한다.

### Visual Hierarchy

영역의 계층은 다음 우선순위로 표현한다. 가능하면 앞 단계만으로 해결한다.

1. Layout & Spacing
2. Background / Surface
3. Typography
4. Border
5. Shadow

### Anti-AI Patterns

- Card 안에 Card (/ Card 안에 Card 안에 Card)
- 모든 Section을 Card로 감싸기
- 모든 요소에 Border 적용
- 모든 Card에 Shadow 적용
- 여러 단계의 Gray Surface 중첩
- Shadow + Border + Background를 동시에 써서 Card를 과도하게 강조

---

## 4. Border Radius

- 모든 Radius는 최소 `8px`, 최대 `20px` 범위에서 사용한다.
- `8px` 미만, `20px` 초과는 사용하지 않는다.
- `9999px` / 과도한 Pill 형태를 기본 UI에 사용하지 않는다. `rounded-full`은 원형 요소 등 특수한 경우만.
- 동일 화면·동일 역할의 컴포넌트는 동일 Radius로 통일한다. (예: Card가 16px이면 모든 Card 16px)
- 한 화면에서 `8/12/16/20px`을 무분별하게 혼합하지 않는다.
- 큰 컨테이너라고 무조건 큰 Radius를 적용하지 않는다. 장식 목적으로 Radius를 과도하게 키우지 않는다.
- 전체 UI가 지나치게 둥글고 장난스러워 보이지 않게 한다.

---

## 5. Spacing & Padding

### Component Padding

- 컴포넌트의 기본 Padding은 상하좌우 동일한 값을 사용한다. (특별한 레이아웃 이유 없으면 방향별로 다르게 두지 않는다)
- 제한된 Padding Scale만 사용한다: **Small 4px · Medium 8px · Large 16px · X-Large 24px**
- 컴포넌트 내부 **최대 Padding은 24px**을 넘지 않는다. `13/18/27px` 같은 비정형 값을 만들지 않는다.
- 동일 역할·크기의 컴포넌트는 동일 Padding을 유지한다.
- 작은 콘텐츠를 과도한 Padding으로 감싸지 않는다. 내부 여백보다 외부 간격이 필요하면 Layout의 Gap을 쓴다.

> **주의:** 위 "최대 24px"은 **컴포넌트 내부 여백** 규칙이다. **섹션 사이의 세로 여백은 이와 별개이며 훨씬 크게** 둔다 → `6. Layout & Responsive` 참고.

---

## 6. Layout & Responsive  *(랜딩 보강)*

### Header / Nav 정렬

- 상단 메뉴 탭을 **가운데 정렬**할 땐, 좌측(로고)·우측(버튼) 폭이 서로 달라도 메뉴가 **페이지 정중앙**에 오게 한다.
- `justify-content: space-between`(flex)은 좌우 폭 차이 때문에 가운데 메뉴가 **한쪽으로 쏠린다.** → **3분할 그리드**를 쓴다:
  - `grid-template-columns: 1fr auto 1fr` → 로고 `justify-self:start` / 메뉴 `center` / 액션 `end`
- 메뉴를 **왼쪽 정렬**로 둘 땐 flex(`space-between`)로 충분하다. (쏠림 문제는 "가운데 정렬"일 때만 생긴다)

### Content Width

- 본문 콘텐츠 최대폭은 약 `1080–1200px`로 제한하고 가운데 정렬한다.
- 읽는 텍스트 한 줄 폭은 약 `45–75자`를 넘지 않는다.
- 좌우 가장자리 여백(gutter): 모바일 `16–20px`, 데스크톱 `24–48px`.

### Section Rhythm (섹션 여백)

- 섹션 사이 **세로 여백은 크게** 둔다: 데스크톱 `80–120px`, 모바일 `48–72px`.
- 모든 섹션에 같은 세로 리듬을 적용해 일관성을 준다.
- 요소 그룹 사이 간격은 Padding보다 **Layout의 Gap**으로 만든다.
- 여백으로 "호흡"을 만든다. 랜딩은 꽉 채우는 것보다 **비우는 것**이 고급스러워 보인다.

### Responsive

- 모바일(약 `768px` 이하)에서는 다단 레이아웃을 **1열**로 내린다.
- 터치 대상(버튼 등)은 **최소 44px 높이**를 확보한다.
- 폰트·여백은 고정값 대신 범위값(`clamp()` 등)으로 화면 크기에 따라 부드럽게 변하게 한다.
- **가로 스크롤이 생기지 않게** 한다. (이미지·표 등은 자기 영역 안에서만 넘치게)

### Hero

- 히어로는 필요 시 화면 높이를 꽉 채울 수 있다(풀스크린). 배경 이미지/영상 위 텍스트는 **대비를 반드시 확보**한다(스크림/오버레이).
- 히어로 외 섹션은 콘텐츠 높이에 맞춘다. 억지로 화면을 꽉 채우지 않는다.

---

## 7. Landing Composition  *(랜딩 보강)*

### Page Structure

- 랜딩은 위→아래로 스캔된다. 기본 순서:
  **① 히어로(핵심 메시지 + CTA) → ② 가치/기능 → ③ 증거(후기·로고·숫자) → ④ 상세 → ⑤ 마지막 CTA → ⑥ 푸터**
- **한 섹션 = 한 메시지.** 한 화면에 너무 많은 걸 담지 않는다.
- 섹션마다 짧은 제목(필요하면 한 줄 설명)으로 위계를 준다.

### CTA

- 주요 CTA는 화면에서 **가장 눈에 띄는 1개**로 (Primary 색 채움). 보조 행동은 약한 버튼으로 둔다.
- CTA는 **히어로와 페이지 끝**에 반복 배치한다.
- 버튼 문구는 행동을 그대로 쓴다. (예: "메뉴 보기", "예약하기")

### Hierarchy & Scannability

- 중요도 순으로 크기·굵기·색을 준다. **모든 걸 강조하면 아무것도 강조되지 않는다.**
- 훑어만 봐도 **"뭐 하는 곳인지 + 뭘 누르면 되는지"가 3초 안에** 읽혀야 한다.
- 장식 대신 **여백·타이포 위계**로 흐름을 만든다.

### Imagery

- 이미지는 실제 콘텐츠와 관련된 것만 쓴다. 의미 없는 스톡/장식 이미지는 피한다.
- 같은 역할의 이미지(예: 카드 썸네일)는 **동일 비율**로 맞춘다 (`object-fit: cover`).
- **상업적으로 사용 가능한 이미지인지 반드시 확인**한다 — 직접 생성했거나 라이선스가 명확한 스톡만. "다운로드 된다"가 "상업용 OK"는 아니며, 출처 불명 이미지는 쓰지 않는다.

---

## 8. Device Mockup (서비스 소개 화면)  *(랜딩 보강)*

웹/앱 서비스를 소개할 땐 **기기 목업 안에 실제 화면(스크린샷)**을 넣는다.

### 조건 (필수)

- 목업 **안의 화면 이미지는 잘리거나 비는 부분이 없어야 한다.** (crop ✗, 빈 공간 ✗)
- 보장 원리: 넣는 스크린샷을 **목업 화면 영역과 같은 비율**로 준비한다. 비율이 다르면 `cover`=잘림 / `contain`=빈공간 중 **하나는 반드시** 생긴다.
- **가장 안전한 기본값:** 화면 영역을 `width:100%; height:auto`로 둬서 **가로를 꽉 채우고 높이는 이미지에 맞춘다** → 잘림 0, 빈공간 0.
- **웹(브라우저·노트북):** 가로 전체를 꽉 채운다. **좌우가 잘리면 실패.** 세로로 긴 페이지를 고정 높이 창에 넣을 땐 **아래만** 클립(위 정렬), 좌우는 항상 완전.
- **앱(폰):** 스크린샷을 **기기 화면 비율 그대로** 캡처해 넣는다 → 프레임에 딱 맞아 잘림·빈공간 0.
- 기기 프레임(브라우저 바·폰 베젤)은 **장식이 아니라 "기기 표현"**이므로 Border·Shadow 금지의 **예외**다. 단 Shadow는 **목업을 띄우는 용도로 1단계**만.

### Source — 브라우저(웹) 목업

```html
<figure class="mockup mockup--browser">
  <div class="mockup__bar">
    <span class="mockup__dot"></span><span class="mockup__dot"></span><span class="mockup__dot"></span>
    <span class="mockup__url">example.com</span>
  </div>
  <div class="mockup__screen">
    <img src="SCREENSHOT.png" alt="서비스 화면">
  </div>
</figure>
```

```css
.mockup{max-width:960px;margin:0 auto;border-radius:16px;overflow:hidden;background:#fff;
  box-shadow:0 24px 60px -30px rgba(20,24,30,.35);}            /* 목업 띄우는 1단계 elevation (예외 허용) */
.mockup--browser .mockup__bar{display:flex;align-items:center;gap:8px;padding:12px 16px;background:var(--surface-2);}
.mockup__dot{width:11px;height:11px;border-radius:50%;background:#cbd2db;}
.mockup__url{margin-left:10px;font-size:13px;color:var(--text-3);background:#fff;border-radius:999px;padding:5px 14px;}
.mockup__screen{overflow:hidden;background:#fff;}
/* 핵심: 가로 꽉 + 자연 높이 → 좌우 잘림 0, 빈공간 0 */
.mockup__screen img{display:block;width:100%;height:auto;}

/* (옵션) 고정 높이 창: 아래만 클립, 좌우는 항상 완전 */
.mockup__screen--fixed{height:480px;}          /* 또는 aspect-ratio:16/10; */
.mockup__screen--fixed img{width:100%;height:auto;}  /* 위 정렬 + overflow:hidden로 아래 클립 */
```

### Source — 폰(앱) 목업

```html
<figure class="mockup mockup--phone">
  <div class="mockup__screen"><img src="APP.png" alt="앱 화면"></div>
</figure>
```

```css
.mockup--phone{width:280px;max-width:72vw;margin:0 auto;padding:12px;background:#1A1C20;border-radius:40px;
  box-shadow:0 24px 60px -30px rgba(20,24,30,.4);}
.mockup--phone .mockup__screen{border-radius:30px;overflow:hidden;background:#fff;}
/* 스크린샷을 폰 화면 비율로 캡처해 넣으면 딱 맞음 (잘림·빈공간 0) */
.mockup--phone .mockup__screen img{display:block;width:100%;height:auto;}
```

- 반응형: 목업 컨테이너는 `width:100%`(웹) / `max-width` + `vw`(폰)로 두어 작은 화면에서 자동 축소한다.
- 스크린샷 파일은 **실제 서비스 화면**을 쓰고, **상업용 사용권**을 확인한다. (`7. Imagery` 참고)

---

## 요약 체크리스트

- [ ] 폰트 2개 이하 · 세리프 없음 · 본문 14px↑
- [ ] 한국어 `word-break: keep-all` (음절 쪼개짐 방지)
- [ ] 행간 고정값: 제목 1.25 / Heading 1.35 / 서브 1.45 / 본문 1.6 / 캡션 1.4 (임의값 금지, 한글 제목 1.2↓ 금지)
- [ ] Primary는 S55–85 / L40–58, 톤은 Hue로만
- [ ] Neutral은 거의 무채색 + Primary 쪽으로 살짝만 (베이지/브라운 금지)
- [ ] 텍스트 대비 4.5:1, 버튼 글자 대비 확인
- [ ] Border·Shadow 지양, 명도차로 구분
- [ ] Radius 8–20px 통일 · 컴포넌트 Padding 4/8/16/24
- [ ] 콘텐츠 최대폭 + 섹션 세로 여백 크게 + 모바일 1열
- [ ] 메뉴 가운데 정렬이면 3분할 그리드(1fr auto 1fr)로 진짜 중앙에
- [ ] 히어로 메시지 + CTA 1개(히어로·끝 반복) + 3초 스캔
- [ ] 이미지는 상업용 사용권 확인
- [ ] 기기 목업: 안 화면 잘림·빈공간 0 (비율 일치 / 웹은 가로 꽉·좌우 안 잘림)
