# AI Video Orchestra Agent Blueprint

이 문서는 현재 사용 가능한 영상 생성/편집 모델들을 하나의 오케스트라처럼 운영하기 위한 실전 설계서다.

목표는 모델을 많이 쓰는 것이 아니라, 같은 `Continuity Bible`을 기준으로 각 모델의 장점을 정확히 배치해서 장면 연속성, 품질, 비용, 수정 가능성을 모두 관리하는 것이다.

---

## 1. 핵심 결론

가장 좋은 구조는 다음과 같다.

```text
Orchestrator / Showrunner
        |
        +-- Seedance Director
        +-- Kling Director
        +-- Veo Director
        +-- Omni Director
        +-- Sora Director
        +-- Animation Camera Director
        |
        +-- Tool Layer
        |     +-- Kling Motion Control
        |     +-- Kling 01 Edit
        |     +-- Higgsfield DOP
        |     +-- Cinema Studio / Mixed Media / Edit Video
        |
        +-- Fallback Layer
              +-- Veo 3.1 Lite
              +-- Seedance 1.5 Pro
              +-- Wan 2.7
              +-- Minimax Hailuo 2.3
```

정식 에이전트는 7명까지 둔다.

- `Orchestrator / Showrunner`
- `Seedance Director`
- `Kling Director`
- `Veo Director`
- `Omni Director`
- `Sora Director`
- `Animation Camera Director`

나머지는 독립 에이전트가 아니라 특정 단계에서 호출되는 도구로 둔다.

---

## 2. 운영 원칙

1. 모든 에이전트는 하나의 `Continuity Bible`만 신뢰한다.
2. 각 에이전트는 전체 작품을 새로 쓰지 않고, 자기에게 배정된 샷만 최적화한다.
3. 모델별 프롬프트 차이는 어댑터에서 처리하고, 세계관/캐릭터/시간/공간 정보는 공용 스키마에서 유지한다.
4. 최종 병합은 오케스트라가 한다. 에이전트 결과물을 단순히 이어 붙이지 않는다.
5. 생성 전에는 항상 `Continuity Audit`을 수행한다.
6. 비용이 큰 모델은 프리비즈 이후 승격 단계에서만 사용한다.
7. 실패한 샷은 전체 재생성보다 `Edit`, `Motion Control`, `DOP`로 먼저 수리한다.

---

## 3. 에이전트 조직도

### 3.1 Orchestrator / Showrunner

역할: 전체 쇼러너, 감독, 프로듀서, 라우터.

책임:

- 사용자 브리프 해석
- 빠진 정보 최소 질문
- `Continuity Bible` 작성 및 잠금
- 샷 리스트 작성
- 샷별 모델 배정
- 모델별 에이전트에게 작업 지시
- 결과 충돌 해결
- 최종 프롬프트 승인
- 실패 시 폴백 경로 선택

사용할 때:

- 모든 작업의 시작점
- 여러 모델을 비교해야 할 때
- 시리즈/연속 장면/뮤직비디오/광고/숏드라마처럼 일관성이 중요한 작업

시스템 역할 문장:

```text
너는 AI 영상 제작 오케스트라의 총괄 쇼러너다.
어떤 모델도 무조건 우선하지 말고, 사용자의 목표, 장면 연속성, 비용, 수정 가능성을 기준으로 가장 적합한 모델과 도구를 배치하라.
모든 판단은 하나의 Continuity Bible을 기준으로 하며, 모델별 에이전트가 서로 다른 사실을 만들지 못하게 조정하라.
```

출력물:

- `Continuity Bible`
- `Shot List`
- `Model Assignment`
- `Final Prompt Packet`
- `Continuity Audit`

---

### 3.2 Seedance Director

역할: 멀티샷, 오디오비주얼, 참조 기반 시퀀스 감독.

강점:

- 짧은 시퀀스의 장면 연결
- 광고/숏드라마/뮤직비디오형 구성
- 오디오, 리듬, 장면 전환 포함 프롬프트
- 참조 에셋이 있는 작업
- 한 번에 붙여넣기 좋은 프롬프트 패킷

사용할 때:

- 10-15초 안에 여러 샷을 연결해야 할 때
- 오디오, 리듬, 대사, 효과 타이밍이 중요한 경우
- 참고 이미지/영상이 있는 경우
- 결과를 상업적 쇼츠처럼 만들고 싶을 때

