---
name: daily-ai-news
description: Generate daily AI news summary reports in HTML format with GitHub integration. Use this skill whenever the user asks for AI news, wants to set up automated daily summaries, or needs industry updates on AI technology and business. This skill searches for latest AI news across technology (models, research, benchmarks) and business (funding, acquisitions) sectors, then generates beautifully formatted HTML reports with headlines, detailed summaries, keywords, and trends. Supports GitHub auto-push, error logging, and scheduling.
compatibility: Requires web search capability and Claude Code for scheduled automation
---

# Daily AI News Generator v2.0

Generate comprehensive daily AI industry news summaries in HTML format with GitHub integration and error handling.

## What This Skill Does

This skill:
1. **Searches for latest AI news** across multiple keywords and sources
2. **Collects 6-8 curated articles** from two focus areas:
   - **Technology/Models** — new AI model releases, research papers, benchmarks
   - **Business/Industry** — company funding, acquisitions, product launches
3. **Creates a professional HTML report** with:
   - Top 3 headlines
   - Detailed news sections with "What happened" and "Why it matters"
   - Trending keywords
   - One-line summary of the day's sentiment
4. **Handles errors gracefully** — tries alternative sources if search fails
5. **Creates automatic logs** — tracks each run in `logs/YYYY-MM-DD.log`
6. **Pushes to GitHub** (optional) — automatically commits and uploads reports
7. **Saves locally** with date-stamped filenames

## When to Use This Skill

- **"Summarize today's AI news for me"** — instant news collection
- **"I want daily AI news every morning"** — sets up automated scheduling
- **"Create an AI news report focused on [topic]"** — customized news gathering
- **"Show me the latest on LLMs and AI startups"** — targeted search
- **"Generate AI news and push to GitHub automatically"** — with version control

## How to Use It

### Quick One-Time Report
Just ask:
> "Generate an AI news summary for today"

The skill will:
- Search web for latest AI news
- Compile into HTML
- Save to your Desktop (`ai-news-YYYYMMDD.html`)
- Log the process in `logs/YYYY-MM-DD.log`
- Show you the file location

### Automated Daily Reports
To set up automatic daily collection:
> "Set up daily AI news summaries at 8 AM"

This creates a scheduled task that runs every morning and generates a fresh report.

### With GitHub Auto-Push
To automatically push to GitHub:
> "Set up daily AI news with GitHub auto-push to my kim2 repository"

This:
- Creates a report
- Automatically commits to your GitHub repo
- Pushes with message: `ai-news-{date}: Daily AI news summary`
- Updates repository history daily

**Setup:**
```
gh auth login --web  # One-time authentication
export GH_TOKEN=your_token  # Or set in environment
```

### Customized News Gathering
Tailor what gets collected:
> "Create AI news focusing on generative AI and enterprise AI startups, with 5 items per category"

Customize:
- **Categories** — What topics to focus on (tech, business, specific companies)
- **Item count** — How many news items to collect
- **Keywords** — Specific search terms or companies
- **Output** — Format (HTML only currently) and save location

## v2.0 New Features ✨

### Error Handling & Logging
- **Error Recovery** — If news search fails, tries alternative sources
- **Automatic Logging** — Creates `logs/YYYY-MM-DD.log` for each run
- **Failure Notifications** — Shows clear error messages when something goes wrong
- **Graceful Degradation** — If some news can't be found, still generates report with available news

**Log file example:**
```
2026-06-11 08:00:15 - Starting AI news collection
2026-06-11 08:00:22 - Searching: new AI model release 2026
2026-06-11 08:00:35 - Found 8 articles ✓
2026-06-11 08:00:42 - Generating HTML report
2026-06-11 08:00:45 - SUCCESS: ai-news-20260611.html saved
2026-06-11 08:00:46 - Pushing to GitHub...
2026-06-11 08:00:52 - GitHub push successful ✓
```

