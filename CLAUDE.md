# AI News Generator Project - CLAUDE.md

## 📋 프로젝트 개요

**목표:** 매일 AI 산업 뉴스를 자동으로 수집하여 HTML 보고서 생성 & GitHub 저장소 관리

**상태:** 🟢 운영 중 (Daily v2.0, Issue Manager v1.0)

**저장소:** https://github.com/wjdrl5415-cloud/kim2

---

## 🎯 핵심 목표

1. ✅ **매일 아침 AI 뉴스 수집** → HTML 리포트 생성
2. ✅ **자동 GitHub 업로드** → 버전 관리
3. ✅ **이슈 자동 추적** → 프로젝트 진행 상황 관리
4. 🟡 **확장 기능** → Issues #3-#9 구현 (진행 예정)

---

## 🏗️ 프로젝트 구조

```
kim/
├── .claude/
│   └── skills/
│       ├── daily-ai-news/
│       │   └── SKILL.md (v2.0: 뉴스 수집 + GitHub 푸시 + 에러 로깅)
│       └── github-issue-manager/
│           └── SKILL.md (v1.0: Issues 자동 추적)
│
├── kim-repo/ (GitHub 저장소 로컬 사본)
│   ├── ai-news-YYYYMMDD.html (일일 뉴스 리포트)
│   ├── ai-news-YYYYMMDD-v2.html (v2.0 이후)
│   ├── README.md (프로젝트 설명)
│   ├── ISSUES.md (개선 사항 목록)
│   ├── SKILL.md (v1.0 스킬)
│   └── skills/ (스킬 저장소)
│
└── logs/ (실행 로그)
    └── YYYY-MM-DD.log
```

---

## ⚙️ 자동화 설정

### 스케줄된 작업

**Daily AI News (매일 오전 8시)**
```
시간: 0 8 * * * (로컬 시간대)
작업: 
  1. AI 뉴스 검색 (WebSearch)
  2. HTML 파일 생성
  3. GitHub에 자동 커밋/푸시
  4. 로그 파일 생성
위치: Scheduled Tasks (Claude Code)
```

**GitHub Issue Manager (매주 월요일 오전 9시 - 예정)**
```
시간: 0 9 * * 1
작업:
  1. 모든 Issues 읽기
  2. 진행 상황 업데이트
  3. 타임라인 확인
위치: Scheduled Tasks (Claude Code)
```

---

## 📅 진행 일정

### Phase 1: Foundation (완료 ✅)
- [x] Daily AI News 스킬 v1.0 생성
- [x] GitHub 저장소 설정
- [x] 초기 뉴스 수집 테스트
- [x] README.md 작성
- [x] 9개 Issues 등록

### Phase 2: Enhancement (진행 중 🟡)
- [x] Daily AI News v2.0 (GitHub 자동 푸시 + 에러 로깅)
- [x] GitHub Issue Manager 스킬 생성
- [ ] **Issue #1-2 구현** (2026-06-18까지)
  - GitHub 자동 푸시 완전 자동화
  - 에러 핸들링 & 로깅 강화
- [ ] **Issue #3-4 구현** (2026-06-25까지)
  - 앱 종료해도 실행 (Task Scheduler/GitHub Actions)
  - 설정 파일화 (JSON)

### Phase 3: Expansion (예정 📋)
- [ ] Issue #5-9 구현 (2026-07-02 ~ 2026-07-23)
- [ ] Production 배포

---

## 📊 현재 상태

### 스킬 현황

| 스킬 | 버전 | 상태 | 기능 |
|------|------|------|------|
| daily-ai-news | v2.0 | ✅ 운영 중 | 뉴스 수집 + HTML 생성 + GitHub 푸시 + 로깅 |
| github-issue-manager | v1.0 | ✅ 운영 중 | Issues 자동 추적 & 진행 상황 업데이트|

### Issues 현황

| 우선순위 | 상태 | 개수 | 내용 |
|---------|------|------|------|
| 🔴 High | 진행 중 | 2 | #1-2: GitHub 푸시, 에러 로깅 |
| 🟡 Medium | 계획 | 2 | #3-4: 앱 종료 시에도 실행, 설정 파일화 |
| 🟢 Low | 계획 | 5 | #5-9: 파일 정리, 다크모드, 소스 다양화, 이메일, Docker |

### 파일 현황

- HTML 파일: 2개 (v1, v2)
- 문서: 5개 (README, ISSUES, 3개 SKILL)
- 커밋: 6개

---

## 🛠️ 개발 규칙

### 코딩 스타일

