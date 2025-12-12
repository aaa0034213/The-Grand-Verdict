# 📂 프로젝트 컨텍스트 (Project Context)

이 문서는 **진실의 법정 (The Truth's Court)** 프로젝트의 핵심 구조, 데이터 명세, 제약 사항 및 향후 개선 방향을 기술합니다.

## 1. 🏗️ 핵심 파일 구조 (Core File Structure)

본 프로젝트는 배포 편의성을 위해 **단일 파일 아키텍처 (Single File Architecture)**를 채택했습니다.

```
/
├── index.html        # 핵심 게임 파일 (HTML + CSS + JS)
├── README.md         # 프로젝트 소개 및 실행 가이드
├── CONTEXT.md        # 기술적 컨텍스트 및 명세서
└── .gemini/          # (개발 환경 설정 및 아티팩트 저장소)
```

*   **index.html**: 게임의 모든 로직, 스타일, UI 구조가 포함되어 있습니다.
    *   `<head>`: Google Fonts 로드 (`Nanum Myeongjo`, `Gowun Batang`) 및 CSS 스타일 정의.
    *   `<body>`: 게임 UI (타이틀, 법정 패널, 모달 등) 마크업.
    *   `<script>`: 게임 데이터(`CASES`), 상태 관리(`state`), 오디오(`Web Audio API`), 로직 함수.

---

## 2. 📊 데이터 명세 (Data Specifications)

게임의 시나리오는 자바스크립트 `CASES` 배열에 정의되어 있습니다. 각 사건(Case)은 다음 스키마를 따릅니다.

### Case Object Schema

```javascript
{
    id: Number,             // 사건 번호 (1부터 시작)
    title: String,          // 사건 제목 (예: "새벽의 그림자")
    intro: String,          // 사건 도입부 설명 (모달 팝업용)
    witness: {
        name: String,       // 증인 이름 및 나이
        avatar: String,     // 증인 아바타 (이모지 또는 텍스트)
        text: String        // 핵심 거짓 증언 (거짓말이 포함된 문장)
    },
    keywords: Array,        // 증언에서 추출 가능한 검색 키워드 목록
    correct_id: Number,     // 거짓을 입증하는 정답 증거(Evidence)의 ID
    hint: String,           // 힌트 시스템에서 제공할 텍스트
    db: Array<Evidence>     // 검색 가능한 증거 데이터베이스
}
```

### Evidence Object Schema (db)

```javascript
{
    id: Number,             // 증거 ID (101, 102 등)
    title: String,          // 증거 이름 (예: "CCTV 영상")
    content: String,        // 증거 내용 설명
    keywords: Array         // 검색 매칭을 위한 태그 목록
}
```

---

## 3. ⚠️ 기술적 제약 사항 (Technical Constraints)

1.  **Single File Policy**:
    *   모든 코드는 `index.html` 내부에 존재해야 합니다.
    *   외부 이미지(jpg, png)나 오디오 파일(mp3)을 로드하지 않습니다. (Base64 인코딩조차 지양)
    *   모든 시각 효과는 CSS/SVG로, 청각 효과는 Web Audio API로 실시간 합성해야 합니다.

2.  **External Dependencies**:
    *   런타임 라이브러리(jQuery, React 등) 사용 금지.
    *   유일한 외부 의존성은 Google Fonts(CDN)입니다.

3.  **Browser Compatibility**:
    *   Web Audio API (`AudioContext`) 및 Web Speech API (`speechSynthesis`)를 지원하는 모던 브라우저(Chrome, Edge 등)가 필요합니다.
    *   Internet Explorer는 지원하지 않습니다.

---

## 4. 🚀 개선 사항 (Improvements)

향후 프로젝트 고도화를 위해 고려할 수 있는 사항들입니다.

*   **Data Persistence**:
    *   현재는 새로고침 시 진행 상황이 초기화됩니다. `localStorage`를 활용하여 클리어한 사건 정보를 저장하는 기능이 필요할 수 있습니다.
*   **Case Generator Tool**:
    *   JSON 포맷의 사건 데이터를 쉽게 생성할 수 있는 별도의 GUI 도구 또는 스크립트.
*   **Mobile Optimization**:
    *   현재 UI는 데스크탑 가로 모드에 최적화되어 있습니다. 모바일 세로 모드를 위한 반응형 레이아웃(미디어 쿼리) 보강이 필요합니다.
*   **Accessibility (a11y)**:
    *   스크린 리더 사용자를 위한 ARIA 레이블 보강 및 키보드 내비게이션 최적화.
