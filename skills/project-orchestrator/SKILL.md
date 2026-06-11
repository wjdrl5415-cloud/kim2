---
name: project-orchestrator
description: Run all project automation tasks in one command. Use this skill whenever you need to execute your complete daily/weekly workflow - it automatically runs news collection, issue tracking, and documentation updates all at once. Perfect for batch automation, weekend catch-up, or anytime you want everything synchronized in your project. This skill orchestrates all three core automation skills in the correct order with proper error handling and generates a complete execution report.
compatibility: Requires all 3 automation skills to be available (daily-ai-news, github-issue-manager, documentation-generator)
---

# Project Orchestrator

Run all project automation tasks in one unified workflow.

## What This Skill Does

This skill:
1. **Executes all 3 automation skills** in the correct order
2. **Monitors each step** — tracks progress and handles errors
3. **Synchronizes data** — ensures all docs stay in sync
4. **Generates reports** — complete execution summary
5. **Commits everything** — single final commit to GitHub
6. **Sends notifications** — updates on completion status

## When to Use This Skill

- **"Run complete automation"** — execute everything at once
- **"Daily sync"** — refresh news, issues, and docs
- **"Weekly catch-up"** — sync everything that happened during week
- **"Before standups"** — ensure all info is current before meetings
- **"End of day"** — run full sync before leaving
- **"Manual full refresh"** — anytime you want total sync

## How to Use It

### Quick Execution

Just ask:
> "Run complete automation"

The skill will:
- Run all 3 skills in order
- Monitor progress
- Handle any errors
- Generate final report
- Commit everything

Takes: 10-15 minutes total

### Weekly Automation

> "Set up weekly full automation every Monday morning"

This:
- Runs all 3 skills automatically
- Every Monday at 9:00 AM
- Generates weekly summary
- Pushes to GitHub automatically

### With Detailed Report

> "Run automation and give me detailed report"

This:
- Executes all tasks
- Provides step-by-step breakdown
- Shows metrics & stats
- Lists any issues or blockers

## Execution Flow

### Step 1: AI News Collection (5 minutes)
```
[daily-ai-news skill]
├─ Search for latest AI news
├─ Generate HTML report
├─ Create log file
└─ ✅ Complete

Output:
  - ai-news-YYYYMMDD.html
  - logs/YYYY-MM-DD.log
```

### Step 2: Issue Management (3 minutes)
```
[github-issue-manager skill]
├─ Read all GitHub Issues
├─ Analyze progress
├─ Update issue comments
├─ Verify timelines
└─ ✅ Complete

Output:
  - Updated Issue comments
  - Progress tracking
```

### Step 3: Documentation Generation (5 minutes)
```
[documentation-generator skill]
├─ Analyze project state
├─ Update README.md
├─ Update CLAUDE.md
├─ Update ISSUES.md
├─ Generate weekly report
└─ ✅ Complete

Output:
  - Updated documentation
  - Weekly report
```

### Final: Summary & Commit
```
├─ Verify all changes
├─ Create summary report
├─ Commit to GitHub
├─ Push changes
└─ ✅ Complete

Output:
  - Execution summary
  - GitHub commit
```

## Complete Execution Report

When finished, generates:

```markdown
# Project Automation Report
Date: 2026-06-11 08:30 UTC
Status: ✅ SUCCESS

## Execution Summary
├─ Skill 1: daily-ai-news ✅ (5m 23s)
├─ Skill 2: github-issue-manager ✅ (3m 12s)
├─ Skill 3: documentation-generator ✅ (4m 47s)
└─ Total time: 13m 22s

## Changes Made
├─ Files created: 1 (ai-news-20260611.html)
├─ Files updated: 3 (README, CLAUDE, ISSUES)
├─ Issues updated: 3
├─ Commits: 1
└─ Total changes: 8

## AI News Collection
├─ News items found: 8
├─ Categories covered:
│  ├─ Technology/Models: 4
│  └─ Business/Industry: 4
└─ File: ai-news-20260611.html (15 KB)

## Issue Management
├─ Total issues: 9
├─ Updated comments: 3
├─ Completion: 22% (2/9)
└─ Blockers: 0

## Documentation Updates
├─ README.md ✅
├─ CLAUDE.md ✅
├─ ISSUES.md ✅
└─ Weekly report: week-24.md

## GitHub Sync
├─ Files committed: 5
├─ Commit message: "Weekly automation: news + issues + docs"
├─ Push status: ✅ Success
└─ Changes visible at: github.com/wjdrl5415-cloud/kim2

## Metrics
├─ Total execution time: 13m 22s
├─ Success rate: 100% (3/3 skills)
├─ Errors: 0
└─ Warnings: 0

## Next Run
├─ Scheduled: 2026-06-18 08:00
├─ Manual run available: anytime
└─ Status: Ready

Generated: 2026-06-11 08:43:22 UTC
```

## Features

### 1. Sequential Execution
- Runs skills in correct order
- Each completes before next starts
- Prevents conflicts & data issues

### 2. Error Handling
- Catches errors from each skill
- Provides detailed error messages
- Continues with next step (or stops if critical)

