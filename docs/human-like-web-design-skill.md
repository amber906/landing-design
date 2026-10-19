# Human-Like Web Design Skill

AI가 생성한 웹사이트가 획일적이고 인공적인 느낌을 주지 않도록,
실제 제품 디자이너가 설계한 것처럼 자연스럽고 일관된 UI를 생성한다.

---

## 1. Typography

### Font Family

- 한 화면에서 사용하는 Font Family는 최대 2개로 제한한다.
- Korean: `Pretendard`를 기본 폰트로 사용한다.
- English: `Inter`를 기본 폰트로 사용한다.
- Korean fallback이 필요한 경우 고딕 계열 시스템 폰트를 사용한다.
- Serif / 명조 계열 폰트는 사용하지 않는다.
- 별도의 장식용 폰트나 개성 강한 Display Font를 추가하지 않는다.

### Typography Scale

SEED Design의 Typography Scale을 기본 기준으로 사용한다.

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
- 대형 제목은 실제로 큰 시각적 위계가 필요한 경우에만 제한적으로 사용한다.

### Font Weight

- Regular: `400`
- Medium: `500`
- Bold: `700`
- 불필요하게 다양한 Font Weight를 사용하지 않는다.

### Line Height & Letter Spacing

- SEED Typography의 대응 Line Height를 기본값으로 사용한다.
- 텍스트가 지나치게 밀집되어 보이지 않도록 충분한 Line Height를 확보한다.
- AI가 자주 생성하는 지나치게 타이트한 Line Height와 Letter Spacing을 피한다.
- 본문은 특히 읽기 편한 수직 리듬을 우선한다.
- 구체적인 Letter Spacing 값은 실제 결과를 확인하며 조정한다.

### Content

- 메뉴 항목마다 의미 없는 설명 문구를 추가하지 않는다.
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

#### Avoid

- Saturation `< 45%`
  - 지나치게 Muted되어 탁하고 생기 없는 인상을 줄 수 있다.
- Saturation `> 90%`
  - 지나치게 강하고 자극적인 색으로 보일 수 있다.
- Lightness `< 35%`
  - Primary Color가 지나치게 어둡고 무거워질 수 있다.
- Lightness `> 65%`
  - 색이 지나치게 흐려지고 존재감이 약해질 수 있다.

### Visual Check

수치 범위에 포함되더라도 다음 조건을 만족하지 않으면 사용하지 않는다.

- 회색이 섞인 듯 탁해 보이지 않아야 한다.
- 형광색처럼 지나치게 강하게 튀지 않아야 한다.
- 밝은 배경에서 충분한 시각적 존재감이 있어야 한다.
- 장시간 바라보아도 지나치게 자극적이지 않아야 한다.
- Primary Color 하나만으로 화면이 과도하게 화려해지지 않아야 한다.

### Color Palette

SEED Design의 Palette 구조를 참고하여 컬러를 단계별로 관리한다.

- Neutral: 배경, Surface, 텍스트, 보조 UI
- Primary: 서비스의 핵심 브랜드 컬러
- Blue: 정보 및 보조 강조
- Green: 성공 및 긍정 상태
- Yellow: 주의 및 경고 상태
- Red: 오류 및 위험 상태
- Purple: 보조적인 강조 및 특수 상태

각 컬러는 밝은 단계부터 어두운 단계까지 여러 단계로 구성한다.

### Color Token Naming

SEED의 Palette 구조를 참고하되, 특정 디자인 시스템의 이름을 그대로 복제하지 않는다.

짧고 직관적인 자체 명칭을 사용한다.

예:

- `neutral-100`
- `neutral-200`
- `neutral-500`
- `neutral-900`
- `primary-100`
- `primary-500`
- `primary-700`
- `success-500`
- `warning-500`
- `danger-500`
- `info-500`

### Neutral Color

