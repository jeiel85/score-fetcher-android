# 🎵 찬양 악보 매니저 (Praise Score Manager) - Android Edition

![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Capacitor](https://img.shields.io/badge/Capacitor-119EFF?style=for-the-badge&logo=capacitor&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)

> **기존 웹 기반의 찬양 콘티 관리 시스템을 하이브리드 앱 환경으로 성공적으로 포팅한 프로젝트입니다.**

<p align="center">
  <img src="icon.png" alt="App Icon" width="150"/>
</p>

## 🌟 프로젝트 개요
예배 및 찬양팀 연습 환경에서 악보를 빠르고 직관적으로 관리하기 위해 개발되었습니다. 웹 브라우저 환경에서 발생하던 개별 파일 다운로드의 불편함을 개선하고, 안드로이드 네이티브(Native) 기능을 적극 활용하여 실사용에 최적화된 사용자 경험(UX)을 제공합니다.

---

## ✨ 주요 기능 (Key Features)
* **🔍 악보 자동 매칭 및 조회:** 곡 번호와 제목 입력 시 서버 내 악보 이미지를 자동으로 찾아 매칭합니다.
* **📲 네이티브 다중 공유 (Multi-file Share):** 여러 장의 악보 이미지를 Base64 인코딩 후 기기의 임시 저장소(CACHE) 파일로 변환하여, 카카오톡 등 외부 앱에 한 번에 묶어 전송합니다.
* **👀 공유 전 사전 검토 팝업:** 전송 전, 사용자가 선택한 곡 리스트와 번호를 명확히 표시하여 전송 오류를 방지합니다.
* **💡 화면 꺼짐 방지 (WakeLock):** 예배 진행 중 기기 화면이 꺼지는 것을 방지하는 네이티브 디스플레이 제어를 지원합니다.
* **🕒 콘티 이력 관리 (History):** Firebase Realtime DB 기반으로 과거 콘티 내역을 안전하게 저장하고 원클릭으로 로드합니다.
* **🔙 물리 버튼 대응:** 안드로이드 고유의 하드웨어 '뒤로 가기' 버튼을 감지하여 모달 제어 및 앱 종료 로직을 처리합니다.

---

## 🛠 기술 스택 (Tech Stack)
* **Frontend:** HTML5, CSS3, Vanilla JavaScript
* **Hybrid Framework:** [Capacitor](https://capacitorjs.com/)
* **Native Access (Plugins):** `@capacitor/share`, `@capacitor/filesystem`
* **Database:** Firebase Realtime Database

---

## 🚀 포팅 및 아키텍처 노트 (Developer's Note)
기존 레거시 윈도우 프로그래밍(VB6, C# 등) 및 웹 환경의 한계를 극복하고, 현대적인 하이브리드 모바일 아키텍처로 성공적으로 전환했습니다. 

웹 환경의 단순 URL/Blob 방식에서 벗어나, Capacitor의 `Filesystem`과 `Share` 플러그인을 결합했습니다. 이를 통해 **가상의 파일 시스템(임시 저장 구역)을 거쳐 안드로이드 네이티브 공유 시트(Share Sheet)로 파일 객체를 안전하게 이관**하는 데이터 파이프라인을 구축한 것이 본 프로젝트의 핵심입니다.

---

## 📦 설치 및 빌드 방법 (Getting Started)

```bash
# 1. 패키지 및 플러그인 설치
npm install
npm install @capacitor/share @capacitor/filesystem

# 2. 웹 소스 코드를 안드로이드 프로젝트로 복사
npx cap copy android

# 3. Capacitor 네이티브 설정 동기화
npx cap sync android

# 4. 안드로이드 스튜디오에서 프로젝트 열기 및 APK 빌드
npx cap open android
