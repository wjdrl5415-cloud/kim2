# GitHub Issues Backlog

이 문서는 GitHub Issues로 등록할 항목들입니다.
아래 내용을 복사하여 https://github.com/wjdrl5415-cloud/kim2/issues 에서 등록하세요.

---

## 🐛 Bug #1: GitHub 자동 푸시 미지원

**Title:** Implement automatic GitHub push after HTML generation

**Description:**
현재 HTML 파일을 생성한 후 수동으로 GitHub에 커밋/푸시해야 합니다.

**What should happen:**
- 매일 생성된 HTML 파일 자동 커밋
- GitHub에 자동 푸시
- 커밋 메시지: `ai-news-{YYYYMMDD}: Daily AI news summary`

**Steps to reproduce:**
1. 스케줄된 작업 실행 (Run now 클릭)
2. HTML 파일 생성 확인
3. GitHub 확인 → 파일이 올라오지 않음

**Priority:** High  
**Labels:** automation, github, feature

---

## 🐛 Bug #2: 에러 핸들링 및 로깅 부족

**Title:** Add error handling and logging system

**Description:**
뉴스 검색 실패 시 적절한 처리가 없고, 실행 로그가 기록되지 않습니다.

**Problem:**
- 웹 검색 실패 → 에러 메시지 없음
- 각 실행 결과 기록 없음
- 실패 원인 파악 어려움

**Solution:**
- try-catch로 검색 실패 처리
- 실행 로그 파일 자동 생성 (`logs/YYYY-MM-DD.log`)
- 심각한 에러 발생 시 알림 기능

**Priority:** High  
**Labels:** logging, error-handling, bug

---

## 🐛 Bug #3: Claude Code 앱 종료 시 작동 불가

**Title:** Enable scheduled tasks to run even when app is closed

**Description:**
Claude Code 앱이 닫혀있으면 스케줄된 작업이 실행되지 않습니다.

**Current Behavior:**
- 앱이 켜져있을 때만 오전 8시에 실행됨
- 앱이 종료되면 다음 실행 때까지 아무것도 일어나지 않음

**Desired Behavior:**
- 앱 상태 관계없이 일정한 시간에 자동 실행

**Possible Solutions:**
1. Windows Task Scheduler 연동
2. GitHub Actions 활용 (서버리스)
3. 별도 스케줄러 서비스 구축

**Priority:** Medium  
**Labels:** scheduling, automation

---

## ✨ Feature #1: 파일 아카이빙 및 자동 정리

**Title:** Implement file archiving and cleanup system

**Description:**
시간이 지나면서 HTML 파일이 계속 쌓입니다. 체계적인 관리가 필요합니다.

**Requested Features:**
- 월별 폴더 자동 분류 (`kim/2026-06/`, `kim/2026-07/`)
- 30일 이상 된 파일 자동 압축
- 최대 파일 개수 제한 (예: 최근 90일만 보관)
- 아카이브된 파일 리스트 관리

**Example Structure:**
```
kim/
├── 2026-06/
│   ├── ai-news-20260601.html
│   └── ...
├── 2026-07/
└── ai-news-{YYYYMMDD}.html (current month)
```

**Priority:** Low  
**Labels:** enhancement, file-management

---

## ✨ Feature #2: HTML 다크모드 및 반응형 디자인

**Title:** Add dark mode and responsive design to HTML reports

**Description:**
현재 HTML이 데스크톱 중심의 라이트 모드만 지원합니다.

**Improvements Needed:**
- [x] 다크모드 토글 (시스템 설정 감지)
- [x] 모바일/태블릿 반응형 레이아웃
- [x] 인쇄 최적화 (흑백 출력 대비)
- [x] 접근성 개선 (다크모드에서도 충분한 명도 대비)

**Priority:** Low  
**Labels:** ui, enhancement

---

## ✨ Feature #3: 설정 파일화

**Title:** Externalize configuration to JSON/YAML file

**Description:**
현재 모든 설정이 하드코딩되어 있어서 커스터마이징이 어렵습니다.

**Configuration Items:**
```json
{
  "schedule": {
    "enabled": true,
    "cron": "0 8 * * *",
    "timezone": "Asia/Seoul"
  },
  "news": {
    "categories": ["technology", "business"],
    "itemsPerCategory": 4,
    "keywords": [
      "new AI model release",
      "LLM benchmark",
      ...
    ]
  },
  "output": {
    "format": "html",
    "directory": "C:\\Users\\Admin\\Desktop\\kim",
    "template": "default"
  },
  "github": {
    "autoPush": false,
    "repository": "https://github.com/wjdrl5415-cloud/kim2.git"
  }
}
```

**Priority:** Medium  
**Labels:** configuration, enhancement

---

## ✨ Feature #4: 뉴스 소스 다양화

**Title:** Support multiple news sources (RSS, API)

**Description:**
현재 웹 검색(WebSearch)만 사용하고 있습니다.

**New Sources:**
- RSS 피드 (HackerNews, ArXiv 등)
- API 통합 (NewsAPI, Medium API)
- Twitter/X 트렌드
- GitHub Trending

**Benefits:**
- 더 다양한 뉴스 수집
- 신뢰도 높은 소스 활용
- 실시간성 개선

**Priority:** Low  
**Labels:** feature, sources

---

## ✨ Feature #5: 이메일 발송 기능

**Title:** Add email notification feature

**Description:**
생성된 보고서를 이메일로 자동 발송합니다.

**Requirements:**
- 수신자 이메일 설정
- HTML 이메일 포맷 지원
- 첨부파일로도 전송 옵션
- 구독자 관리

**Priority:** Low  
**Labels:** feature, notification

---

## 🐳 Devops #1: Docker 컨테이너화

**Title:** Create Docker image for AI News Summary

**Description:**
프로젝트를 Docker로 패키징하여 어디서나 실행 가능하게 합니다.

**Deliverables:**
- `Dockerfile` 작성
- `docker-compose.yml` (선택사항)
- 컨테이너 이미지 빌드 및 배포

**Benefits:**
- 의존성 관리 자동화
- 클라우드 배포 용이
- 버전 관리 간소화

**Priority:** Low  
**Labels:** devops, docker

---

## 📚 Documentation #1: 설치 및 사용 가이드 강화

**Title:** Expand documentation and add examples

**Description:**
현재 README는 기본적인 정보만 있습니다.

**Missing Documentation:**
- [x] 트러블슈팅 가이드
- [x] 자주 묻는 질문 (FAQ)
- [x] 설정 커스터마이징 예제
- [x] 환경 변수 설정 가이드
- [x] GitHub Actions 통합 가이드

**Priority:** Low  
**Labels:** documentation

---

**Summary:**
- 🔴 High Priority (필수): 2개
- 🟡 Medium Priority (권장): 2개
- 🟢 Low Priority (선택): 5개
- **Total:** 9개

이 이슈들을 GitHub에서 개별적으로 등록하세요!