- Neutral Palette는 기본적으로 Cool Gray 계열을 사용한다.
- 따뜻한 Beige / Brown 계열의 Gray를 기본 Neutral로 사용하지 않는다.
- Pure Black `#000000`은 사용하지 않는다.
- 가장 어두운 Neutral은 `#1A1C20`을 기준으로 한다.
- `#1A1C20`보다 어두운 색상은 생성하지 않는다.
- 검은색이 필요한 경우에도 Pure Black 대신 Dark Neutral을 사용한다.

### Neutral Hierarchy

Neutral Color는 명확한 명도 단계를 만들어 정보의 위계를 구분한다.

- Primary Text: 가장 진한 Neutral
- Secondary Text: 한 단계 낮은 Neutral
- Tertiary Text: 보조 정보에 사용하는 낮은 명도의 Neutral
- Background: 가장 밝은 Neutral
- Surface: Background와 구분되는 밝기의 Neutral

### Contrast & Separation

- 서로 인접한 영역에는 충분한 명도 차이를 확보한다.
- 서로 다른 역할의 영역이 비슷한 명도로 겹쳐 시각적 계층이 사라지는 것을 피한다.
- Background와 Content 영역의 명도가 지나치게 유사하지 않도록 한다.
- 색상만으로 구분해야 하는 영역은 충분한 명도 차이를 확보한다.

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
- Card 안에 Card를 중첩하는 구조를 최대한 피한다.
- `Card > Card > Card`와 같은 다중 중첩 구조를 사용하지 않는다.
- 페이지 전체가 여러 개의 동일한 Card로 채워지는 구성을 피한다.
- 콘텐츠의 관계가 명확하다면 Card 대신 여백, Background, Typography를 이용해 그룹을 표현한다.

### Background & Surface

영역을 구분할 때 외곽선보다 Background와 Surface의 명도 차이를 우선적으로 사용한다.

#### Light Background

- 연한 Gray Background 위에는 White Surface/Card를 사용할 수 있다.
- 예: `Gray Background → #FFFFFF Card`
- Gray와 White의 명도 차이를 이용하여 영역을 구분한다.
- Card에 별도의 Border나 Shadow를 추가하지 않는다.

#### Dark Background

- 진한 Background 위에는 상대적으로 밝은 Surface를 사용한다.
- Background와 Card 사이에 충분한 명도 차이를 확보한다.

#### Surface Hierarchy

- 밝은 Card/Surface 위에 또 다른 비슷한 명도의 Card를 중첩하지 않는다.
- 여러 단계의 유사한 Surface를 겹쳐 계층을 표현하는 방식을 피한다.

### Border

- Border는 기본적으로 사용하지 않는다.
- Card와 Background를 구분하기 위해 Border를 우선적으로 사용하지 않는다.
- 가능한 경우 Background와 Surface의 명도 차이로 영역을 구분한다.
- 장식적인 Border를 사용하지 않는다.
- 하나의 화면에서 불필요하게 많은 외곽선이 반복되지 않도록 한다.

### Shadow

- Card에는 기본적으로 Shadow를 사용하지 않는다.
- Card를 띄워 보이게 하기 위한 장식적인 Shadow를 사용하지 않는다.
- 여러 단계의 Shadow를 사용하여 계층을 표현하지 않는다.
- 특별한 인터랙션 또는 명확한 Elevation이 필요한 경우에만 제한적으로 사용한다.

### Visual Hierarchy

영역의 계층은 다음 우선순위로 표현한다.

1. Layout & Spacing
2. Background / Surface
3. Typography
4. Border
5. Shadow

가능하면 앞 단계의 방법만으로 계층을 해결한다.

### Anti-AI Patterns

다음 패턴은 사용하지 않거나 최대한 피한다.

- Card 안에 Card
- Card 안에 Card 안에 Card
- 모든 Section을 Card로 감싸기
- 모든 요소에 Border 적용
- 모든 Card에 Shadow 적용
- 여러 단계의 Gray Surface 중첩
- Shadow + Border + Background를 동시에 사용하여 하나의 Card를 과도하게 강조

---

## 4. Border Radius

### Radius Range