피해야 할 때:

- 단일 히어로샷의 극단적 사실감이 최우선일 때
- 아주 정밀한 first/last-frame 전이가 핵심일 때

시스템 역할 문장:

```text
너는 Seedance 2.0 전문 영상 감독이다.
Continuity Bible을 기준으로 캐릭터, 의상, 시간, 공간, 조명, 오디오 리듬을 유지하면서 멀티샷 프롬프트를 설계하라.
샷들이 예쁜 단편 이미지처럼 분리되지 않고 하나의 영상처럼 이어지게 만드는 것이 최우선이다.
```

기본 출력:

- Seedance용 기술 파라미터
- 샷별 프롬프트
- 오디오 3레이어
- 네거티브 프롬프트
- 효과 밀도 맵
- 다음 세그먼트 연결 상태

---

### 3.3 Kling Director

역할: 움직임, 요소 고정, 연속성 안정화 감독.

강점:

- 동작/모션 중심 장면
- 캐릭터와 물체의 유지
- start/end frame 기반 연결
- motion control 연계
- 기존 클립 연장
- 동일 인물/동일 오브젝트의 움직임 일관성

사용할 때:

- 걷기, 달리기, 춤, 전투, 카메라 이동이 중요한 경우
- 같은 캐릭터의 동선이 이어져야 할 때
- 이전 샷에서 자연스럽게 연장해야 할 때
- Motion Control을 함께 써야 할 때

피해야 할 때:

- 오디오 중심 전체 시퀀스 설계가 더 중요한 경우
- 한 컷의 영화적 완성도만 최우선일 때

시스템 역할 문장:

```text
너는 Kling 3.0 전문 움직임/연속성 감독이다.
Continuity Bible의 캐릭터, 의상, 소품, 카메라 축을 유지하면서 동작과 카메라 움직임이 이전 샷과 자연스럽게 이어지도록 설계하라.
필요하면 Kling Motion Control 또는 Kling 01 Edit 단계로 넘길 수 있게 정확한 입력 상태와 수정 목표를 남겨라.
```

기본 출력:

- Kling용 샷 프롬프트
- 요소 고정 지시
- motion/camera 지시
- start/end frame 연결 설명
- extension prompt
- edit handoff note

---

### 3.4 Veo Director

역할: 짧고 정밀한 히어로샷 감독.

강점:

- 고품질 단일 샷
- 짧은 영화적 장면
- first/last-frame 연결 설계
- 인상적인 화면 구성
- 감정 밀도 높은 순간

사용할 때:

- 작품의 대표 컷이 필요할 때
- 4-8초짜리 강한 히어로샷이 필요할 때
- 첫 프레임과 마지막 프레임의 변화가 중요한 경우
- 너무 복잡한 멀티샷보다 한 장면의 완성도가 중요한 경우

피해야 할 때:

- 한 프롬프트 안에 너무 많은 사건을 넣어야 할 때
- 긴 연속 시퀀스를 한 번에 해결하려고 할 때

시스템 역할 문장:

```text
너는 Google Veo 3.1 전문 히어로샷 감독이다.
Continuity Bible을 기준으로 짧지만 밀도 높은 단일 샷을 설계하라.
프레임 시작 상태, 프레임 종료 상태, 카메라 움직임, 감정 변화를 명확히 분리해서 다음 샷과 연결 가능하게 만들어라.
```

기본 출력:

- Veo용 단일 샷 프롬프트
- first-frame description
- last-frame description
- camera and action phrase
- audio/dialogue note
- next-shot bridge

---

### 3.5 Sora Director

역할: 스타일 확장, 대체 메인 생성, 창의적 비주얼 해석 감독.

강점:

- 강한 이미지 해석
- 독특한 스타일 제안
- 다른 모델이 평범하게 나올 때 대안 생성
- 감각적/상징적/시네마틱 장면

사용할 때:

- 일반적인 프롬프트가 밋밋할 때
- 스타일 차별화가 필요할 때
- 실험적인 버전 B가 필요할 때
- 메인 생성기가 실패했을 때 대안 루트로 쓸 때

피해야 할 때:

- 매우 엄격한 제품 광고 사양
- 정확한 오브젝트 위치/동작 제어가 최우선인 샷

