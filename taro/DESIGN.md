# TARO AI — Style & Design System Guide
> **Mystic Editorial Darkroom.** 어두운 암실 속 따뜻한 빛을 머금은 단 하나의 타로 카드 오브제, 온화한 크림빛 타이포그래피와 절제된 엠버 액센트.

**Theme:** Dark (Warm Dark Editorial)  
**Target:** Mobile Web (최대 너비 440px 모바일 뷰포트 중심 & 1080×1350 카드 이미지 저장 최적화)  
**Reference:** ORYZO Visual System × shadcn/ui × Tailwind CSS v4  
**Connected Specs:** [TARO_01_PRD.md](file:///c:/Users/seoji/Desktop/taro/TARO_01_PRD.md), [TARO_02_기능명세서.md](file:///c:/Users/seoji/Desktop/taro/TARO_02_기능명세서.md), [TARO_03_유저플로우.md](file:///c:/Users/seoji/Desktop/taro/TARO_03_유저플로우.md), [TARO_04_와이어프레임.md](file:///c:/Users/seoji/Desktop/taro/TARO_04_와이어프레임.md)

---

## 1. 디자인 철학 및 비주얼 컨셉

1. **단 하나의 유물(Museum Artifact)로서의 타로 카드**
   - 화려하고 산만한 흔한 점술 사이트의 네온·보라색 그래픽을 배제합니다.
   - 전시관 암실의 스포트라이트를 받는 유물처럼, 깊고 따뜻한 흑갈색 캔버스(`Walnut Shadow`) 위에 카드 한 장과 타이포그래피만 단정하게 떠오릅니다.
2. **2단계 서피스 스택 (그림자 배제)**
   - 블러(Blur)나 드롭 섀도우(Drop Shadow)를 일체 사용하지 않습니다.
   - 바닥면(`Walnut Shadow #100904`) → 엘리베이션 면(`Bark Brown #382416`)의 2단계 단차와 섬세한 1px 대시 보더(`Cork Border #40372e`)만으로 깊이감을 완성합니다.
3. **두 가지 타이포그래피 보이스 (Typographic Voice)**
   - **UPPERCASE 500 (절제와 선언):** 서비스명, 카드 이름(XIX THE SUN), 주제 뱃지, 버튼, 법적 고지.
   - **MIXED-CASE 400 (사적인 대화):** 사용자의 생년월일과 전공을 결합한 3줄 맞춤 해석 문장.
4. **극도로 절제된 엠버 액센트 (Ember Accent)**
   - 강렬한 오렌지빛 엠버(`#dc5000`)는 버튼 배경으로 절대 남용하지 않으며, 활성화 인디케이터·태그 점·자물쇠 아이콘 등 극소수의 시각적 포인트에만 부여합니다.

---

## 2. 디자인 토큰 — 컬러 (Colors)

### 2.1 팔레트 정의

| Name | Hex Value | Token | shadcn Semantic Mapping | 역할 및 사용 가이드 |
|------|-----------|-------|--------------------------|-------------------|
| **Walnut Shadow** | `#100904` | `--color-walnut-shadow` | `--background`, `--popover` | 전체 모바일 캔버스 및 가장 깊은 배경 (순수 블랙이 아닌 따뜻한 흑갈색) |
| **Bark Brown** | `#382416` | `--color-bark-brown` | `--card`, `--primary`, `--secondary` | 카드 뒷면/앞면 표면, 유일한 단색 채움 CTA 버튼 배경 |
| **Cork Border** | `#40372e` | `--color-cork-border` | `--border`, `--input` | 1px 헤어라인 점선 분할선, 입력창 하단선, 카드 테두리 |
| **Driftwood** | `#8c7b6d` | `--color-driftwood` | `--muted-foreground` | 서브 텍스트, 비활성 텍스트, 부가 설명문 |
| **Warm Cream** | `#ffedd7` | `--color-warm-cream` | `--foreground`, `--card-foreground` | 메인 텍스트, 카드 제목, 고대비 레이블 (순수 화이트 `#fff` 금지) |
| **Ember Accent** | `#dc5000` | `--color-ember-accent` | `--accent` (Indicator only) | 선택된 주제 칩 인디케이터, 중요 키워드, 프라이버시 락 아이콘 |
| **Pure Black** | `#000000` | `--color-pure-black` | — | 타로 카드 일러스트 내부 음영 및 SVG 마스크 전용 |

### 2.2 do's and don'ts (컬러)
- **DO:** 모든 텍스트는 온화한 크림빛 `#ffedd7`을 기준으로 작성합니다.
- **DO:** 테두리와 구분선은 1px 점선(`border-dashed border-cork-border`)을 기본으로 사용합니다.
- **DON'T:** `#ffffff`(순수 화이트)나 `#000000`(순수 블랙 캔버스)을 사용하지 않습니다.
- **DON'T:** `#dc5000`(엠버)을 버튼의 전체 배경색으로 사용하지 않습니다. 버튼은 언제나 `#382416`(Bark Brown) 또는 투명 고스트 버튼을 사용합니다.

---

## 3. 디자인 토큰 — 타이포그래피 (Typography)

### 3.1 폰트 패밀리
- **한글 및 기본 본문:** `Pretendard`, `-apple-system`, `BlinkMacSystemFont`, `system-ui`, `sans-serif`
- **타로 카드명 및 로마자/영문:** `Cinzel`, `Halyard Display Variable`, `serif` / `sans-serif`

### 3.2 타이포그래피 스케일

| Token | Size | Line Height | Weight | Letter Spacing | 적용 위치 |
|-------|------|-------------|--------|----------------|-----------|
| `--text-display` | 44px | 0.95 | 500 | -0.02em | 타로 카드 로마 숫자 및 카드 대형 심볼 (XIX) |
| `--text-heading` | 24px | 1.15 | 500 | -0.01em | S-03 결과 카드 메인 타이틀 ("지민님의 타로 · 커리어") |
| `--text-heading-sm`| 18px | 1.25 | 500 | 0 | S-01 시작 타이틀, 모달 제목, 카드 이름 ("XIX 태양") |
| `--text-body` | 15px | 1.60 | 400 | -0.01em | **F-4 맞춤 해석 3줄 문장** (가장 가독성 높은 줄간격) |
| `--text-body-sm` | 13px | 1.40 | 400 | 0 | 폼 라벨, 주제 칩 텍스트, 버튼 라벨 |
| `--text-caption` | 11px | 1.30 | 500 | +0.02em | 오락용 안내 ("※ 오락용 타로 해석입니다"), 개인정보 안내문 |
| `--text-micro` | 9px | 1.20 | 500 | +0.04em | 하단 저작권, 카드 이미지 하단 서비스 워터마크 |

---

## 4. 형태 및 간격 (Shapes, Spacing & Layout)

### 4.1 Border Radius (모서리 곡률 규칙)
시스템 전체에서 허용되는 radius는 단 4가지입니다:

```css
--radius-cards: 12px;       /* 타로 카드 본체, 안내 모달 컨테이너 (rounded-xl) */
--radius-inputs: 0px;       /* 텍스트 입력창 (하단 보더만 사용하는 미니멀 언더라인) */
--radius-buttons-ghost: 22.5px; /* 고스트 아웃라인 버튼 (rounded-full) */
--radius-buttons-pill: 36px;    /* 주요 채움 CTA 버튼 및 주제 칩 (rounded-full) */
```

### 4.2 레이아웃 & 패딩 규격
- **모바일 셸 너비:** `max-w-[440px]`, `w-full`, `min-h-screen`, `mx-auto`
- **화면 내부 패딩:** `px-6 py-8` (좌우 24px, 상하 32px)
- **컴포넌트 간 기본 수직 갭:** `gap-6` (24px) 또는 `gap-4` (16px)
- **구분선 규격:** `border-t border-dashed border-[#40372e]` (1px)

---

## 5. shadcn/ui 컴포넌트 스타일링 규칙

### 5.1 버튼 (`Button`) — Pill & Ghost
- **Primary CTA (`[타로 시작]`, `[카드 한 장 뽑기]`):**
  - 형태: `h-14 w-full rounded-full bg-[#382416] text-[#ffedd7] font-medium text-sm border border-[#40372e] hover:bg-[#4a301e] active:scale-[0.98] transition-all`
  - 비활성화 상태: `opacity-40 pointer-events-none border-dashed`
- **Secondary Ghost Button (`[이미지 저장]`, `[결과 공유]`):**
  - 형태: `h-12 flex-1 rounded-full bg-transparent text-[#ffedd7] border border-[#ffedd7]/30 hover:border-[#ffedd7] hover:bg-[#382416]/40 text-xs font-medium`
- **Text Button (`[다시 뽑기]`, `[처음으로]`):**
  - 형태: `h-10 text-xs text-[#8c7b6d] hover:text-[#ffedd7] underline underline-offset-4 decoration-dashed`

### 5.2 입력 폼 (`Field`, `FieldLabel`, `Input`) — Underline Only
- shadcn의 `FieldGroup` + `Field` 구조를 준수하되, 인풋 테두리를 사각 박스가 아닌 **언더라인(Bottom Border Only)** 스타일로 구현합니다.
- `FieldLabel`: `text-xs text-[#8c7b6d] uppercase tracking-wider mb-1`
- `Input`: `h-11 w-full bg-transparent border-0 border-b border-[#40372e] rounded-none px-0 text-[#ffedd7] text-base placeholder:text-[#8c7b6d]/50 focus-visible:ring-0 focus-visible:border-[#ffedd7] transition-colors`
- 필수 안내 힌트: `text-[11px] text-[#8c7b6d]`

### 5.3 주제 선택 칩 (`ToggleGroup` + `ToggleGroupItem`)
- 6개 주제(💼 커리어, 💰 재물, 💕 연애, 🌿 건강, 📚 학업, ✨ 종합)를 `grid grid-cols-3 gap-2.5`로 배치합니다.
- 기본 상태: `h-10 rounded-full border border-[#40372e] bg-[#100904] text-[#8c7b6d] text-xs font-medium`
- 선택 상태: `border-[#ffedd7] bg-[#382416] text-[#ffedd7] relative font-medium before:content-[''] before:size-1.5 before:rounded-full before:bg-[#dc5000] before:mr-1.5`

### 5.4 타로 결과 카드 (`Card`)
- 비율: 세로형 황금비 (저장 이미지 규격인 4:5 비율 대응)
- 구조:
  - 외부: `rounded-xl border border-[#40372e] bg-[#1a110a] p-6 text-center relative overflow-hidden`
  - 카드 프레임: 중앙에 22장 메이저 아르카나 일러스트(종횡비 1:1.6) 배치, 테두리에 1px 대시 보더
  - 뒤집기 애니메이션: `transition-transform duration-700 [transform-style:preserve-3d]`

### 5.5 보안/개인정보 안내문 (`Alert` / Callout)
- `rounded-lg border border-dashed border-[#40372e] bg-[#100904]/80 p-3.5 text-left flex items-start gap-2.5`
- 아이콘: `🔒` 또는 `LockIcon` (`text-[#dc5000] size-4 shrink-0 mt-0.5`)
- 문구: `text-[11px] leading-relaxed text-[#8c7b6d]`

---

## 6. 화면별 세부 컴포넌트 인터랙션

### S-01 시작 화면 (F-1)
- **비주얼:** 상단에 신비로운 빛을 받는 타로 카드 뒷면 3D/플랫 그래픽이 부드럽게 부유(Floating subtle animation, 3초 주기).
- **카피라이트:**
  - 상단: `🔮 오늘의 맞춤 타로` (Display Heading)
  - 서브: `내 정보를 넣고 카드 한 장으로 나만의 해석을 받아 봐요`
- **액션:** 하단 단일 고정형 `[타로 시작]` Pill Button (`bg-[#382416]`).
- **하단 캡션:** `※ 오락용 타로 · 정보는 저장되지 않아요`

### S-02 내 정보 & 주제 선택 화면 (F-2)
- **상단 바:** 뒤로가기 화살표(`←`) 및 타이틀 `나에 대해 알려 주세요`.
- **입력 섹션:**
  1. `이름 (닉네임 가능)`: 최대 10자 입력 제한.
  2. `생년월일`: `YYYY . MM . DD` 포맷 마스킹 및 날짜 유효성 검증.
  3. `전공 (선택)`: "예: 경영학과, 컴퓨터공학" (계열 매핑용).
- **주제 선택:** 6개 주제 칩 그리드.
- **안내 박스:** 자물쇠 아이콘 + "입력한 정보는 해석을 만드는 데만 쓰고 저장하지 않아요."
- **하단 버튼:** `[카드 한 장 뽑기]`. 이름·생년월일·주제가 모두 채워지기 전까지 `disabled` 상태 유지.

### S-03 맞춤 해석 결과 화면 (F-4 ~ F-7)
- **카드 뒤집기 연출:** 진입 시 0.8초간 카드가 뒷면에서 앞면으로 회전하며 서서히 공개됨.
- **결과 카드 컴포넌트 (저장 영역):**
  - 헤더: `{이름}님의 타로 · {주제}`
  - 카드 비주얼: 메이저 아르카나 정방향 일러스트
  - 카드 타이틀: `{번호} {카드명} · {별자리 기호} {별자리명}`
  - 3줄 해석:
    1. *기본 문장 (카드 × 주제)*: 예) "지민님, 준비한 것을 드러낼 때예요."
    2. *별자리 문장*: 예) "사자자리의 자신감이 오늘은 무기가 돼요."
    3. *전공 문장 (선택 시)*: 예) "경영학도다운 기획력이 빛나는 날이에요."
  - 면책 문구: `※ 오락용 타로 해석입니다`
