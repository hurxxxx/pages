# KStarMusic Store — 일일 프로젝트 보고서 양식 가이드

## 개요

이 문서는 일일 프로젝트 보고서의 **양식과 필수 포함 항목**을 정의한다.
보고서 생성 시 이 가이드를 읽고, 양식은 유지하되 데이터 분석 결과에 따라
특이사항, 리스크 코멘트, 종합 평가 등을 자유롭게 추가한다.

## 파일 규칙

- 위치: `reports/YYYY-MM-DD.html`
- 인덱스: `index.html`의 reports 배열에 새 항목 추가
- 디자인: 다크모드/라이트모드 자동 대응, 모바일 반응형, 인쇄 가능
- 폰트: Pretendard (Google Fonts)
- 차트: Chart.js 4.x (CDN), canvas는 반드시 `position:relative` div로 감싸고 고정 height 지정
- 링크: WP ID 클릭 시 OpenProject 해당 작업으로 이동
- 상단에 `../` 목록 돌아가기 링크 포함

---

## 필수 섹션 (순서대로)

### 1. 헤더
- 프로젝트명: KStarMusic Store
- 부제: "종합 프로젝트 진행 현황"
- 기준일 표시 (YYYY-MM-DD 요일)
- 프로젝트 시작일 표시

### 2. 핵심 지표 카드 (6개)
- 전체 작업 수 (타입별 내역: Task, Summary task, Milestone)
- 완료 (Closed) 수 + 전체 대비 비율
- 진행 중 (In progress) 수 + 어디서 진행 중인지
- 대기 (New) 수
- 기각 (Rejected) 수
- 최근 변경 수 (전일~당일) + 신규/수정/완료 내역

### 3. 전체 포팅 Phase 현황
- `Phase 0 → Phase 7`을 항상 고정 순서로 모두 표시
- 각 Phase마다 `주제`, `현재 상태`, `짧은 진행 메모`를 함께 표시
- 상태 소스는 기본적으로 `docs/porting/progress/PROGRESS.md`를 기준으로 삼는다
- 완료/진행/대기/QA backlog 성격이 한눈에 보이도록 색 또는 뱃지 차이를 둔다

### 4. 차트 (2열 그리드)
- 좌: 상태별 도넛 차트 (Closed, In progress, New, Rejected)
- 우: 주간별 활동 막대 차트 (생성/수정/완료)

### 5. 일자별 활동 추이
- 라인 차트 (프로젝트 시작일 ~ 기준일)
- 생성/수정/완료 3개 라인
- 급증 또는 급감 구간이 있으면 코멘트 추가

### 6. 전체 로드맵 타임라인
- 간트형 바 차트 (전체 스프린트/Summary task)
- 상태별 색상 구분: 완료(green), 진행(blue), 예정(gray), 기각(red)
- 오늘 날짜 표시선 (빨간 세로선)

### 7. 감사/검증 진행률 (해당되는 경우)
- 감사 대상 총 수 vs 완료 수
- 프로그레스 바 + 퍼센트
- 감사 기준 변경이 있었으면 별도 코멘트

### 8. 스프린트별 진척률
- 각 스프린트: 이름, 기간, 프로그레스 바, 완료%
- 전체/완료/진행/기각 수치
- 진척이 특히 느리거나 빠른 스프린트에 코멘트

### 9. 일정 변경 이력
- 테이블: WP ID, 작업명, 변경 전 날짜, 변경 후 날짜, 사유
- 전일~당일 발생한 변경만 표시
- 변경이 없으면 "변경 없음" 표시

### 10. 지연 사유 (해당되는 경우)
- 지연이 있는 경우에만 표시
- 각 사유: 제목 + 설명
- 좌측 코랄색 보더 강조

### 11. 현재 진행 중인 작업
- 모든 In progress 상태 작업 나열
- 각 항목: WP ID, 제목, 기간, 소속 그룹, 현재 상태 노트
- 어제 대비 변화가 있으면 표시