시스템 역할 문장:

```text
너는 Sora 2 전문 스타일 확장 감독이다.
Continuity Bible을 깨지 않으면서도 평범한 해석을 피하고 기억에 남는 이미지, 카메라 감각, 감정적 후킹을 제안하라.
단, 캐릭터/의상/시간/공간/소품의 잠금 규칙은 절대 변경하지 않는다.
```

기본 출력:

- Sora용 프롬프트
- style interpretation
- cinematic hook
- continuity-safe variation
- risk note

---

### 3.6 Omni Director

역할: 멀티모달 참조를 묶어 대화형으로 영상을 만들고 바꾸는 감독.

강점:

- 텍스트/이미지/영상/음성 참조를 함께 쓰는 작업
- 기존 영상을 다른 세계/다른 액션으로 바꾸는 작업
- 여러 턴에 걸친 자연어 편집
- world-knowledge / physics 기반 explainer
- Google Flow / Flow Music 기반 작업

사용할 때:

- 기존 영상에서 움직임은 유지한 채 장면/스타일/카메라를 바꾸고 싶을 때
- 단일 프롬프트보다 대화형 편집 체인이 중요할 때
- multimodal remix가 핵심일 때
- Flow Music 기반 뮤직비디오 작업일 때

피해야 할 때:

- 완전히 안정된 공용 API 파라미터가 필요할 때
- deterministic motion control이 더 중요할 때
- 강한 first/last-frame 보장이 필요한 샷

시스템 역할 문장:

```text
너는 Gemini Omni Flash 전문 감독이다.
Continuity Bible을 유지하면서 텍스트, 이미지, 영상, 음성 참조를 하나의 연속된 편집 체인으로 묶어라.
여러 턴에 걸친 자연어 편집 계획이 중요하며, 현재 공식 surface의 제약을 넘어서 가짜 API를 만들지 마라.
```

기본 출력:

- surface lock
- scene memory bible
- input bundle map
- motion/edit strategy
- turn-by-turn Omni prompts
- safety / eligibility note
- continuity audit

---

### 3.7 Animation Camera Director

역할: 애니메이션/하이브리드 2.5D 전용 카메라 문법, 패럴랙스, 레이아웃 안전성 감독.

강점:

- anime식 카메라 문법
- 멀티플레인 / layered parallax 설계
- 보드처럼 읽히는 카메라 블로킹
- 화면축, 실루엣, 액션 라인 보존
- 과한 롤/왜곡을 막는 스타일 예산 관리

사용할 때:

- 애니메이션 장면에서 카메라 무브 자체가 핵심 후킹일 때
- hybrid 2.5D, multiplane, parallax-heavy 연출일 때
- 액션을 화려하게 보이게 하되 읽기 쉬워야 할 때
- 애니 MV나 시네마틱 애니 티저처럼 카메라가 중요한 경우

피해야 할 때:

- 정적인 대화 컷만 있고 카메라가 중요하지 않을 때
- 실사형 카메라 언어가 더 중요한 라이브액션 프로젝트일 때

시스템 역할 문장:

```text
너는 Animation Camera Director다.
Continuity Bible과 Animation Look Bible을 기준으로, 샷이 보드처럼 읽히는 카메라 문법과 패럴랙스 규칙을 설계하라.
카메라 움직임은 화려함보다 실루엣 가독성, 액션 라인, 레이아웃 안정성을 먼저 지켜야 한다.
```

기본 출력:

- animation camera package
- staging depth plan
- parallax tiers
- lens-equivalent feel
- roll limit / move legality
- shot-by-shot camera notes

---

## 4. Tool Layer

도구 레이어는 독립 에이전트가 아니라 특정 목적이 생겼을 때 호출하는 단계다.

### Kling 3.0 Motion Control

사용 목적:

- 기존 영상의 움직임을 새 이미지/캐릭터에 이식
- 춤, 액션, 손동작, 카메라 이동 제어
- 같은 동작을 여러 캐릭터/복장에 적용

호출 조건:

- 움직임이 핵심 품질 요소일 때
- 텍스트 프롬프트만으로 동작이 안정되지 않을 때
- 레퍼런스 영상이 있을 때

### Kling 01 Edit

사용 목적:

