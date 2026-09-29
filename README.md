# Amazon Product Research and Regional Price Comparison with Magnetic Proxy | Agent Skill

A sourced comparison matrix that shows which listings and variants are genuinely comparable across regions.

This public Agent Skill addresses **amazon product research** with Magnetic Proxy residential routing where the job requires it. It is an independent use-case package, not an MCP or a claim that the product has completed an authenticated task.

**Product role:** Magnetic Proxy is the routing and observed-location layer for any live regional check in this skill. Without an authorized account and verified exit, the agent may prepare or analyze supplied data but cannot claim a live regional observation. The proxy does not grant data-access rights.

## What you can ask an agent to do

> Compare the public Amazon US and UK listings for these two blender models, including the 1.5 L variant, seller, displayed price, shipping, and availability.

**Example result (illustrative, not a live run):** Comparison matrix: Model A, 1.5 L: US listing observed at USD 89 with seller X; UK listing observed at GBP 82 with seller Y. UK shipping to the requested postcode was not displayed, so no landed-price winner is declared. Model B UK page presented a 1.2 L variant and is excluded from equivalent-price comparison.

## Install

```bash
npx skills add MagneticProxy/magneticproxy-amazon-product-research-skill --skill amazon-product-research
```

Or copy this prompt into an agent that supports skill installation:

> Install the `amazon-product-research` skill from https://github.com/MagneticProxy/magneticproxy-amazon-product-research-skill and use it to help with: [describe your task]. Confirm installation, ask for my authorized inputs, and show me the proposed output before any external action.

Read the [skill instructions](skills/amazon-product-research/SKILL.md). The agent needs compatible tools and access to your authenticated account to operate Magnetic Proxy; installation alone does not provide that access.

## Scope and trust

- **Input:** User-approved Amazon product URLs or ASINs, product attributes to compare, target marketplaces/countries, and a small collection scope.
- **Output:** A sourced comparison matrix that shows which listings and variants are genuinely comparable across regions.
- **Product:** [Magnetic Proxy Amazon use case](https://www.magneticproxy.com/use-cases/amazon-proxies) and the [main product skill](https://github.com/MagneticProxy/magneticproxy-residential-proxy-agent-skills).
- **Current verification:** skill format and installation discovery are tested locally. An authenticated live product run has not yet been demonstrated for this repository.

The skill does not authorize purchases, unapproved Amazon scraping, email sending, CRM writes, or publication. Third-party sites and product interfaces can change; the agent must observe the current state and report uncertainty.

## Access and privacy

Amazon collection requires an approved Amazon access route or express permission for the requested scope. When unavailable, work from licensed or user-provided product records and leave live regional collection pending.

Check the destination’s terms, access permission, and rate limits before collection. A public URL and a successful proxy connection are not authorization to scrape. Stop on access denials or challenges; do not rotate to evade them. [Magnetic Proxy documentation](https://www.magneticproxy.com/documentation) explains routing and restricted targets.

## Review checklist

1. Does the agent request the right inputs and distinguish this job from the other use cases?
2. Does it make the product step observable and avoid inventing results?
3. Does the output preserve source rows/URLs, time, uncertainty, and a clear decision for the user?

Feedback and improvements can be filed as a GitHub issue in this repository.
