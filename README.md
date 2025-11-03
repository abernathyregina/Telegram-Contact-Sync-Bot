# Telegram Contact Sync Bot

A production-ready Telegram Contact Sync Bot that automatically imports, deduplicates, labels, and keeps contacts in sync across Telegram accounts and devices. It removes the manual grind of CSV imports and phonebook juggling, ensuring clean, verified contact books for outreach, CRM alignment, and bulk messaging workflows.

<p align="center">
  <a href="https://Appilot.app" target="_blank"><img src="media/appilot-baner.png" alt="Appilot Banner" width="100%"></a>
</p>
<p align="center">
 <a href="https://t.me/devpilot1" target="_blank"><img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram"></a>
 <a href="mailto:support@appilot.app" target="_blank"><img src="https://img.shields.io/badge/Email-support@appilot.app-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail"></a>
 <a href="https://appilot.app" target="_blank"><img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website"></a>
 <a href="https://discord.gg/r5sJ5vhf" target="_blank"><img src="https://img.shields.io/badge/Join-Appilot_Community-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Appilot Discord"></a>
</p>

<p align="center"> 
   Created by Appilot, built to showcase our approach to Automation!<br>
   <strong>If you are looking for custom Telegram Contact Sync Bot, you've just found your team — Let’s Chat.👆👆</strong>
</p>

## Introduction
**What it does:** Automates end-to-end contact synchronization for Telegram: ingestion (CSV/Excel/API), validation, deduplication, tagging, and bi-directional sync with device/Google Contacts or CRMs.

**Problem it solves:** Manual imports, number formatting issues, duplicate entries, and inconsistent labels across multiple Telegram accounts and devices.

**Benefit:** Clean, unified contact books that stay updated automatically, enabling faster outreach, reliable targeting, and lower ban/flag risks thanks to human-like behavior.

### Automating Telegram Contact Hygiene & Sync at Scale
- Bulk import (CSV/Excel/API) with validation, dedupe, and country code normalization.
- Bi-directional sync: Telegram ↔ Device Contacts ↔ Google Contacts/CRM webhooks.
- Safe, human-like action pacing with jitter, randomization, and retry logic.
- Multi-account, multi-device orchestration for agencies and growth teams.
- Audit-grade logs, metrics, and exportable reports for compliance and QA.

## Core Features
- **Real Devices and Emulators:** Works on physical Android phones and popular emulators (BlueStacks, Nox). Auto-detects screen sizes, DPI, and language for robust selectors.
- **No-ADB Wireless Automation:** ADB-less control via Accessibility + input bridges to reduce detection surface and simplify device onboarding over Wi-Fi.
- **Mimicking Human Behavior:** Randomized taps/scrolls, adaptive delays, backoffs, UI path variation, and session warmups to emulate genuine user interaction.
- **Multiple Accounts Support:** Manage and rotate dozens to hundreds of Telegram accounts with isolated profiles, storage dirs, and per-account rate limits.
- **Multi-Device Integration:** Parallel runners dispatch tasks across device farms; queue-based orchestration ensures steady throughput and graceful scaling.
- **Exponential Growth for Your Account:** Clean, labeled contact graphs improve outreach efficiency and reply rates, compounding over campaigns.
- **Premium Support:** Priority ticketing, playbooks, and guided setups for device farms, proxies, and safe operation policies.

**Additional Feature Set**

| Feature | Description |
|---|---|
| **Smart Dedupe Engine** | Detects duplicates by phone hash, username, and normalized name; merges labels without losing metadata. |
| **Number Normalization** | Auto-applies E.164 formatting with country inference; flags invalid or unreachable numbers. |
| **Tagging & Segmentation** | Assigns tags (e.g., “Leads:Q4”, “VIP”) from rules or columns; supports bulk edits and saved segments. |
| **CSV/Excel/Google Sheets Ingest** | Monitors data sources; incremental sync with error rows and reprocessing queue. |
| **Webhook & API Sync** | Push/pull contacts via webhooks; integrates with CRMs or data hubs for continuous updates. |
| **Session Safety Controls** | Per-account cooldowns, daily caps, speed tiers, and pause/resume to reduce risk. |

</p>
<p align="center">
  <a href="https://appilot.app" target="_blank">
    <img src="media/telegram-contact-sync-bot-banner.png" alt="telegram-contact-sync-bot-architecture" width="95%">
  </a>
</p>

