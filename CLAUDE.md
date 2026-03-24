# 디자인 스튜디오 홈페이지 — 프로젝트 메모 (CLAUDE.md)

## 프로젝트 개요

미리캔버스 디자인허브 기여자(@somangpli)의 서비스를 소개하는 **원페이지 홈페이지**.  
방문자가 상품을 확인하고 클릭 한 번으로 비즈하우스 크리에이터 샵으로 이동할 수 있도록 구성.

---

## 크리에이터 정보

| 항목 | 내용 |
|---|---|
| 플랫폼 | 미리캔버스 디자인허브 기여자 |
| 샵 주소 | https://www.bizhows.com/v/creator/@somangpli |
| 상품 카테고리 | 요소 / 배경 / 템플릿 / 상품샵 |

---

## 디자인 방향

| 항목 | 결정 내용 |
|---|---|
| 분위기 | 따뜻하고 신뢰감 있는 느낌 |
| 색상 계열 | 베이지 톤 |
| 주 색상 | `#F7F2EA` (배경), `#B8845A` (액센트), `#2E231A` (다크) |
| 폰트 | Cormorant Garamond (제목), DM Serif Display (로고), Noto Sans KR (본문) |

---

## 페이지 구성 (섹션 순서)

1. **Nav** — 로고 + 메뉴 링크 (서비스 / 상품 보기 / 소개 / 작업 방식 / 문의하기)
2. **Hero** — 타이틀, 설명, CTA 버튼, 서비스 요약 카드
3. **서비스** — 디자인 요소 / 템플릿 / 상품샵(준비 중) 3가지 카드
4. **상품 갤러리** (`#portfolio`) — 탭 필터 + 12개 카드 그리드
5. **소개** (`#about`) — 크리에이터 스토리 + 통계 수치
6. **작업 과정** (`#process`) — 4단계 프로세스
7. **CTA** (`#contact`) — 샵 바로가기 + 이메일 문의
8. **Footer**

---

## 상품 갤러리 스펙

- **탭 필터**: 전체 / 요소(4) / 배경(3) / 템플릿(3) / 상품샵(2)
- **카드 클릭 시**: 비즈하우스 크리에이터 샵으로 이동 (`target="_blank"`)
- **현재 상태**: 플레이스홀더 (썸네일 없음, 상품명 미입력)
- **호버 효과**: 카라멜 오버레이 + "미리캔버스에서 보기" 텍스트

---

## 링크 연결 현황

| 위치 | 연결 URL |
|---|---|
| Hero "상품 바로가기" 버튼 | https://www.bizhows.com/v/creator/@somangpli |
| 갤러리 카드 전체 (12개) | https://www.bizhows.com/v/creator/@somangpli |
| "전체 상품 보러가기" 버튼 | https://www.bizhows.com/v/creator/@somangpli |
| 하단 CTA 버튼 | https://www.bizhows.com/v/creator/@somangpli |
| 이메일 문의 | hello@example.com ← **실제 이메일로 교체 필요** |

---

## 자동 상품 연동 검토 결과

비즈하우스(미리캔버스 상품샵)는 아래 이유로 **외부 자동 연동 불가**:
- `robots.txt`로 외부 크롤링 차단
- 기여자용 공개 API 미제공
- 미리캔버스 디자인허브도 동일하게 외부 API 없음

→ **채택한 방식**: 상품 링크·이미지를 직접 HTML에 입력하는 수동 관리 방식

---

## 앞으로 해야 할 것

- [ ] 각 카드에 실제 상품명 입력 (`class="p-name"`)
- [ ] 각 카드에 실제 상품 설명 입력 (`class="p-desc"`)
- [ ] 각 카드의 `href`를 개별 상품 URL로 교체
- [ ] 각 카드에 썸네일 이미지 추가 (`<img>` 태그로 `.p-thumb-inner` 대체)
- [ ] 이메일 주소 교체 (`hello@example.com`)
- [ ] 통계 수치 실제값으로 수정 (요소 수, 템플릿 수 등)

---

## 카드 교체 방법 (개발자 메모)

```html
<!-- 기존 플레이스홀더 카드 구조 -->
<a class="p-card" data-cat="요소" href="[여기에 개별 상품 URL]" target="_blank">
  <div class="p-thumb">
    <!-- 썸네일 이미지가 있으면 아래처럼 교체 -->
    <img src="[썸네일 이미지 URL]" style="width:100%;height:100%;object-fit:cover;" alt="상품명">
    <!-- 호버 오버레이는 그대로 유지 -->
    <div class="p-overlay">...</div>
  </div>
  <div class="p-info">
    <span class="p-cat-badge">요소</span>
    <div class="p-name">실제 상품명</div>
    <div class="p-desc">실제 상품 설명</div>
  </div>
</a>
```

---

## 파일 목록

| 파일 | 설명 |
|---|---|
| `index.html` | 홈페이지 전체 (HTML + CSS + JS 단일 파일) |
| `CLAUDE.md` | 이 파일. 프로젝트 결정 사항 기록 |