- **하단 액션 그룹:**
  - 1열: `[ 📥 이미지 저장 ]` `[ 🔗 결과 공유 ]` (Ghost Button 5:5 분할)
  - 2열: `[ 다시 뽑기 ]` `[ 처음으로 (정보 삭제) ]` (Text Button)

---

## 7. F-5 결과 이미지 저장 규격 (1080 × 1350)

html2canvas 또는 modern-screenshot 라이브러리로 캡처할 타로 결과 카드의 정밀 규격:

```
┌───────────────────────────────────────────┐
│ [헤더 80px] TARO : DAILY ESSENCE          │
│                                           │
│  지민님의 타로 · 커리어                   │
│                                           │
│  ┌─────────────────────────────────────┐  │
│  │                                     │  │
│  │        [ 타로 카드 일러스트 ]        │  │
│  │                                     │  │
│  └─────────────────────────────────────┘  │
│                                           │
│  XIX THE SUN · ♌ LEO                      │
│                                           │
│  준비한 것을 세상에 드러낼 때예요.         │
│  사자자리의 자신감이 오늘은 무기가 돼요.  │
│  경영학도다운 기획력이 빛나는 날이에요.   │
│                                           │
│  ───────────────────────────────────────  │
│  ※ 본 결과는 오락용 해석이며 개인정보는  │
│    어디에도 저장되지 않습니다.            │
│  TARO PROJECT · 2026                      │
└───────────────────────────────────────────┘
```
- **해상도:** 1080 × 1350 px (4:5 Ratio)
- **배경색:** `#100904` (Walnut Shadow)
- **카드 테두리:** `#40372e` (2px solid with 1px inset dashed line)
- **개인정보 보호 원칙 준수:** 생년월일 전체 날짜 및 전공 원문 텍스트는 이미지에 절대 인쇄하지 않음.