**Python/Bash Scripts:**
- 명확한 변수명 사용
- 에러 핸들링 필수
- 로그 메시지 포함
- 주석 최소화 (코드가 자명할 것)

**HTML/CSS:**
- 반응형 디자인 우선
- 다크모드 고려
- 접근성(a11y) 준수

**GitHub Commits:**
```
형식: [type] title

type:
- feat: 새 기능
- fix: 버그 수정
- docs: 문서화
- refactor: 코드 정리
- ci: 자동화 설정

예시:
feat: Add GitHub auto-push to daily-ai-news v2.0
fix: Handle web search timeout errors
docs: Update README with new features
```

### 파일 관리

**로컬 저장:** `C:\Users\Admin\Desktop\kim\`
**GitHub 저장:** `https://github.com/wjdrl5415-cloud/kim2`
**로그 저장:** `logs/YYYY-MM-DD.log`

**매일 생성되는 파일:**
```
ai-news-YYYYMMDD.html (또는 ai-news-YYYYMMDD-v2.html)
logs/YYYY-MM-DD.log
```

---

## 🔄 워크플로우

### 일일 실행 프로세스

```
1️⃣ 08:00 - Daily AI News 자동 실행
   ├─ 뉴스 검색 (3-5분)
   ├─ HTML 생성 (1-2분)
   ├─ GitHub 커밋/푸시 (2-3분)
   └─ 로그 저장

2️⃣ 09:00 - 수동 확인 (필요시)
   ├─ HTML 파일 확인
   ├─ GitHub 커밋 확인
   └─ 에러 로그 확인

3️⃣ 월요일 09:00 - Issue Manager 실행 (예정)
   ├─ Issues 진행 상황 확인
   ├─ 댓글 자동 업데이트
   └─ 타임라인 확인
```

### 이슈 처리 프로세스

```
1. Issue 계획 작성 (댓글로 Phase별 계획)
2. 계획 실행 (코드 작성, 테스트)
3. 진행 상황 업데이트 (체크박스 체크)
4. 완료 후 Issue 종료
```

---

## 📝 주의사항

### ⚠️ 필수 확인사항

- [ ] Claude Code 앱이 매일 오전 8시에 켜져있을 것
  - (또는 Windows Task Scheduler/GitHub Actions로 대체 예정)
- [ ] GitHub 토큰이 유효할 것
  - 토큰 만료 시: `gh auth login --web`
- [ ] 로그 파일 권한이 있을 것
  - 권한 문제 시: 폴더 권한 확인

### 🔐 보안

- GitHub 토큰을 환경 변수로만 사용
- 절대 코드에 토큰을 하드코딩하지 말 것
- .gitignore에 민감한 파일 추가

### 📱 로깅

모든 실행은 자동으로 로그됨:
```
logs/2026-06-11.log
├─ 08:00:15 - Starting AI news collection
├─ 08:00:22 - Searching: new AI model release
├─ 08:00:35 - Found 8 articles
├─ 08:00:45 - SUCCESS: ai-news-20260611.html saved
└─ 08:00:52 - GitHub push successful
```

---

## 🚀 다음 단계

### 이번 주 (2026-06-11 ~ 2026-06-15)
- [ ] Issue #1 구현 마무리 (GitHub 자동 푸시 완전 자동화)
- [ ] Issue #2 구현 마무리 (에러 로깅 강화)
- [ ] 테스트 및 검증

### 다음 주 (2026-06-18 ~ 2026-06-25)
- [ ] Issue #3 시작 (앱 종료해도 실행)
- [ ] Issue #4 시작 (설정 파일화)
- [ ] GitHub Actions 워크플로우 추가 검토

### 장기 (2026-07 이후)
- [ ] Issue #5-9 순차 구현
- [ ] Production 환경 배포
- [ ] 모니터링 및 최적화

---

## 📞 연락처 & 리소스

**GitHub Issues:** https://github.com/wjdrl5415-cloud/kim2/issues

**스킬 위치:** `C:\Users\Admin\.claude\skills\`

**로컬 프로젝트:** `C:\Users\Admin\Desktop\kim\`

---

## 📚 문서 참고

- [README.md](./kim-repo/README.md) - 프로젝트 소개
- [ISSUES.md](./kim-repo/ISSUES.md) - 개선 사항 목록
- [SKILL.md - daily-ai-news](./kim-repo/skills/daily-ai-news/SKILL.md) - 뉴스 수집 스킬
- [SKILL.md - github-issue-manager](./kim-repo/skills/github-issue-manager/SKILL.md) - 이슈 관리 스킬

---

**Last Updated:** 2026-06-11  
**Project Owner:** wjdrl5415  
**Status:** 🟢 Active & Automated
