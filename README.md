# 🤖 AI 뉴스 요약 시스템

매일 아침 AI 산업의 주요 뉴스를 자동 수집하여 HTML 보고서로 생성하는 시스템입니다.

## 📋 기능

- **자동 뉴스 수집** — 매일 오전 8시 자동 실행
- **기술/모델 + 비즈니스 뉴스** — 두 분야 균형있게 수집
- **HTML 보고서 생성** — 예쁜 레이아웃의 인터랙티브 HTML 파일
- **날짜별 저장** — `ai-news-YYYYMMDD.html` 형식으로 자동 생성

## 🚀 시작하기

### 필수 요구사항
- Claude Code 앱 (데스크톱)
- 인터넷 연결

### 설치

1. **Claude Code 앱에서 설정**
   - 사이드바 → `Scheduled` 탭
   - `daily-ai-news-summary` 작업 확인

2. **실행 확인**
   - "Run now" 버튼 클릭하여 테스트
   - `C:\Users\Admin\Desktop\kim\` 폴더에 HTML 파일 생성 확인

### 사용법

매일 오전 8시마다 자동으로:
1. 뉴스 웹 검색
2. 기술/모델 + 비즈니스/산업 뉴스 6~8건 수집
3. HTML 보고서 생성 (`ai-news-YYYYMMDD.html`)

생성된 파일을 브라우저로 열면 예쁜 포맷으로 볼 수 있습니다.

## 📝 커스터마이징

### 뉴스 키워드 변경
Claude Code → Scheduled Tasks → `daily-ai-news-summary` → 편집
`prompt` 섹션의 검색 키워드 수정

### 실행 시간 변경
- 현재: 매일 오전 8시 (cron: `0 8 * * *`)
- 변경하려면: Scheduled Tasks에서 `cronExpression` 수정

### HTML 스타일 커스터마이징
생성되는 HTML 파일의 `<style>` 섹션에서 색상/레이아웃 변경 가능

## ⚠️ 주의사항

- **Claude Code 앱이 켜져있어야 함** — 앱 종료 시 다음 실행까지 대기
- **웹 검색 권한 필요** — 스케줄 첫 실행 시 권한 승인 필요
- **파일 저장 위치** — 고정: `C:\Users\Admin\Desktop\kim\`

## 🐛 알려진 문제

- [ ] GitHub 자동 푸시 미지원 (수동 push 필요)
- [ ] 뉴스 검색 실패 시 에러 핸들링 부족
- [ ] 로깅 시스템 없음
- [ ] 이전 파일 자동 정리 기능 없음

## 🔄 로드맵

- [ ] GitHub 자동 커밋/푸시 기능
- [ ] 에러 로깅 시스템
- [ ] 파일 아카이빙 (월별 폴더 분류)
- [ ] 다크모드 / 반응형 디자인
- [ ] RSS 피드 및 API 소스 지원
- [ ] 이메일 발송 기능
- [ ] Docker 컨테이너화

## 📧 피드백

문제가 있거나 제안이 있으면 [Issues](https://github.com/wjdrl5415-cloud/kim2/issues)에 등록해주세요.

---

**Last Updated:** 2026-06-11  
**Created by:** wjdrl5415