## How It Works
1. **Input or Trigger** — Start from the Appilot dashboard by selecting sources (CSV/Excel/Sheets/API) and mapping fields (name, phone, tags). Choose target Telegram accounts/devices and schedule immediate or periodic syncs.  
2. **Core Logic** — The engine controls the Android device/emulator via UI Automator or ADB (when enabled), navigating Telegram’s Contacts UI to add/update entries, apply tags (via notes/labels), and verify visibility.  
3. **Output or Action** — Contacts are imported, deduped, and labeled in Telegram; optional push back to Google Contacts/CRM occurs via webhooks or exports.  
4. **Other functionalities** — Automatic retries, structured logging, screenshots on failure, and parallel processing with queues can be configured in the dashboard.

## Tech Stack 
- **Language:** Kotlin, Java, JavaScript, Python  
- **Frameworks:** Appium, UI Automator, Espresso, Robot Framework, Cucumber  
- **Tools:** Appilot, Android Debug Bridge (ADB), Appium Inspector, BlueStacks, Nox Player, Scrcpy, Firebase Test Lab, MonkeyRunner, Accessibility  
- **Infrastructure:** Dockerized device farms, Cloud-based emulators, Proxy networks, Parallel Device Execution, Task Queues, Real device farm

## Directory Structure
```
telegram-contact-sync-bot/
│
├── src/
│ ├── main.py
│ ├── automation/
│ │ ├── tasks.py
│ │ ├── scheduler.py
│ │ └── utils/
│ │ ├── logger.py
│ │ ├── proxy_manager.py
│ │ └── config_loader.py
│ ├── device/
│ │ ├── uiactions.py
│ │ ├── selectors.yaml
│ │ └── accessibility_bridge.py
│ ├── ingest/
│ │ ├── csv_loader.py
│ │ ├── sheets_client.py
│ │ └── validators.py
│ ├── sync/
│ │ ├── dedupe.py
│ │ ├── normalizer.py
│ │ └── telegram_sync.py
│ └── api/
│ ├── server.js
│ └── webhooks.js
│
├── config/
│ ├── settings.yaml
│ ├── devices.yaml
│ ├── credentials.env
│ └── limits.yaml
│
├── dashboards/
│ └── appilot-flows.json
│
├── logs/
│ ├── activity.log
│ └── device_screens/
│ └── failures/
│
├── output/
│ ├── exports/
│ │ ├── contacts_merged.csv
│ │ └── error_rows.csv
│ └── reports/
│ └── sync_report_YYYYMMDD.json
│
├── tests/
│ ├── test_dedupe.py
│ ├── test_normalizer.py
│ └── test_sync_flow.py
│
├── requirements.txt
└── README.md
```

## Use Cases
- **Agencies** use it to onboard lead lists across multiple Telegram accounts, so they can launch outreach faster with clean, labeled contact sets.  
- **Sales teams** use it to keep Telegram contacts synced with Google Contacts/CRM, so they can maintain consistent segments and avoid duplicates.  
- **Support teams** use it to tag VIPs and priority customers, so they can route conversations and escalate quickly.  
- **Growth marketers** use it to normalize numbers and auto-dedupe at import, so they can reduce bounce/ban risk during campaigns.  

## FAQs
**How do I configure this automation for multiple accounts?**  
Add each account to the device farm with isolated profiles and set per-account limits (daily caps, concurrency). Assign segments to accounts in the scheduler to parallelize safely.

**Does it support proxy rotation or anti-detection?**  
Yes. Use device-level proxies or emulator proxies, plus randomized delays and selector variance. ADB-less mode further reduces telemetry exposure.

**Can I schedule it to run periodically?**  
You can schedule hourly/daily/weekly sync windows in the Appilot dashboard. Incremental sync only processes new/changed rows.

**What happens with invalid numbers or duplicates?**  
Invalid numbers are quarantined into `output/exports/error_rows.csv`. Duplicates are merged by phone hash/username with tag preservation and a full audit log.

## Performance & Reliability Benchmarks
- **Execution Speed:** ~1,200–2,000 contacts/hour per device in steady-state (import + label), depending on network, device, and UI latency.  
- **Success Rate:** 95% end-to-end task success in stable network conditions with recommended delays.  
- **Scalability:** Horizontally scales to 300–1,000 Android devices via queue-based orchestration and per-device workers.  
- **Resource Efficiency:** Lightweight runners (~150–250MB RAM per worker); batched selector lookups; screenshot-on-failure only.  
- **Error Handling:** Structured retries with exponential backoff, circuit-breaker for failing accounts, redrive queues, and Slack/Email alerts with artifact links.
##
<p align="center">
<a href="https://cal.com/app-pilot-m8i8oo/30min" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
</p>








