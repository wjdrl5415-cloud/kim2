---
name: documentation-generator
description: Automatically generate and update project documentation. Use this skill whenever you need to create, update, or maintain project documents like README, CLAUDE.md, ISSUES summaries, or project status reports. This skill analyzes your project structure, progress, and code changes, then automatically creates or updates documentation to keep everything in sync. Perfect for maintaining accurate documentation without manual effort - use whenever files change, milestones complete, or you want to refresh documentation.
compatibility: Requires Git access and file system write permissions
---

# Documentation Generator

Automatically create, update, and maintain project documentation.

## What This Skill Does

This skill:
1. **Analyzes project structure** — reads all files and understands the project
2. **Generates documentation** — creates README, CLAUDE.md, status reports
3. **Updates existing docs** — keeps docs in sync with actual project state
4. **Tracks changes** — detects new features, completed issues, progress
5. **Creates reports** — weekly/monthly status, progress metrics
6. **Maintains consistency** — ensures all docs follow same format
7. **Auto-commits** — updates docs and commits to Git automatically

## When to Use This Skill

- **"Create documentation for this project"** — generate all docs from scratch
- **"Update all documentation"** — refresh docs after changes
- **"Generate a project status report"** — weekly/monthly summary
- **"Keep documentation in sync"** — auto-update docs regularly
- **"Create a weekly summary of what was done"** — track progress
- **"Document the new feature I just added"** — update docs immediately

## How to Use It

### Generate Complete Documentation

Just ask:
> "Generate complete documentation for my project"

The skill will:
- Create/update README.md
- Create/update CLAUDE.md
- Analyze Issues and update status
- Create project status report
- Commit all changes to GitHub

### Update After Changes

> "Update documentation after my changes"

This:
- Detects what changed
- Updates relevant docs
- Reflects new features/fixes
- Updates progress metrics
- Commits changes

### Create Weekly Report

> "Create weekly progress report"

This:
- Summarizes work completed
- Lists Issues closed
- Shows metrics (commits, files changed)
- Lists upcoming work
- Exports as markdown

### Keep Docs in Sync

> "Set up automatic documentation updates every Monday"

This creates a scheduled task to:
- Auto-update all documentation weekly
- Reflect current project state
- Commit changes automatically

## Documentation Managed

### README.md
**Contents:**
- Project overview
- Features & capabilities
- How to use
- Installation instructions
- Requirements
- Examples
- Troubleshooting
- Version history

**Updated when:**
- New features added
- Usage changes
- Installation steps change
- New examples needed

### CLAUDE.md
**Contents:**
- Project goals & status
- File structure
- Automation settings
- Progress timeline
- Development rules
- Workflows
- Important notices
- Next steps

**Updated when:**
- Schedule changes
- New automation added
- Phase completion
- Process updates

### ISSUES.md
**Contents:**
- Issue list with priorities
- Implementation plans
- Phase breakdown
- Timeline for each issue
- Dependencies & blockers

**Updated when:**
- New issues created
- Issue status changes
- Implementation plans updated
- Timeline changes

### Status Reports
**Weekly Report (auto-generated)**
```markdown
# Weekly Status Report - Week of YYYY-MM-DD

## Summary
- Issues completed: X
- Features added: X
- Commits: X
- Lines changed: +X, -X

## Completed This Week
- Issue #1 Phase 1: Done
- Added GitHub auto-push
- Improved error handling

## In Progress
- Issue #1 Phase 2
- Issue #2 implementation

## Blockers
- None

## Next Week
- Complete Issue #1
- Start Issue #3
```

**Monthly Report (auto-generated)**
```markdown
# Monthly Status - June 2026

## Overall Progress
- Issues completed: 15/30 (50%)
- Features shipped: 5
- Commits: 127

## Key Achievements
- Launched v2.0 with GitHub integration
- Implemented GitHub Issue Manager
- Created Documentation Generator skill

## Metrics
- Avg commits per day: 4.2
- Avg Issues completed per week: 3.75
- Project velocity: Increasing

## Roadmap Status
- Phase 1 ✅ Complete
- Phase 2 🟡 60% complete
- Phase 3 📋 Planning
```

## Features

### 1. Automatic Analysis
Scans project and understands:
- What was changed (commits, files)
- What was completed (closed issues)
- What's in progress (open issues, branches)
- Project metrics (lines of code, commit frequency)