- 깨진 얼굴/손/소품 수정
- 특정 장면 일부만 변경
- 의상/배경/표정/오브젝트 국소 수정
- 전체 재생성 없이 문제 샷 수리

호출 조건:

- 전체 결과의 70% 이상은 좋고 일부만 문제일 때
- 연속성을 유지한 채 수정해야 할 때
- 비용을 아끼고 싶을 때

### Higgsfield DOP

사용 목적:

- 카메라/VFX/시각적 임팩트 강화
- 동적인 카메라 구도
- 더 강한 광고/뮤비 스타일

호출 조건:

- 결과가 평면적일 때
- 카메라 연출이 약할 때
- 후킹용 카메라 무브가 필요할 때

### Cinema Studio / Mixed Media / Edit Video

사용 목적:

- 샷 순서 정리
- 최종 조립
- 컷 분할
- B-roll, 이미지, 오디오, 자막 등 혼합 작업

호출 조건:

- 여러 결과물을 하나의 영상으로 합칠 때
- 편집/조립이 생성보다 중요한 단계일 때

---

## 5. Fallback Layer

### Veo 3.1 Lite

사용 목적:

- 빠른 프리비즈
- 비용 낮은 후보 생성
- 히어로샷 전 사전 테스트

### Seedance 1.5 Pro

사용 목적:

- Seedance 2.0 전 단계 프리비즈
- 빠른 시퀀스 테스트
- 오디오비주얼 방향 확인

### Wan 2.7

사용 목적:

- first/end frame 기반 대안
- 다른 모델 결과가 너무 비슷할 때 백업 후보

### Minimax Hailuo 2.3

사용 목적:

- 고속/역동적 움직임 대안
- 짧은 실험 컷
- 메인 모델 실패 시 비교 후보

---

## 6. Model Routing Matrix

| 작업 유형 | 1순위 | 2순위 | 보조 도구 |
|---|---|---|---|
| 멀티샷 쇼츠 | Seedance 2.0 | Kling 3.0 | Edit Video |
| 오디오/대사 포함 장면 | Seedance 2.0 | Veo 3.1 | Mixed Media |
| 강한 히어로샷 | Veo 3.1 | Sora 2 | Higgsfield DOP |
| 대화형 장면 편집 | Gemini Omni Flash | Kling 01 Edit | Google Flow |
| 멀티모달 영상 리믹스 | Gemini Omni Flash | Sora 2 | Flow Music |
| 독특한 스타일 버전 | Sora 2 | Veo 3.1 | Higgsfield DOP |
| 움직임/동작 유지 | Kling 3.0 | Seedance 2.0 | Kling Motion Control |
| 레퍼런스 동작 이식 | Kling Motion Control | Kling 3.0 | Kling 01 Edit |
| 일부 수정/수리 | Kling 01 Edit | Edit Video | Mixed Media |
| 빠른 프리비즈 | Veo 3.1 Lite | Seedance 1.5 Pro | Wan 2.7 |
| 긴 시퀀스 연결 | Seedance 2.0 | Kling 3.0 | Cinema Studio |
| 카메라 임팩트 강화 | Higgsfield DOP | Sora 2 | Kling 3.0 |

---

## 7. Common Continuity Bible Format

모든 에이전트는 아래 포맷을 기준으로 작업한다.

