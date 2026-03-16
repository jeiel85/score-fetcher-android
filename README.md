# 🎵 찬양 악보 매니저 (Praise Score Manager) - Android

> **웹 기반 찬양 콘티 관리 시스템을 Capacitor를 통해 안드로이드 네이티브 앱으로 포팅한 프로젝트입니다.**

![App Icon](icon.jpg) ## 🌟 프로젝트 개요
기존에 VB6 및 C# 환경에서 관리하던 찬양 악보 데이터를 모바일 환경에서도 손쉽게 조회하고, 찬양팀원들에게 공유하기 위해 제작되었습니다. 안드로이드 네이티브 기능을 활용하여 **화면 꺼짐 방지**, **다중 파일 공유**, **오프라인 캐시 저장** 등의 기능을 제공합니다.

---

## ✨ 주요 기능

* **🔍 악보 자동 검색:** 곡 번호와 제목을 입력하면 서버에서 악보 이미지를 자동으로 매칭하여 리스트업합니다.
* **📲 다중 악보 공유:** 선택한 여러 장의 악보를 하나의 묶음(File Bundle)으로 카카오톡 등 외부 앱에 즉시 공유할 수 있습니다.
* **💡 화면 꺼짐 방지(WakeLock):** 예배 및 연습 중 화면이 꺼지지 않도록 네이티브 WakeLock 기능을 지원합니다.
* **🕒 콘티 이력 관리:** Firebase Realtime Database를 연동하여 과거에 생성했던 콘티를 언제든 불러올 수 있습니다.
* **🎨 네이티브 최적화:** 안드로이드 12 이상의 Adaptive Icon 및 Splash Screen이 적용되었습니다.

---

## 🛠 Tech Stack

* **Frontend:** HTML5, CSS3, JavaScript (Vanilla JS)
* **Hybrid Framework:** [Capacitor JS](https://capacitorjs.com/)
* **Database:** Firebase Realtime Database
* **Native Tools:** Android Studio (Java), Capacitor Share/Filesystem/WakeLock Plugins

---

## 🚀 개발 및 포팅 과정 (15년 경력 개발자의 노트)

1.  **웹 앱 고도화:** 기존 웹 소스를 모바일 뷰포트 및 세이프 에어리어(Safe Area)에 맞게 리뉴얼.
2.  **Capacitor 도입:** `npx cap add android`를 통해 하이브리드 앱 환경 구축.
3.  **네이티브 기능 연동:** * `@capacitor/share`를 활용한 다중 이미지 전송 로직 구현.
    * `Filesystem` API를 사용하여 웹상의 이미지를 네이티브 임시 경로(CACHE)로 변환 후 공유.
4.  **UI/UX 개선:** 안드로이드 물리 뒤로가기 버튼 처리 및 배포 전 공유 목록 확인 팝업 추가.

---

## 📦 설치 및 실행 방법

### 사전 요구 사항
* Node.js & npm
* Android Studio

### 빌드 순서
```bash
# 의존성 설치
npm install

# 웹 소스 빌드 및 안드로이드 프로젝트 동기화
npx cap copy android
npx cap sync android

# 안드로이드 프로젝트 열기
npx cap open android
