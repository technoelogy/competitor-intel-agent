# Competitor-Intel Agent

A continuous competitive intelligence system for Indian consumer health, OTC, and pharma brands. Pulls structured product data and verbatim customer reviews from e-pharmacies (1mg, PharmEasy, Netmeds), Amazon India, and brand DTC sites into a single Google Sheet, refreshed as often as you need.

Built because most competitive audits take 2-3 weeks of analyst time and arrive stale. The verbatim capture is the point. For OTC and pharma, exact claim and review language matters for positioning, regulatory monitoring, and insight work.

Status: live, running on self-hosted n8n at technoelogy.n8ns.host. Tested on live competitive sets in diabetes nutrition, ashwagandha, OTC digestives.

## What it does

Give the agent a product URL. It will:

1. Scrape the page using Firecrawl with stealth proxy (handles Amazon.in and Shopify anti-bot blocks)
2. Extract structured fields using OpenAI gpt-4o-mini: product name, brand, price in ₹, rating, claims verbatim, source URL
3. For review pages, extract per-review fields: reviewer, star rating, title, body verbatim, review date
4. Append rows to a Google Sheet

## Architecture