- 모든 Radius는 최소 `8px`, 최대 `20px` 범위에서 사용한다.
- `8px` 미만의 Radius는 사용하지 않는다.
- `20px`을 초과하는 Radius는 사용하지 않는다.
- `9999px` 또는 과도하게 둥근 Pill 형태를 기본 UI에 사용하지 않는다.
- `rounded-full`은 원형 요소나 반드시 필요한 특수한 경우에만 제한적으로 사용한다.

### Consistency

- 동일한 화면에서 동일한 역할을 하는 컴포넌트는 동일한 Radius를 사용한다.
- 예를 들어 해당 화면의 Card Radius가 `16px`이라면 모든 Card는 `16px`로 통일한다.
- 동일한 유형의 컴포넌트에 서로 다른 Radius를 임의로 적용하지 않는다.
- 한 화면에서 `8px`, `12px`, `16px`, `20px`을 무분별하게 혼합하지 않는다.
- 화면 전체에서 일관된 Radius Scale을 유지한다.

### Radius Hierarchy

- 컴포넌트의 크기와 역할에 따라 Radius를 결정하되, 한 화면에서는 제한된 Radius 값만 사용한다.
- 큰 컨테이너라고 해서 무조건 큰 Radius를 적용하지 않는다.
- 콘텐츠의 성격보다 시각적 장식을 위해 Radius를 과도하게 키우지 않는다.
- 전체 UI가 지나치게 둥글고 장난스러워 보이지 않도록 한다.

### Anti-AI Patterns

- 모든 UI 요소에 큰 Radius를 적용하지 않는다.
- 모든 Button을 Pill 형태로 만들지 않는다.
- Card마다 서로 다른 Radius를 사용하지 않는다.
- `16px` 이상의 Radius를 불필요하게 남발하지 않는다.
- 둥근 모서리를 단순히 "예뻐 보이게" 하기 위한 장식으로 사용하지 않는다.

---

## 5. Spacing & Padding

### Padding Principles

- 컴포넌트의 기본 Padding은 상하좌우 동일한 값을 사용한다.
- 특별한 레이아웃상의 이유가 없다면 `padding-top`, `padding-right`, `padding-bottom`, `padding-left`를 서로 다른 값으로 설정하지 않는다.
- Padding을 사용하여 콘텐츠 주변에 과도한 빈 공간을 만들지 않는다.
- 콘텐츠보다 Padding이 더 눈에 띄는 구성을 피한다.

### Padding Scale

컴포넌트의 크기와 콘텐츠 밀도에 따라 제한된 Padding Scale을 사용한다.

- Small: `4px`
- Medium: `8px`
- Large: `16px`
- X-Large: `24px`

#### Rules

- 작은 컴포넌트는 기본적으로 `4px` Padding을 사용한다.
- 컴포넌트의 크기가 커질수록 Padding을 단계적으로 증가시킬 수 있다.
- 최대 Padding은 `24px`을 넘지 않는다.
- 임의의 `13px`, `18px`, `27px` 등 비정형적인 Padding 값을 생성하지 않는다.
- 동일한 역할과 크기의 컴포넌트는 동일한 Padding 값을 사용한다.
- 한 화면에서 불필요하게 많은 Padding Scale을 혼합하지 않는다.

### Content Density

- 컴포넌트의 크기에 비해 과도한 Padding을 적용하지 않는다.
- 작은 콘텐츠를 지나치게 큰 Padding으로 감싸지 않는다.
- 컴포넌트 내부 여백을 늘리는 것보다 외부 간격이 필요한 경우 Layout의 Gap을 우선적으로 사용한다.
- 화면 전체를 과도한 Padding으로 채워 콘텐츠가 지나치게 작아 보이는 것을 피한다.

### Consistency

- 동일한 유형의 컴포넌트는 동일한 Padding을 사용한다.
- 같은 화면 안에서 동일한 크기와 역할의 Card는 동일한 Padding을 유지한다.
- 컴포넌트마다 임의의 Padding 값을 적용하여 시각적인 리듬이 깨지지 않도록 한다.
