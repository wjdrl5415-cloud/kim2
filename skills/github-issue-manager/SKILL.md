---
name: github-issue-manager
description: Manage GitHub Issues efficiently with planning and tracking. Use this skill whenever you need to work on GitHub Issues systematically - for creating implementation plans, tracking progress, updating issue status, closing completed issues, or managing a project roadmap. This skill helps organize issues into phases, add detailed implementation plans as comments, track progress automatically, and maintain a clear project timeline. Perfect for coordinating multi-phase features, managing technical debt, or orchestrating team projects.
compatibility: Requires GitHub CLI (gh) authentication and write access to repository
---

# GitHub Issue Manager

Efficiently manage GitHub Issues with automated planning, tracking, and progress updates.

## What This Skill Does

This skill:
1. **Reads all Issues** in a GitHub repository
2. **Creates implementation plans** with phases and checkpoints
3. **Adds detailed comments** to each Issue
4. **Tracks progress** automatically
5. **Updates issue status** as work completes
6. **Closes completed issues** with summary
7. **Maintains roadmap** with timeline
8. **Generates reports** of project progress

## When to Use This Skill

- **"Create implementation plans for all issues in my kim2 repo"** — bulk planning
- **"Update progress on issue #1"** — mark items as complete
- **"Show me project roadmap with timelines"** — view full schedule
- **"Close completed issues automatically"** — mark done items
- **"Generate weekly progress report"** — track team velocity
- **"Move these issues to in-progress"** — bulk status update

## How to Use It

### Quick Setup
Just ask:
> "Set up issue management for my kim2 repository"

The skill will:
- List all Issues
- Analyze each one
- Suggest implementation timeline
- Ask for approval before proceeding

### Create Implementation Plans
> "Create implementation plans for all issues with phases and timelines"

This:
- Breaks each Issue into phases
- Adds detailed comments with checkpoints
- Sets realistic timelines
- Links related Issues

### Track Progress
> "Update progress: issue #1 phase 1 is complete"

This:
- Updates the Issue comment with checkmarks
- Updates issue labels (in-progress, blocked, etc.)
- Sends notification
- Recalculates timeline

### Generate Reports
> "Create a project status report"

This:
- Summarizes all Issues
- Shows completion percentage
- Lists blocked items
- Forecasts finish date
- Exports as markdown

## Implementation Planning Phases

When creating plans, the skill uses this structure:

```markdown
## 구현 계획

### Phase 1: Foundation
- [ ] Task 1
- [ ] Task 2

### Phase 2: Integration
- [ ] Task 3
- [ ] Task 4

### Phase 3: Testing
- [ ] Task 5
- [ ] Task 6

### Expected Completion: YYYY-MM-DD
```

Each phase includes:
- **Clear tasks** — specific, measurable work items
- **Checkboxes** — for progress tracking
- **Dependencies** — what blocks what
- **Timeline** — realistic completion dates

## Supported Issue Labels

The skill automatically manages these labels:

| Label | Meaning | Auto-Update |
|-------|---------|-------------|
| `status/ready` | Ready to start | Yes |
| `status/in-progress` | Currently being worked on | Yes |
| `status/blocked` | Blocked by another issue | Yes |
| `status/review` | Waiting for review | Yes |
| `priority/high` | Urgent/required | Manual |
| `priority/medium` | Important | Manual |
| `priority/low` | Nice to have | Manual |
| `type/feature` | New feature | Manual |
| `type/bug` | Bug fix | Manual |
| `type/docs` | Documentation | Manual |

## Features

### 1. Automated Planning
```
Input: Issue #1 - Add GitHub auto-push
Output:
- Phase 1: Research GitHub APIs (2 days)
- Phase 2: Implement core logic (3 days)
- Phase 3: Testing & integration (2 days)
Timeline: 7 days total
```

### 2. Progress Tracking
- Automatic checkbox counting
- Completion percentage per Issue
- Phase-by-phase status
- Dependency tracking

### 3. Status Management
- Auto-label based on progress
- Update labels as work completes
- Cascade status to dependent Issues
- Link related Issues

### 4. Timeline Management
- Estimate completion dates
- Identify critical path
- Flag delays automatically
- Forecast overall completion

### 5. Report Generation
- Weekly progress reports
- Monthly summaries
- Risk assessment
- Team velocity tracking

## Example Workflow

### Day 1: Planning
```
User: "Create plans for all 9 issues"
Skill:
  1. Reads all Issues
  2. Adds implementation comments
  3. Sets labels and timelines
  4. Generates roadmap
Output: Issues updated with detailed plans
```

### Days 2-7: Execution
```
User: "Update issue #1 phase 1 complete"
Skill:
  1. Updates Issue comment (checkmarks)
  2. Auto-labels as in-progress
  3. Recalculates timeline
  4. Flags any blocked items
Output: Issue #1 updated with new status
```

### Weekly: Reporting
```
User: "Generate week 1 report"
Skill:
  1. Counts completed items
  2. Summarizes progress per Issue
  3. Lists blockers
  4. Updates overall completion
Output: Markdown report with metrics
```

### Completion: Closure
```
User: "Issue #1 is complete"
Skill:
  1. Verifies all phases done
  2. Adds completion summary
  3. Closes the Issue
  4. Links to PR/commits
Output: Issue closed with documentation
```

## Technical Details

### Supported Repositories
- ✅ Public repositories
- ✅ Private repositories (with auth)
- ✅ Organization repositories
- ✅ Team repositories

### Requirements
- GitHub CLI (gh) installed and authenticated
- Repository write access
- Issues enabled on repository

### What Gets Created/Updated
- **Comments** — Phase-based implementation plans
- **Labels** — Status and priority labels
- **Issue titles** — No changes (preserved as-is)
- **Milestones** — Optional timeline grouping
- **Projects** — Optional board integration

### Data Preserved
- Original Issue descriptions
- Author information
- Created/updated dates
- Comments from others

## Advanced Usage

### Bulk Operations
> "Mark issues #1-#5 as in-progress"

### Linking Issues
> "Link issue #1 (blocks) issue #2"

### Dependency Tracking
> "Show issues blocked by #1"

### Timeline Estimation
> "Estimate completion for all High priority issues"

### Resource Planning
> "Show which issues are assigned to which people"

### Velocity Tracking
> "Calculate team velocity - issues completed per week"

## Limitations

- **No direct issue closing** — Must close via user command with reason
- **No code changes** — Can't modify repo files, only Issues metadata
- **No direct assignment** — Can suggest but user must assign manually
- **No PR linking** — Manual linking required (for now)
- **Comments only** — Can't edit existing comments (creates new ones)

## What's Next?

This skill is actively maintained. Coming soon:
- [ ] Auto-link to pull requests
- [ ] Slack notifications for blockers
- [ ] Integration with project boards
- [ ] Burndown chart generation
- [ ] Team assignment suggestions
- [ ] Automatic delay detection
- [ ] Risk scoring system

## Version History

**v1.0** (Current)
- GitHub Issues reading and writing
- Implementation planning automation
- Progress tracking
- Status management
- Report generation

Perfect for managing projects like **AI News Generator** where multiple features are being built in parallel!

Have feedback or suggestions? Let me know!