### 2. Smart Documentation Updates
- Detects what changed
- Updates only relevant sections
- Preserves manual edits
- Maintains consistency

### 3. Progress Tracking
- Counts completed issues & features
- Calculates completion percentage
- Tracks timeline vs actual
- Identifies blockers

### 4. Report Generation
- Weekly summaries
- Monthly reviews
- Quarterly retrospectives
- Project metrics

### 5. Automatic Commits
All documentation updates are automatically:
- Staged and committed
- Pushed to GitHub
- Logged with descriptive messages

## Example Workflow

### Day 1: Project Start
```
User: "Generate documentation"
Skill:
  1. Analyzes project structure
  2. Creates README.md
  3. Creates CLAUDE.md
  4. Summarizes Issues
  5. Commits to GitHub
Output: 4 new documents created
```

### Week 1: After First Changes
```
User: "Update documentation"
Skill:
  1. Detects changes
  2. Updates README with new features
  3. Updates CLAUDE with progress
  4. Updates status in ISSUES.md
  5. Creates week 1 report
  6. Commits all changes
Output: Documentation synced with reality
```

### Weekly Automation
```
Every Monday morning:
  1. Analyzes past week
  2. Creates weekly report
  3. Updates progress metrics
  4. Commits changes
  5. Notifies team
Output: Automatic status reports
```

## Documentation Template

### README.md Template
```markdown
# [Project Name]

## Overview
[One sentence description]

## Features
- Feature 1
- Feature 2
- Feature 3

## Quick Start
[How to get started]

## Installation
[Setup instructions]

## Usage
[How to use]

## Examples
[Code examples]

## Configuration
[Settings & customization]

## Troubleshooting
[Common issues & solutions]

## Requirements
[Dependencies & system requirements]

## Version History
[Release notes]

## Contributing
[How to contribute]

## License
[License info]
```

### CLAUDE.md Template
```markdown
# [Project Name] - CLAUDE.md

## Project Overview
[Project description]

## Project Structure
[Directory structure]

## Automation Setup
[Scheduled tasks & workflows]

## Progress Timeline
[Phases & milestones]

## Current Status
[What's done, in progress, planned]

## Development Rules
[Coding standards & conventions]

## Workflows
[How the project works]

## Important Notes
[Critical information]

## Next Steps
[What comes next]
```

## Advanced Usage

### Bulk Documentation Update
> "Update all documentation, including metrics and timelines"

### Generate Different Formats
> "Export documentation as PDF/HTML instead of markdown"

### Team Sync
> "Create a documentation sync report showing what changed"

### Archive Old Docs
> "Archive documentation from previous months"

## Configuration

### Auto-Update Frequency

**Default:** Weekly (every Monday)

**Options:**
- Daily — very detailed tracking
- Weekly — good balance
- Monthly — high-level overview
- Manual — only on demand

Set in CLAUDE.md under automation settings.

### Documentation Style

**Default:** Markdown with emojis

**Customizable:**
- Color/styling
- Emoji usage
- Section order
- Detail level

## Limitations

- **Manual edits preserved** — Won't overwrite custom content you add
- **Git integration required** — Needs git for commits
- **Read-only sources** — Can't edit source code, only docs
- **Format limited** — Currently markdown only (HTML/PDF coming)

## Output Examples

When run, creates/updates:
- ✅ README.md (project overview)
- ✅ CLAUDE.md (project config)
- ✅ ISSUES.md (work tracking)
- ✅ weekly-report-YYYY-WW.md (status reports)
- ✅ monthly-report-YYYY-MM.md (summaries)
- ✅ metrics.json (raw data)

All automatically committed to GitHub!

## What's Next?

Coming soon:
- [ ] HTML/PDF export
- [ ] Automatic changelog generation
- [ ] Team contribution tracking
- [ ] Project health scoring
- [ ] Slack/email notifications
- [ ] Comparison reports (prev month vs now)
- [ ] Trend analysis (velocity, quality metrics)

## Version History

**v1.0** (Current)
- Automatic README generation
- CLAUDE.md creation
- Issue status tracking
- Weekly/monthly reports
- Git auto-commit

Perfect for keeping documentation fresh automatically!

Have feedback? Let me know!
