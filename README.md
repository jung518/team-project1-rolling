# 🎉 Rolling - 디지털 롤링페이퍼 서비스

**Rolling**은 친구, 가족, 동료에게 따뜻한 메시지를 카드 형태로 모아보는 디지털 롤링페이퍼 서비스입니다. 사용자는 메시지를 작성하고, 이를 롤링페이퍼 형태로 공유할 수 있습니다.  

---

## 📅 프로젝트 개요

- **진행 기간**: 2025.09.24 ~ 2025.10.15  
- **참여 인원**: 프론트엔드 5명  
- **역할**: 상세 페이지 개발, 공통 컴포넌트 개발 (Input, PlusButton, ArrowButton)

---

## 🛠 기술 스택

| 구분       | 기술 |
|------------|------|
| 프레임워크 | React |
| 상태 관리  | useState, useEffect, useCallback |
| API 통신   | Axios |
| 스타일링   | CSS Module |
| 협업 도구  | GitHub, Notion, Discord |

---

## 🙋‍♀️ 담당한 기능 및 역할

## 📌 `/post/{id}` 상세 페이지 기능
`MainPages.tsx / MainPages.css`

해당 페이지는 특정 롤링페이퍼 수신자(recipient)의 상세 정보와 메시지 목록을 보여주는 페이지입니다.  
React, TypeScript, Axios, Infinite Scroll 등을 활용하여 구현했습니다.


- **Axios를 이용한 비동기 데이터 요청**
  - GET /recipients/{id}/로 대상자(recipient) 정보 조회
  - GET /recipients/{id}/messages/로 메시지 목록 조회

- **메시지 데이터 매핑 및 렌더링**
  - 응답 데이터를 가공하여 카드 형태로 표시
  - 작성자, 작성일, 관계 배지, 프로필 이미지 등 UI에 필요한 정보 추출 및 변환

- **무한 스크롤(Infinite Scroll) 구현**
  - 초기 메시지 6개 로드 후 스크롤 시 다음 메시지 자동 로딩
  - 모든 메시지를 불러온 경우 로딩 종료 처리

- **카드 클릭 시 모달(MessageModal) 팝업**
  - 메시지 상세 내용을 모달 형태로 보여주며, 닫기 기능 포함

- **카드 클릭 시 메시지 작성 페이지로 이동**
  - /post/{id}/message 경로로 이동하여 새로운 메시지 작성 가능

- **배경 설정**
  - recipient 데이터에 따라 배경 이미지 또는 배경색 적용
  - 반응형 CSS 처리로 다양한 디바이스에 대응

- **유틸 함수 활용**
  - 날짜 포맷 처리 (formatDate)
  - 관계 정보 → 배지 타입으로 매핑 (relationshipToBadge)
    
---

### ➕ 2. `PlusButton` 공통 컴포넌트
`PlusButton.tsx / PlusButton.css`

- size props로 다양한 크기 지원 (px 단위)
- onClick props로 외부 이벤트 전달
- className 및 기타 props로 커스터마이징 가능
- CSS 변수(--plus-button-size) 사용해 유연한 크기 조절 구현

---

### ➡️ 3. `ArrowButton` 공통 컴포넌트
`ArrowButton.tsx / ArrowButton.css`
- direction props (left, right)로 방향 전환
- size props (small, default, large)로 크기 조절
- SVG 아이콘 회전 처리 (left 방향 시 rotate-180)
- 조건부 클래스 조합으로 유지보수 용이한 구조 설계

---

### ⌨️ 4. `Input` 공통 컴포넌트
`Input.tsx / Input.css`
- 내부 상태로 입력값, 에러 메시지 관리 (useState)
- 숫자 입력 시 에러 메시지 출력 (임시 검증)
- 기본 input 속성 모두 지원 (ComponentPropsWithoutRef<"input">)
- 상태에 따라 에러 스타일 동적 적용

---

## 🔗 배포 링크

https://codeit-6team-rolling.vercel.app

---

## 🧠 프로젝트 회고 및 개발 블로그

[React로 공용 컴포넌트 설계하며 배운 협업의 힘](https://blog.naver.com/jwy030518/224043294031)



## 🚀 실행 방법

```bash
# 저장소 클론
git clone https://github.com/jung518/portfolio-projects.git

# 디렉토리 이동
cd portfolio-projects

# 패키지 설치
npm install

