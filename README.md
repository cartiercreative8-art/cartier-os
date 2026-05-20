# CartierOS — Client Automation Suite

> Productized 4-workflow n8n automation system. Deployed to real clients. Runs in under 2 hours from a single template.

---

## What It Is

CartierOS is the core product of CartierCreative — a complete AI-powered business operating system for local service businesses (plumbers, roofers, HVAC, handymen, landscapers). 

One template. Any client. Live in under 2 hours.

**What gets deployed per client:**
- Professional website (Netlify)
- 4-workflow n8n automation suite
- Google Sheets CRM
- Slack workspace with dedicated channels
- Jarvis AI agent (Claude API)
- Daily briefings + automated follow-up

**Pricing:** $1,500–$2,000 setup + $299/month recurring

---

## The 4-Workflow Architecture

### Workflow 1 — Public Lead Capture
```
Website form submission
       ↓
   Webhook trigger
       ↓
  Parse + validate
       ↓
 Append to CRM (Sheets)
       ↓
Slack alert → #leads channel
```

### Workflow 2 — Private Manual Entry
```
Slack command from owner
       ↓
   Webhook trigger
       ↓
  AI parses message
       ↓
 Append to CRM (Sheets)
       ↓
 Confirmation in Slack
```

### Workflow 3 — Daily Morning Briefing
```
Cron: 0 13 * * * (7AM MT)
       ↓
 Pull all open leads from CRM
       ↓
 Claude AI writes briefing summary
       ↓
 Post to #briefing in Slack
```

### Workflow 4 — Automated Follow-Up
```
Cron: 0 15 * * * (9AM MT)
       ↓
 Scan CRM for leads needing follow-up
       ↓
 Claude AI writes personalized message
       ↓
 Post reminders to #follow-up in Slack
```

---

## Tech Stack

- **Automation:** n8n Cloud
- **AI:** Claude API (Anthropic) — lead parsing, briefing generation, follow-up writing
- **CRM:** Google Sheets (multi-tab: Dashboard, Leads, Follow-Ups, Active Clients)
- **Notifications:** Slack (webhooks + bot)
- **Website:** Netlify
- **Triggers:** Webhooks + Cron (`runOnceForAllItems` mode)

---

## Lead ID System

Every lead gets a unique ID on capture:
```
[CLIENT_PREFIX]-MMDDHHMM

Examples:
  MO-05051423   → Measure Once, May 5th at 2:23PM
  DP-05191100   → DeWalt Plumbing, May 19th at 11:00AM
```

---

## Active Deployments

| Client | Industry | Status |
|---|---|---|
| Jeremy Halladay — Measure Once Handyman | Handyman | ✅ Live |
| Joe Castro — Super Handyman Co. | Handyman | ✅ Live |
| Paul DeWalt — DeWalt Plumbing Services | Plumbing | ✅ Live |

---

## Deployment Checklist

- [ ] Clone 4-workflow template in n8n
- [ ] Update webhook URLs
- [ ] Update Slack channel IDs
- [ ] Link Google Sheets CRM (client-specific)
- [ ] Link Gmail credentials
- [ ] Set lead prefix
- [ ] Activate all 4 workflows
- [ ] Test end-to-end with live lead

**Total time: ~2 hours**

---

## Command Center

CartierOS is managed through [CartierHQ](https://github.com/cartiercreative8-art/cartier-hq), the React dashboard that provides real-time visibility across all client deployments.