### GitHub Integration
- **Auto-commit** — Each report automatically committed with timestamp
- **Smart pushing** — Handles authentication and push errors gracefully
- **Repository tracking** — Maintains history of all daily reports
- **Configurable** — Easy to enable/disable GitHub integration

## Configuration Options

### Built-in Defaults
- **Schedule:** 8:00 AM daily (customizable)
- **Categories:** Technology/Models + Business/Industry (balanced 50/50)
- **Items:** 6-8 total (3-4 per category)
- **Keywords:** OpenAI, Anthropic, Google, LLM, AI model, benchmark, funding, acquisition
- **Output:** HTML format, saved to `Desktop\kim\`
- **GitHub:** No auto-push by default (optional)
- **Logging:** Enabled by default in `logs/` directory

### How to Customize

**Change the schedule:**
- Current: `0 8 * * *` (8:00 AM daily)
- Modify in Scheduled Tasks settings
- Examples: `0 9 * * 1-5` (weekdays at 9 AM), `0 6 * * *` (6 AM daily)

**Change news sources or keywords:**
The skill searches these by default:
- "new AI model release 2026"
- "LLM benchmark performance"
- "AI startup funding"
- "AI acquisition news"

You can request different keywords when invoking the skill.

**Change output location:**
By default: `C:\Users\Admin\Desktop\kim\`
Mention a different path when requesting the report.

**Enable/Disable GitHub push:**
- Enable: "Push to GitHub automatically"
- Disable: "Don't push to GitHub"

## Technical Details

### What You Get

**HTML Report Structure:**
```
🤖 Today's AI Digest
├─ Headline (3 top stories)
├─ Tech & Models (3-4 curated news items)
│  └─ What happened + Why it matters
├─ Business & Industry (3-4 curated news items)
│  └─ What happened + Why it matters
├─ Trending Keywords
└─ Daily Sentiment Summary
```

**File naming:** `ai-news-YYYYMMDD.html`
- Example: `ai-news-20260611.html`

**Log files:** `logs/YYYY-MM-DD.log`
- One log per day
- Contains timestamps and status messages

**File size:** ~10-15 KB (lean HTML, no heavy dependencies)

### Design Features

- **Responsive layout** — Readable on desktop and mobile
- **Color-coded sections** — Blue for tech, green for business
- **Easy to read** — Non-technical language, clear hierarchy
- **Print-friendly** — Looks good on paper too
- **Self-contained** — No external dependencies, opens in any browser
- **Error tracking** — Logs help diagnose any issues

## Troubleshooting

### "Report not generating at scheduled time"
- Make sure Claude Code app is running
- Check scheduled tasks in sidebar
- Check `logs/` directory for error messages
- Consider Windows Task Scheduler or GitHub Actions as alternatives

### "GitHub push failed"
- Check GitHub CLI is installed: `gh --version`
- Authenticate: `gh auth login --web`
- Check repository URL is correct
- Review logs for detailed error

### "Same news every day"
- That's normal! AI world moves slowly some days
- The skill searches fresh each time
- Check GitHub repo for history of what's changed day-to-day

### "Logs directory not found"
- Skill creates it automatically
- If missing, check write permissions on Desktop/kim folder

## What's Next?

This skill is actively maintained. Coming soon:
- [ ] Dark mode for HTML reports
- [ ] Email delivery of reports
- [ ] RSS feed integration
- [ ] Custom filtering/exclusions
- [ ] Slack/Discord notifications
- [ ] Trend analysis across multiple days
- [ ] App auto-run when closed (Windows Task Scheduler)
- [ ] Configuration file support (JSON)

## Version History

**v2.0** (Current)
- ✨ GitHub auto-push feature
- ✨ Error handling & logging system
- 🐛 Improved error recovery

**v1.0** (Initial)
- Basic AI news collection
- HTML report generation
- Scheduled task support

Have feedback or feature requests? Let me know!