---

## 8. Tailwind CSS v4 & Theme 코드 블록

`app/globals.css` 파일에 적용할 테마 설정:

```css
@import "tailwindcss";

@theme inline {
  /* Colors */
  --color-walnut-shadow: #100904;
  --color-bark-brown: #382416;
  --color-cork-border: #40372e;
  --color-driftwood: #8c7b6d;
  --color-warm-cream: #ffedd7;
  --color-ember-accent: #dc5000;

  /* shadcn/ui Semantic Variables Mapping */
  --color-background: var(--color-walnut-shadow);
  --color-foreground: var(--color-warm-cream);

  --color-card: #191008;
  --color-card-foreground: var(--color-warm-cream);

  --color-popover: var(--color-walnut-shadow);
  --color-popover-foreground: var(--color-warm-cream);

  --color-primary: var(--color-bark-brown);
  --color-primary-foreground: var(--color-warm-cream);

  --color-secondary: #24160c;
  --color-secondary-foreground: var(--color-warm-cream);

  --color-muted: #1c130b;
  --color-muted-foreground: var(--color-driftwood);

  --color-accent: var(--color-bark-brown);
  --color-accent-foreground: var(--color-warm-cream);

  --color-destructive: #7f1d1d;
  --color-destructive-foreground: #fee2e2;

  --color-border: var(--color-cork-border);
  --color-input: var(--color-cork-border);
  --color-ring: var(--color-warm-cream);

  /* Radius */
  --radius-xl: 12px;
  --radius-2xl: 22.5px;
  --radius-full: 9999px;

  /* Fonts */
  --font-sans: 'Pretendard', system-ui, -apple-system, sans-serif;
  --font-serif: 'Cinzel', serif;
}

:root {
  color-scheme: dark;
}

body {
  background-color: var(--color-walnut-shadow);
  color: var(--color-warm-cream);
  font-family: var(--font-sans);
  -webkit-font-smoothing: antialiased;
}
```