```text
=== CONTINUITY BIBLE ===

PROJECT
- Title:
- Format: short / ad / music video / drama / product / experiment
- Target duration:
- Aspect ratio:
- Final delivery model:
- Candidate models:
- Language:
- Output style:

WORLD
- Genre:
- Tone:
- Reality layer:
- Visual grade:
- Color palette:
- Texture:
- Forbidden style drift:

CHARACTERS
- Character ID:
- Role:
- Age range:
- Face type:
- Body type:
- Hair:
- Wardrobe locked:
- Signature detail:
- Emotional baseline:
- Emotional arc:
- Must not change:

PROPS
- Prop ID:
- Description:
- Owner:
- Screen position rule:
- Continuity importance:
- Must not change:

TIME
- Time of day:
- Weather:
- Light source:
- Light direction:
- Time progression:
- Forbidden time drift:

SPACE
- Primary location:
- Layout map in words:
- Camera axis / 180-degree line:
- Foreground:
- Midground:
- Background:
- Entry/exit paths:
- Forbidden spatial drift:

CAMERA LANGUAGE
- Default lens feeling:
- Framing rules:
- Camera movement style:
- Allowed camera moves:
- Forbidden camera moves:
- Shot rhythm:

AUDIO
- Music mood:
- BPM:
- Opening stinger:
- Rhythm layer:
- Diegetic sound:
- Dialogue:
- Ending tail:

HOOK STRATEGY
- 0.0-0.5s:
- 0.5-1.5s:
- 1.5s+:
- Payoff:

NEGATIVE CONSTRAINTS
- No text/subtitles/watermarks/logos unless requested:
- No real-person likeness unless rights are confirmed:
- No face/body defects:
- No wardrobe flicker:
- No time/light drift:
- No prop pop-in/pop-out:
- No AI plastic skin:
- Brief-specific negatives:

REFERENCE ASSETS
- Asset ID:
- Asset type: image / video / audio
- Purpose:
- Use as first frame: yes / no
- Use as motion reference: yes / no
- Use as style reference: yes / no
- Natural-language description:

SEED / REPRODUCIBILITY
- Seed strategy:
- Successful generation ID:
- Reuse rules:
- Fallback if seed unavailable:

ENDING STATE
- Final character pose:
- Final expression:
- Final camera position:
- Final light state:
- Final prop positions:
- Bridge to next segment:
```

---

## 8. Common Shot Schema

각 샷은 아래 형식을 사용한다.

```text
=== SHOT SPEC ===

SHOT ID:
Timecode:
Purpose:
Assigned model:
Fallback model:

Continuity anchors:
- Character:
- Wardrobe:
- Prop:
- Location:
- Light:
- Emotional state:

Action:
- Main action:
- Secondary action:
- Micro gesture:

Camera:
- Framing:
- Angle:
- Movement:
- Lens feeling:
- Blocking:

Audio:
- Music cue:
- Sound effect:
- Dialogue:

Model-specific notes:
- Seedance:
- Kling:
- Veo:
- Omni:
- Sora:

Ending state:
- Pose:
- Expression:
- Camera:
- Prop:
- Light:

Risks:
- Continuity risk:
- Motion risk:
- Face/body risk:
- Prompt overload risk:
```

---

## 9. Standard Workflow

### Step 1. Brief Intake

오케스트라가 사용자 브리프를 받는다.

필수로 확인할 것:

- 영상 길이
- 비율
- 단편/시리즈 여부
- 참고 이미지/영상/오디오 여부
- 최종 사용처

### Step 2. Continuity Bible Lock

사용자 브리프를 공용 `Continuity Bible`로 정리한다.

이 단계 이후에는 캐릭터, 의상, 시간, 공간, 조명, 소품을 함부로 바꾸지 않는다.

### Step 3. Shot Breakdown

오케스트라가 전체 영상을 샷 단위로 나눈다.

각 샷에는 다음을 반드시 둔다.

- 목적
- 시작/끝 상태
- 감정 변화
- 카메라 변화
- 연속성 앵커
- 모델 후보

### Step 4. Readiness Report

오케스트라가 실제 실행 전에 `GO / HOLD / REVISE`를 판단한다.

반드시 기록할 것:

- 장면 기능 / dramatic question
- 성공 조건
- 입력 완성도
- 에셋 준비 상태
- 커버리지 공백
- 권리 / 정책 리스크
- 연속성 리스크

### Step 5. Specialist Reports

각 전문가가 자기 관점의 보고서를 낸다.

- 뮤비 전문가: 곡 구조, 후렴 고정샷, 퍼포먼스 커버리지
- 영화 전문가: dramatic beat, coverage, blocking, editorial logic
- 애니 전문가: 스타일 잠금, 모델 시트, 포즈/실루엣/라인 안정성
- 모델 전문가: 모델 적합성, 실패 리스크, 폴백 경로

### Step 6. Orchestra Execution Plan

오케스트라가 보고서를 모아 실행 계획을 고정한다.

반드시 포함할 것:

- 실행 순서
- 샷 소유자
- 모델/도구
- 의존성
- 프리비즈 승격 기준
- 리페어 vs 재생성 기준
- 최종 납품 게이트

### Step 7. Model Assignment

라우팅 매트릭스를 기준으로 샷마다 담당 모델을 배정한다.

### Step 8. Specialist Prompt Draft

각 전문 에이전트가 자기 샷의 모델별 프롬프트를 작성한다.

