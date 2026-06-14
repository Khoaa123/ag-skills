---
description: Run a web performance audit via the performance-optimizer persona.
---

# /webperf - Web Performance Audit

$ARGUMENTS

---

## 🔴 CRITICAL RULES

1. **Web Apps Only:** Only run this audit on browser-facing web applications.
2. **Metric-Honesty:** Never fabricate Core Web Vitals (LCP, INP, CLS) or Lighthouse scores. If no measurement data is provided, scorecard fields must remain "not measured".
3. **Sourced Values:** Tag every scorecard item with its source (Field CrUX, Lab Lighthouse, DevTools trace).

---

## Audit Modes

- **Quick mode:** Scan source code for performance anti-patterns (e.g. over-memoization, missing image dimensions, rendering loops). Mark scorecard as `not measured` and findings as `potential impact`.
- **Deep mode:** Activated when Lighthouse JSON reports, PageSpeed Insights API responses, CrUX data, or DevTools traces are provided, or via live DevTools MCP capture. Fill scorecard using these verified sources.

---

## Execution

Spawn the `performance-optimizer` agent (or call the tool directly) passing the file paths, URL, or performance report JSON files. The auditor will return:
1. Core Web Vitals Scorecard.
2. Ranked findings (Critical, High, Medium, Low, Info) with exact recommendations.
3. Positive observations.
4. Proactive recommendations.
