# 🕵️‍♂️ 진실의 법정 (The Truth's Court)

> **"모든 거짓말에는 모순이 존재한다."**

![Premium Courtroom Style](https://img.shields.io/badge/Style-Premium%20Courtroom-8B4513?style=for-the-badge)
![Tech Stack](https://img.shields.io/badge/Tech-HTML5_JS_CSS3-ff0055?style=for-the-badge)

## 📌 개요 및 목적 (Overview & Purpose)

**진실의 법정**은 플레이어가 법정의 검사/탐정이 되어 증인의 증언 속에 숨겨진 거짓을 밝혀내는 **싱글 파일 웹 추리 게임**입니다.
이 프로젝트의 주요 목적은 다음과 같습니다:

1.  **몰입형 추리 경험**: 단순한 텍스트 나열이 아닌, 검색(RAG 시뮬레이션)과 추리, 이의 제기를 통해 능동적으로 사건을 해결하는 경험 제공.
2.  **프리미엄 웹 경험 부각**: 외부 라이브러리 없이 순수 로직만으로 고품질의 비주얼(Classic Courtroom Theme)과 인터랙션을 구현.
3.  **접근성 및 배포 용이성**: `index.html` 단일 파일로 구성되어 별도의 서버나 설치 없이 즉시 실행 가능.

---

## 🛠️ 기술 스택 (Tech Stack)

이 프로젝트는 100% **Vanilla Web Technologies**로 제작되었습니다.

*   **HTML5**: 시맨틱 마크업 및 게임 구조 정의.
*   **CSS3**:
    *   **Premium Courtroom Theme**: 고해상도 나무 질감, 금박 장식, 가죽 텍스처 등을 CSS Gradient만으로 구현.
    *   **Animations**: 타자기 효과(Typewriter), 도장 찍기(Stamp), 화면 흔들림, 종이 질감 효과 등.
    *   **Flexbox/Grid**: 반응형 레이아웃 구성.
*   **JavaScript (ES6+)**:
    *   **Game Logic**: 상태 관리, 시나리오 진행, 체력 시스템.
    *   **Web Audio API**: 효과음(타자, 종이, 쿵, 팡파레 등) 실시간 합성 (No external assets).
    *   **Web Speech API**: 증언 텍스트 음성 변환(TTS) 기능.

---

## 📦 설치 방법 (Installation)

이 게임은 **설치가 필요 없습니다.**
단일 파일 형태이므로 소스 코드를 다운로드하거나 복사하기만 하면 됩니다.

1.  이 저장소를 클론(Clone)하거나 다운로드합니다.
2.  `index.html` 파일이 있는지 확인합니다.

---

## � 실행 방법 (How to Run)

웹 브라우저가 설치된 모든 환경(PC, 태블릿 등)에서 실행 가능합니다.

1.  `index.html` 파일을 **더블 클릭**합니다.
2.  또는 파일을 브라우저(Chrome, Edge, Safari 등) 창으로 **드래그 앤 드롭**합니다.
3.  (권장) 몰입감을 위해 **F11 키**를 눌러 전체 화면으로 플레이하세요.

---

## ✨ 제공 기능 (Key Features)

### 1. 🔍 증거 검색 시스템 (RAG Simulation)
*   증언에서 의심스러운 키워드(예: "치킨", "CCTV")를 입력하면 관련 증거(데이터베이스)를 검색하여 보여줍니다.
*   실제 수사 기록을 뒤지는 듯한 경험을 제공합니다.

### 2. 🔨 이의 제기 (Objection!)
*   모순되는 증거를 선택하고 "이의 제기!" 버튼을 누르면 판결이 내려집니다.
*   **정답**: "SUSTAINED" 도장과 함께 다음 사건으로 진행.
*   **오답**: 체력(❤️) 감소 및 화면 흔들림 효과.

### 3. � 오디오 및 음성 (Audio & Voice)
*   **Sounx FX**: 클릭, 타자 치는 소리, 책 넘기는 소리, 승리 효과음 등이 Web Audio API로 구현되어 있습니다.
*   **TTS (Voice)**: "🔊 증언 듣기" 버튼을 클릭하면 한국어 음성으로 증언을 읽어줍니다.

### 4. 🎨 프리미엄 비주얼 (Visuals)
*   **Classic Courtroom**: 묵직한 우드 톤과 금색 포인트로 법정의 엄숙함을 표현.
*   **Photo Cards**: 증인 아바타를 폴라로이드 사진 스타일과 머그샷 배경으로 연출.
*   **Mute & Hints**: 음소거 기능과 힌트 시스템으로 사용자 편의성 제공.
*   **Victory Screen**: 모든 사건 해결 시 화려한 컨페티(꽃가루) 효과와 함께 명탐정 인증서 수여.

### 5. 📚 다양한 시나리오 (7 Cases)
*   초급(알리바이 모순)부터 고급(물리학적 모순, 의학적 지식)까지 난이도별 7개의 에피소드 수록.

---
*Created by Antigravity*