중요 규칙:

- 전체 Bible을 다시 쓰지 않는다.
- 자기 샷의 입력/출력 상태만 정확히 쓴다.
- 모델별 한계를 명시한다.

### Step 9. Orchestrator Arbitration

오케스트라가 모든 샷을 검토한다.

확인할 것:

- 캐릭터가 바뀌지 않았는가
- 조명이 튀지 않는가
- 소품이 갑자기 생기거나 사라지지 않는가
- 감정선이 뒤집히지 않는가
- 모델별 프롬프트가 서로 충돌하지 않는가

### Step 10. Previz

저비용/빠른 모델로 먼저 테스트한다.

추천:

- `Veo 3.1 Lite`
- `Seedance 1.5 Pro`
- `Wan 2.7`

### Step 11. Hero Generation

좋은 샷만 메인 모델로 승격한다.

추천:

- `Seedance 2.0`
- `Kling 3.0`
- `Google Veo 3.1`
- `Sora 2`

### Step 12. Repair / Motion / DOP

문제가 있는 샷만 도구 레이어로 보낸다.

- 움직임 문제: `Kling Motion Control`
- 일부 수정: `Kling 01 Edit`
- 카메라/VFX 약함: `Higgsfield DOP`
- 편집/조립: `Mixed Media` 또는 `Edit Video`

### Step 13. Final Delivery Gate

최종 납품 전 오케스트라가 아래를 승인한다.

- 권리 / 정책 통과
- 후렴/리프레인 매칭 통과
- 마스터 / 소셜 리프레임 통과
- 남은 WARN 수용 여부
- 최종 조립 순서 통과

### Step 14. Final Audit

최종 출력 전 `Continuity Audit`을 수행한다.

---

## 10. Continuity Audit Checklist

```text
=== CONTINUITY AUDIT ===

Character:
- Same face type preserved?
- Same body type preserved?
- Same hair preserved?
- Same wardrobe preserved?
- Signature detail visible when needed?

World:
- Same genre and tone preserved?
- Same color palette preserved?
- No style drift between shots?

Time / Light:
- Time of day consistent?
- Weather consistent?
- Light direction consistent?
- No sudden day/night jump?

Space:
- Location layout consistent?
- 180-degree line respected?
- Character screen direction preserved?
- Props remain in plausible positions?

Action:
- Shot starts from previous ending state?
- Motion direction consistent?
- Emotional progression justified?

Audio:
- Opening stinger present?
- Rhythm layer consistent?
- Dialogue does not contradict action?
- Ending tail supports next segment?

Prompt:
- Not overloaded?
- No contradictory instructions?
- Negative constraints included?
- Model-specific controls separated?

Routing:
- Assigned model matches shot purpose?
- Fallback model selected?
- Repair path defined?
```

---

## 11. Orchestrator Prompt Template

```text
You are the Orchestrator / Showrunner for an AI video production pipeline.

Your task:
1. Interpret the user's creative brief.
2. Build and lock a Continuity Bible.
3. Break the video into shot specs.
4. Assign each shot to the best available model or tool.
5. Route only necessary work to specialist agents.
6. Merge specialist outputs without continuity conflicts.
7. Produce the final model-ready prompt packet.

Available primary agents:
- Seedance Director
- Kling Director
- Veo Director
- Omni Director
- Sora Director
- Animation Camera Director

Available tool layer:
- Kling Motion Control
- Kling 01 Edit
- Higgsfield DOP
- Cinema Studio
- Mixed Media / Edit Video

Available fallback layer:
- Veo 3.1 Lite
- Seedance 1.5 Pro
- Wan 2.7
- Minimax Hailuo 2.3

Hard rules:
- Maintain one canonical Continuity Bible.
- Do not let specialist agents invent new canon.
- Do not overuse agents when a single model is enough.
- Prefer previsualization before expensive hero generation.
- Repair specific failed shots instead of regenerating the whole sequence.
- Always provide a fallback path.
```

---

## 12. Specialist Handoff Template

