# Weekly Ad Report with n8n and an LLM

I built this workflow to stop writing weekly client reports by hand. It cut my reporting from **6 to 8 hours to under 90 minutes**. A person still reads and approves every report before it goes out.

## The idea
1. **Collect:** a schedule trigger pulls last week's numbers (spend, results, cost per result) from the ad data source.
2. **Check:** simple rules flag anything unusual, such as a spend spike or a sudden drop in results.
3. **Draft:** an LLM turns the numbers and flags into a plain-language draft: what happened, what changed, what to do next.
4. **Review:** the draft goes to a human, who edits and approves it. Nothing is sent automatically.

## Why a human approves
An LLM can sound sure and still be wrong. So every draft is compared with the source numbers before it is used.

## What is in this repo
- `workflow.json`: the exported n8n workflow *(add your export here, with API keys, client names and account IDs removed)*
- `prompt.md`: the instructions the LLM gets *(add yours)*
- `sample-report.md`: an example report using made-up numbers *(add one)*

## Stack
n8n, webhooks and API calls, an LLM, Google Sheets.

Related project: [Spend Watch](https://github.com/AnkitS96/spend-watch), a demo that flags spend spikes, creative fatigue and tracking gaps.

*Built by [Ankit Singh](https://www.linkedin.com/in/ankit-singh-wpl).*