### 3. Progress Tracking
- Shows real-time status
- Estimated time remaining
- Percentage complete

### 4. Data Synchronization
- Ensures docs reflect current state
- Validates all changes
- Checks for conflicts

### 5. Comprehensive Reporting
- Execution summary
- Metrics & statistics
- Changes made
- Next scheduled run

### 6. GitHub Integration
- Auto-commits all changes
- Single, clean commit message
- Pushes to remote
- Verifies success

## Configuration

### Execution Frequency

**Default:** Manual only

**Options:**
```
Manual        → "Run automation"
Daily         → Every day at 8:00 AM
Weekly        → Every Monday at 9:00 AM
Bi-weekly     → Every other Monday
Monthly       → 1st of each month
```

Set in CLAUDE.md under automation settings.

### Which Skills to Run

**Default:** All 3 skills

**Options:**
```
All           → Daily-news + Issues + Docs
News only     → Just AI news collection
Issues only   → Just GitHub issue management
Docs only     → Just documentation update
News+Issues   → Skip documentation
Issues+Docs   → Skip news collection
```

### Notification Level

**Default:** Summary only

**Options:**
```
Silent        → No notifications
Summary       → Final report only
Progress      → Real-time updates
Detailed      → Step-by-step breakdown
Verbose       → Everything including debug info
```

## Example Workflows

### Scenario 1: Daily Morning Routine
```
Time: 8:00 AM
User: (automation runs automatically)

1. News collected ✅
2. Issues updated ✅
3. Docs refreshed ✅
4. Report sent ✅

User starts day with fresh information!
```

### Scenario 2: Weekly Catch-Up
```
Time: Monday 9:00 AM
User: "Run complete automation"

1. Analyzes all changes from past week
2. Collects news
3. Updates Issues with progress
4. Refreshes all documentation
5. Generates weekly summary report
6. Commits everything

User has complete week overview!
```

### Scenario 3: Before Important Meeting
```
Time: 10:00 AM (meeting at 11:00 AM)
User: "Quick sync everything"

Runs full automation in 15 minutes
Generates report to bring to meeting

User arrives with latest information!
```

### Scenario 4: End of Project Day
```
Time: 5:00 PM
User: "Finalize everything for today"

1. Ensures all news is documented
2. All Issues are up-to-date
3. All docs are current
4. Everything committed to GitHub

User leaves knowing everything is saved!
```

## Performance

### Typical Execution Time
```
Daily-news:           5-7 minutes
Issue-manager:        2-4 minutes
Doc-generator:        4-6 minutes
Summary & commit:     1-2 minutes
────────────────────────────────
Total:               12-19 minutes
```

### Optimization Tips
- Run during off-hours (less network congestion)
- Ensure good internet connection
- Have at least 100MB free disk space
- GitHub API rate limits: OK for daily use

## Output Files Created/Updated

**Created:**
- `ai-news-YYYYMMDD.html` (news report)
- `weekly-report-YYYY-WW.md` (weekly summary)
- `logs/YYYY-MM-DD.log` (execution log)

**Updated:**
- `README.md` (project overview)
- `CLAUDE.md` (project config)
- `ISSUES.md` (issues status)
- GitHub Issues (comments & status)

**Committed:**
- All above files
- Single commit: "Weekly automation: news + issues + docs"

## Limitations

- **Sequential only** — Cannot run skills in parallel (by design for data consistency)
- **No manual interrupts** — Once started, runs to completion
- **All-or-nothing** — Cannot skip individual skills mid-run (choose beforehand)
- **GitHub API limits** — Daily limit is generous but respect rate limits
- **Requires connectivity** — Internet connection needed for all steps

## Troubleshooting

### "One skill failed"
- Skill error is reported
- Full report still generated
- Check error message & logs
- Can re-run just that skill

### "GitHub push failed"
- Check internet connection
- Verify GitHub token is valid
- Check repository write permissions
- Retry (usually succeeds on 2nd attempt)

### "Automation takes too long"
- Normal range is 12-19 minutes
- Check internet speed
- GitHub API might be slow (wait & retry)
- Consider running less frequently

### "Documentation conflicts"
- Orchestrator detects conflicts
- Merges changes intelligently
- Manual edits are preserved
- Full log shows what merged

## What's Next?

Coming soon:
- [ ] Parallel execution option
- [ ] Partial runs (skip specific skills)
- [ ] Slack notifications
- [ ] Custom report formats
- [ ] Performance optimization
- [ ] Dry-run mode (simulate without committing)

## Version History

**v1.0** (Current)
- Execute all 3 skills sequentially
- Error handling for each step
- Comprehensive reporting
- GitHub auto-commit
- Configurable frequency

## Use Cases

**Personal Projects:**
- Daily refresh of project info
- Weekly catch-up on progress
- Monthly retrospectives

**Team Projects:**
- Daily stand-up preparation
- Weekly sprint updates
- Project health monitoring

**Open Source:**
- Automated community updates
- Regular documentation refresh
- Issue triage & tracking

Perfect for keeping your project automatically synchronized!

Have feedback? Let me know!