```text
=== SPECIALIST HANDOFF ===

To:
Assigned shot IDs:
Goal:
Model/tool:

Use only this Continuity Bible:
[paste locked Bible]

Use these shot specs:
[paste assigned shot specs]

Your task:
- Optimize only the assigned shots.
- Keep all locked continuity facts unchanged.
- Produce model-ready prompts.
- Include any model-specific warnings.
- Include ending state for the next shot.

Do not:
- Rewrite the whole story.
- Change character design.
- Change wardrobe.
- Change time of day or location unless explicitly instructed.
- Add new props unless approved by the Orchestrator.
```

---

## 13. Output Packet Format

```text
=== FINAL VIDEO PROMPT PACKET ===

1. Continuity Bible
[locked project bible]

2. Readiness Report
[GO / HOLD / REVISE plus blockers]

3. Specialist Reports
[creative + model specialist reports]

4. Orchestra Execution Plan
[execution order, ownership, gates]

5. Shot Timeline
[shot-by-shot timeline]

6. Model Assignment
[shot -> model/tool -> reason -> fallback]

7. Model-Ready Prompts

Seedance 2.0:
[prompts]

Kling 3.0:
[prompts]

Google Veo 3.1:
[prompts]

Gemini Omni Flash:
[prompts]

Sora 2:
[prompts]

Tool Layer:
[motion/edit/dop instructions]

8. Execution Gates
[gate checklist]

9. Continuity Audit
[checklist results]

10. Next Action
[what the user should generate first]
```

---

## 14. Anti-Patterns

피해야 할 것:

- 모든 모델에 같은 프롬프트를 그대로 던지기
- 에이전트마다 다른 캐릭터 설명을 만들기
- 각 에이전트가 전체 영상을 다시 쓰기
- 결과물을 단순히 이어 붙이기
- 한 샷에 너무 많은 사건을 넣기
- 문제가 있는 1개 샷 때문에 전체 영상을 재생성하기
- Motion Control, Edit, DOP를 메인 생성기처럼 취급하기
- 매번 모든 에이전트를 호출하기

---

## 15. Minimal Mode

간단한 요청일 때는 전체 오케스트라를 돌리지 않는다.

사용 조건:

- 단일 5-10초 영상
- 참고 에셋 없음
- 시리즈 아님
- 엄격한 캐릭터 연속성 필요 없음

흐름:

```text
Brief -> Orchestrator -> one best model -> final prompt
```

추천 모델:

- 상업적 숏폼: Seedance 2.0
- 강한 단일 컷: Veo 3.1
- 움직임 중심: Kling 3.0
- 스타일 실험: Sora 2

---

## 16. Full Orchestra Mode

복잡한 요청일 때만 전체 오케스트라를 돌린다.

사용 조건:

- 15초 이상
- 여러 샷/세그먼트
- 참고 이미지/영상 있음
- 같은 캐릭터 반복 등장
- 시리즈물
- 오디오/대사/리듬 중요
- 수정/편집까지 포함

흐름:

```text
Brief
-> Continuity Bible
-> Readiness Report
-> Specialist Reports
-> Orchestra Execution Plan
-> Shot Specs
-> Model Assignment
-> Specialist Drafts
-> Orchestrator Arbitration
-> Previz
-> Hero Generation
-> Repair / Motion / DOP
-> Final Assembly
-> Audit
```

---

## 17. Practical First Version

처음 구현할 때는 아래 3개만 있어도 충분하다.

1. `Orchestrator`
2. `Seedance Director`
3. `Kling Director`

그다음 추가 순서:

1. `Veo Director`
2. `Sora Director`
3. `Omni Director`
4. `Animation Camera Director`
5. `Tool Layer`
6. `Fallback Layer`

이 순서가 좋은 이유:

- Seedance와 Kling이 현재 연속성/멀티샷/움직임 쪽에서 가장 직접적으로 쓰인다.
- Veo와 Sora는 고품질/스타일 차별화 샷으로 나중에 붙여도 된다.
- Omni는 대화형 리믹스나 소스 푸티지 변환이 필요할 때 붙이면 된다.
- Animation Camera Director는 애니메이션/2.5D 카메라 설계가 실제 병목일 때 추가하는 것이 효율적이다.
- Tool Layer는 실제 실패 패턴을 본 뒤 붙이는 것이 더 정확하다.

---

## 18. One-Line Rule

```text
오케스트라는 모델을 많이 부르는 시스템이 아니라, 같은 Continuity Bible을 지키면서 가장 적은 호출로 가장 안정적인 결과를 만드는 시스템이다.
```
