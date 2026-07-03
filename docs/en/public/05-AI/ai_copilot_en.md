# AI Copilot — Optional Cloud-Assisted Analysis

The **AI Copilot** is an optional, opt-in feature that gives you a natural-language, expert-style explanation of a specific alert — what it means, how serious it is, and what to do next.

Unlike the local AI/ML engine (which runs entirely on your device), the AI Copilot is **cloud-assisted**: it sends the details of a single alert to an EU-hosted service (nyroxis.ai) that uses a large language model to produce the analysis. Because this involves sending data off the device, Nyroxis treats it as a deliberate, transparent choice — it is **disabled by default** and never runs automatically.

---

## Local AI vs. AI Copilot

Nyroxis has two separate, clearly different intelligence layers. It is important not to confuse them:

| | Local AI/ML Engine | AI Copilot |
|---|--------------------|------------|
| Where it runs | Entirely on your device | EU-hosted cloud service (nyroxis.ai) |
| Network | None — fully offline | Sends one alert's data over HTTPS |
| When it runs | On demand, locally | Only when you click "Analyze" on an alert |
| Enabled by default | Yes (offline) | No — opt-in only |
| What it does | Isolation Forest + statistical anomaly detection | Natural-language explanation of a single alert |

The local engine is covered on the **Local AI/ML** pages. This page is only about the optional cloud Copilot.

---

## How It Works

1. You connect an AI Copilot account from **Settings → AI Copilot** and accept an explicit consent checkbox.
2. You open a specific alert and click **Analyze**.
3. The Dashboard sends that single alert's information to nyroxis.ai.
4. The service returns a natural-language analysis in your interface language (English, French, or German), including MITRE ATT&CK context and recommended next steps.

There is no background transmission, no bulk upload, and no automatic analysis. Each analysis is a single alert, sent only when you ask for it. You can disconnect at any time, which removes the local credential.

---

## What Is Sent — and What Is Not

When you analyze an alert, the Dashboard sends to nyroxis.ai:

- The alert metadata (rule, severity, channel, timestamp, status)
- The source IP associated with the alert
- Your own note on the alert (if any)
- The definition of the rule that matched

**Never sent:** your raw Windows event logs, the encrypted event database, or any local AI/ML output.

On the server side, nyroxis.ai is hosted on EU infrastructure. Before an analysis record is stored, the source IP is replaced with a one-way hash and common path/username patterns in the note are masked. To produce its analysis, the service does process the alert information described above — this is the inherent trade-off of any cloud-assisted analysis, and it is exactly why the feature is opt-in and per-alert rather than automatic.

---

## Plans

The AI Copilot is a separate, optional subscription with a free tier, so you can try it at no cost:

| Plan | Price | Analyses per month |
|------|-------|--------------------|
| Free | €0 | 30 |
| Pro | €29 / month | 1,000 |
| Team | €59 / month | 5,000 |
| Business | €149 / month | 15,000 |

All AI Copilot plans are EU-hosted and GDPR-aligned. The desktop Nyroxis platform and the AI Copilot subscription are independent — the platform is fully functional without any AI Copilot subscription. Pricing and limits are indicative and may change; see [www.nyroxis.com](https://www.nyroxis.com) for current details.

---

## Summary

The AI Copilot brings an expert, natural-language second opinion to any alert — offered transparently, hosted in the EU, opt-in, and entirely under your control. If you prefer a fully offline setup, simply leave it disabled: everything else in Nyroxis continues to work on-device.