### 12. 최근 완료된 작업
- 전일~당일 Closed된 작업
- 각 항목: WP ID, 제목, 완료일, 노트
- 완료된 게 없으면 "해당 없음"

### 13. 스프린트별 상세 현황
- 각 스프린트 접이식 또는 카드형
- 하위 작업 전체 나열: ID, 제목, 상태 뱃지, 기간
- 일정 변경이 있는 작업에 변경 태그

---

## 선택 섹션 (상황에 따라 추가)

### 종합 평가 코멘트
- 전체 진행 상황에 대한 1~3문장 요약 평가
- 잘 되고 있는 점, 우려되는 점
- 다음 주 핵심 목표

### 리스크 & 주의사항
- 일정 지연 위험이 있는 작업
- 의존성 충돌
- 리소스 병목

### 마일스톤 현황
- 주요 마일스톤 달성/미달성 상태
- 다음 마일스톤까지 남은 일수

### 신규 생성 작업
- 당일 새로 생성된 작업이 많은 경우 별도 섹션

### 어제 vs 오늘 비교
- 주요 수치 변화 (완료 수, 진행 수 등)
- 상태가 바뀐 작업 목록

---

## 디자인 규칙

### 색상 체계
- 상태 뱃지: In progress(파란), Closed(초록), New(회색), Rejected(빨강)
- 변경 태그: 호박색 배경
- 지연 사유: 좌측 코랄색 보더
- 차트 색상: 생성(#60A5FA), 수정(#FBBF24), 완료(#34D399)

### 레이아웃
- 최대 너비: 1120px 중앙 정렬
- 카드: 1px 보더 + 가벼운 그림자
- 폰트 크기: 본문 .82rem, 라벨 .68~.72rem, WP ID .73rem (mono)
- 반응형: 768px 이하에서 2열→1열, 480px 이하에서 메트릭 2열

### 차트 필수 규칙
- canvas를 `<div style="position:relative;height:NNNpx">` 로 감싼다
- canvas에 직접 height 속성 사용 금지
- `responsive: true, maintainAspectRatio: false` 필수
- 범례는 Chart.js 기본 사용 (커스텀 불필요)

---

## 데이터 수집 방법 (OpenProject API v3)

### 전체 작업 조회
```
GET /api/v3/work_packages?filters=[{"project":{"operator":"=","values":["5"]}}]&pageSize=200&sortBy=[["updatedAt","desc"]]
```

### 특정 상위 작업 하위 조회
```
GET /api/v3/work_packages?filters=[{"ancestor":{"operator":"=","values":["PARENT_ID"]}}]&pageSize=200
```

### 변경 이력 확인
```
GET /api/v3/work_packages/{ID}/activities?pageSize=10
```

### 주요 필드
- `subject`: 제목
- `_links.type.title`: Task / Summary task / Milestone
- `_links.status.title`: New / In progress / Closed / On hold / Rejected
- `startDate`, `dueDate`: 시작일, 종료일
- `createdAt`, `updatedAt`: 생성일시, 수정일시
- `_links.parent.title`: 부모 작업
- `description.raw`: 설명 (마크다운)

### 상태 ID
- 1: New
- 7: In progress
- 12: Closed
- 13: On hold
- 14: Rejected

---

## index.html 업데이트 규칙

보고서 생성 후 `index.html` 내 `reports` 배열에 항목 추가:

```javascript
{
  date: 'YYYY-MM-DD',
  title: '종합 프로젝트 진행 현황',   // 또는 특이사항 반영한 제목
  file: 'reports/YYYY-MM-DD.html',
  summary: '전체 N건 · 완료 N · 진행 N · 대기 N',
  changes: N,                          // 전일~당일 변경 수
  highlights: '주요 변경사항 1줄 요약',
  latest: true                         // 최신 보고서만 true, 이전것은 false로 변경
}
```

---

## 참고

- OpenProject 프로젝트: https://project.kstarmusic.com/projects/kstarmusicstore
- 프로젝트 ID: 5
- GitHub Pages: https://hurxxxx.github.io/pages/
- 이 가이드 자체도 필요시 업데이트 가능
