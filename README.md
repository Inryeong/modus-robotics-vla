# 위키독스 운영 및 작성 가이드 v0.1


<aside>

## 📌 모두의 로보틱스 랩 활동을 통해 얻은 지식을 자산화해요.

</aside>

---

Last Updated 2026년 01월 21일 

---

## 목차
- [1. **운영 구조 (Roles & Rules)**](#1-운영-구조-roles--rules)
  - [1-1. **역할**](#1-1-역할)
  - [1-2. **핵심 규칙(필수)**](#1-2-핵심-규칙필수)
- [2. **Repo 구조 & 파일 규칙**](#2-repo-구조--파일-규칙)
  - [2-1. **기본 구조**](#2-1-기본-구조)
  - [2-2. **파일 설명**](#2-2-파일-설명)
  - [2-3. **파일/제목 네이밍 규칙**](#2-3-파일제목-네이밍-규칙)
- [3. **협업 전략 (Branch / Commit / PR)**](#3-협업-전략-branch--commit--pr)
  - [3-1. **브렌치 네이밍**](#3-1-브렌치-네이밍)
  - [3-2. **커밋 메시지 컨벤션**](#3-2-커밋-메시지-컨벤션)
  - [3-3. **PR 규칙 & 리뷰 플로우**](#3-3-pr-규칙--리뷰-플로우)
- [4. **작성 규칙(TOC/이미지)**](#4-작성-규칙toc이미지)
  - [4-1. **TOC 기본 형식**](#4-1-toc-기본-형식)
  - [4-2. **TOC 올바른 작성 예시**](#4-2-toc-올바른-작성-예시)
  - [4-3. **TOC 들여쓰기 규칙**](#4-3-toc-들여쓰기-규칙)
  - [4-4. **이미지 파일 저장**](#4-4-이미지-파일-저장)
  - [4-5. **마크다운에서 이미지 참조**](#4-5-마크다운에서-이미지-참조)
  - [4-6. **동기화 시 자동 변환**](#4-6-동기화-시-자동-변환)
  - [4-7. **주의사항**](#4-7-주의사항)
- [5. **Quick Start**](#5-quick-start)
  - [5-1. **리포지토리 클론**](#5-1-리포지토리-클론)
  - [5-2. **브렌치 생성/커밋/푸시 & PR생성**](#5-2-브렌치-생성커밋푸시--pr생성)

---


## 1. **운영 구조 (Roles & Rules)**

<aside>
✅ 문서/목차/이미지는 GitHub에서 관리하고, `main` 브랜치 머지 후 위키독스에 반영됩니다.
</aside>

### **1-1. 역할**

- **리뷰어**: TOC/머지/최종 품질 관리
- **컨트리뷰터**: 담당 파트 작성 → PR 제출 → 피드백 반영

### **1-2. 핵심 규칙(필수)**

- 컨트리뷰터는 **main 직접 push 금지**
- **TOC.md는 리뷰어만 수정**
- 하나의 PR = **한 페이지(하나의 글/논문/실습 등)**

---

## **2. Repo 구조 & 파일 규칙**

### 2-1. **기본 구조**

```
my-book/
├── README.md
├── TOC.md
├── assets/
└── pages/
    ├── basic/
    ├── paper/
    └── lab/
```

### **2-2. 파일 설명**

| 파일 | 설명 |
| --- | --- |
| `README.md` | 책의 요약 설명. 첫 번째 제목(#)을 제외한 내용이 책 요약으로 사용됩니다. |
| `TOC.md` | 목차 구조. 페이지의 계층(부모-자식) 관계를 정의합니다. |
| `pages/` | 실제 페이지 콘텐츠가 저장되는 폴더입니다. |
| `assets/` | 이미지 파일을 저장하는 폴더입니다. |

### 2-3. 파일/제목 네이밍 규칙

- 파일명: **번호-페이지제목**
    - pages/lab/01-lerobot-install.md
- 페이지 제목: **번호 포함 권장**
    - # 01. LeRobot 설치

## **3. 협업 전략 (Branch / Commit / PR)**

### 3-1. 브렌치 네이밍

```
# 형식
<type>/<scope>-<short-topic>

# scope 예시
	•	paper: openvla, rt2, saycan, survey …
	•	basic: transformer, tokenization … 선수 지식이 필요한 용어 및 이론 개념 (딥하게 X)
	•	lab: install, dataset, train, eval, troubleshooting

# 브랜치 네이밍 예시
	•	paper/openvla-core-summary
	•	basic/terms-vla
	•	lab/install-lerobot
	•	fix/paper-links
	•	docs/contributing-template
```

### 3-2. 커밋 메시지 컨벤션

- 한 커밋엔 한 type만, summary는 한글도 OK

```
# 형식
<type>(<scope>): <summary>

# 커밋 메세지 예시
	•	paper(openvla): add key ideas and limitations
	•	lab(install): add LeRobot setup steps for Ubuntu 22.04
	•	fix(openvla): correct typos and update arXiv link
	•	assets(install): add setup screenshot
```

### 3-3. PR 규칙 **& 리뷰 플로우**

- PR = 한 페이지(한 논문/한 실습/한 글)
- 리뷰 flow

```
**컨트리뷰터** PR 생성 및 체크리스트 완료
-> **리뷰어** 검토/코멘트
-> **컨트리뷰터** 수정 반영
-> **리뷰어** Squash merge
```

- PR 체크리스트(필수 점검)
    - 한 주제/한 페이지 단위
    - main 직접 push X
    - assets에 저장 + 상대경로 링크
    - 링크 깨짐 없음
    - (새 페이지) TOC 수정 X + TOC 추가 요청 코멘트

---

## **4. 작성 규칙(TOC/이미지)**

TOC.md 파일은 책의 목차 구조를 정의합니다. 위키독스는 이 파일을 파싱하여 페이지의 계층 구조를 생성합니다.

<aside>
✅ 위키독스는 페이지를 제목 알파벳순으로 자동 정렬합니다. </br>
원하는 순서를 유지하려면 제목에 번호를 붙이세요.
</aside>

### **4-1. TOC 기본 형식**

```
# 목차

- [페이지 제목](pages/파일명.md)
  - [하위 페이지 제목](pages/하위파일명.md)
```

### **4-2. TOC 올바른 작성 예시**

```
# 목차

- [01. 시작하기](pages/01-getting-started.md)
  - [01-1. 설치하기](pages/01-1-install.md)
  - [01-2. 환경설정](pages/01-2-config.md)
- [02. 기본 문법](pages/02-basics.md)
  - [02-1. 변수](pages/02-1-variables.md)
  - [02-2. 자료형](pages/02-2-datatypes.md)
- [03. 심화 학습](pages/03-advanced.md)
```

### **4-3. TOC 들여쓰기 규칙**

- **2칸 들여쓰기** = 하위 페이지 (자식)
- **4칸 들여쓰기** = 하위의 하위 페이지 (손자)

```
- [01. 부모 페이지](pages/01-parent.md)
  - [01-1. 자식 페이지](pages/01-1-child.md)
    - [01-1-1. 손자 페이지](pages/01-1-1-grandchild.md)
```

### **4-4. 이미지 파일 저장**

이미지 파일은 `assets/` 폴더에 저장합니다:

```
my-book/
├── assets/
│   ├── screenshot.png
│   └── diagram.jpg
└── pages/
    └── 01-getting-started.md

```

### **4-5. 마크다운에서 이미지 참조**

상대 경로를 사용하여 이미지를 참조합니다:

```
![스크린샷](../assets/screenshot.png)

![다이어그램](../assets/diagram.jpg)

```

### **4-6. 동기화 시 자동 변환**

깃허브에서 위키독스로 동기화될 때, 이미지 경로가 자동으로 위키독스 경로로 변환됩니다:

```
# 깃허브 원본
![스크린샷](../assets/screenshot.png)

# 위키독스 변환 후
![스크린샷](https://static.wikidocs.net/images/page/123/screenshot.png)
```

### **4-7. 주의사항**

- 외부 URL 이미지(`https://...`)는 변환되지 않고 그대로 유지됩니다.
- 이미지 파일명에 한글이나 특수문자는 피하는 것이 좋습니다.
- 권장 이미지 형식: PNG, JPG, GIF

---

## **5. Quick Start**

깃허브 연동 책은 **로컬 PC에서 작업**하고 **git push**로 배포하는 방식을 권장합니다.

- 워크플로우
    - 브랜치 생성 → 페이지 작성 → 커밋/푸시 → PR 생성 → 리뷰 → Squash merge → 위키독스 동기화

![](https://static.wikidocs.net/images/page/321336/workflow.png)

### **5-1. 리포지토리 클론**

```bash
git clone https://github.com/Inryeong/modus-robotics-vla.git
cd <repo>
```

### **5-2. 브렌치 생성/커밋/푸시 & PR생성**

```bash
## 예시
# 1) main 최신화
git checkout main
git pull origin main

# 2) 브랜치 생성
git checkout -b lab/install-ubuntu22

# 3) 작업(예: 파일/이미지 추가)
# pages/lab/01-lerobot-install.md 작성
# assets/lerobot-install.png 추가

# 4) 변경 확인
git status

# 5) 스테이징 + 커밋
git add pages/lab/01-lerobot-install.md assets/lerobot-install.png
git commit -m "lab(install): add LeRobot setup steps for Ubuntu 22.04"

# 6) 푸시
git push -u origin lab/install-ubuntu22
```

---