---

## 9. 컴포넌트 구현 체크리스트 (Developer Do's & Don'ts)

### Do (필수 적용 사항)
1. **모바일 퍼스트 레이아웃:** 최상단 컨테이너에 `max-w-[440px] w-full mx-auto min-h-screen flex flex-col justify-between`을 기본 적용할 것.
2. **시맨틱 토큰 우선:** 컴포넌트 스타일링 시 `bg-[#382416]` 대신 `bg-primary`, `border-border`, `text-muted-foreground` 등 시맨틱 클래스를 우선 사용할 것.
3. **간격 규칙 준수:** 요소 간격은 flex 컨테이너에 `gap-4` 또는 `gap-6`을 사용할 것 (`space-y-*` 금지).
4. **접근성 타이틀 필수:** 모달(`Dialog`, `Drawer`) 사용 시 시각적으로 숨기더라도 반드시 `DialogTitle className="sr-only"`를 포함할 것.
5. **카드 뒤집기 최적화:** 3D 회전 애니메이션 시 GPU 가속(`transform-gpu`)을 활성화하고 저사양 모바일 기기를 위해 1초 이내로 끝낼 것.

### Don't (절대 금지 사항)
1. **그림자(Shadow) 사용 금지:** `shadow-md`, `shadow-lg`, `drop-shadow` 클래스 일체 사용 금지.
2. **화이트/블랙 사용 금지:** `text-white`, `bg-black` 금지. 반드시 `text-warm-cream`과 `bg-walnut-shadow` 사용할 것.
3. **인풋 외곽선 박스 금지:** `border rounded-md` 형태의 인풋 박스를 만들지 말고, 하단선만 존재하는 미니멀 인풋 형태를 유지할 것.
4. **저장소 저장 금지:** `localStorage`, `sessionStorage`, `cookie`에 사용자 이름·생년월일·전공 데이터를 저장하는 코드를 절대 작성하지 말 것 (메모리 상태로만 유지).
