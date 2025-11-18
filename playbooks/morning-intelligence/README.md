# Morning Intelligence / Global Briefing

**Entity:** All  
**Frequency:** Daily (6:00 AM UTC)  
**Version:** 1.0.0

## Overview

The Morning Intelligence playbook aggregates and synthesizes market data, news, and competitive intelligence into a comprehensive daily briefing. This autonomous workflow runs every morning to provide actionable insights across crypto, stocks, and macro indicators.

## Inputs

- **Market Data Sources:**
  - Polygon.io API (stocks, forex)
  - CoinGecko/CoinMarketCap (crypto)
  - Federal Reserve Economic Data (FRED)

- **News Feeds:**
  - RSS feeds (TechCrunch, Bloomberg, Reuters)
  - Twitter/X trending topics
  - Reddit sentiment analysis

- **Competitor Monitoring:**
  - Competitor websites (via Firecrawl)
  - Product launches and updates
  - Pricing changes

## Outputs

- **Daily Briefing Report** (Markdown)
  - Market summary and key movements
  - Top news stories with analysis
  - Competitor activity highlights
  - Actionable recommendations

- **Alert Notifications**
  - Critical market events
  - Competitor launches
  - Regulatory changes

## Configuration

```yaml
schedule: "0 6 * * *"  # Daily at 6 AM UTC
entities: ["shards_inc", "shards_labs", "shards_foundation"]
data_sources:
  polygon:
    symbols: ["SPY", "QQQ", "BTC-USD", "ETH-USD"]
  news:
    feeds: ["https://feeds.bloomberg.com/markets/news.rss"]
  competitors:
    urls: ["https://competitor1.com", "https://competitor2.com"]
notifications:
  - type: "email"
    recipients: ["team@shards.inc"]
  - type: "slack"
    channel: "#daily-intelligence"
```

## Success Metrics

- Report delivery time < 5 minutes
- Coverage of 50+ data sources
- 95%+ accuracy in trend identification
- 90%+ stakeholder satisfaction

## Execution Flow

1. **Data Collection** (2 min)
   - Fetch market data from APIs
   - Scrape news feeds
   - Monitor competitor sites

2. **Analysis & Synthesis** (2 min)
   - Identify trends and patterns
   - Summarize key insights
   - Generate recommendations

3. **Report Generation** (1 min)
   - Format as Markdown document
   - Add visualizations (charts, tables)
   - Prepare email/Slack notifications

4. **Distribution** (< 30 sec)
   - Send via email
   - Post to Slack
   - Update Notion page

## Example Output

```markdown
# Daily Intelligence Briefing
**Date:** 2025-11-18  
**Generated:** 06:05 UTC

## Market Summary
- **SPY:** +0.8% (bullish momentum continues)
- **BTC:** $45,234 (+2.3%, breaking resistance)
- **ETH:** $2,456 (+1.8%)

## Top Stories
1. **Fed signals rate pause** - Market reacts positively
2. **Major crypto exchange hack** - $50M stolen, security concerns
3. **AI startup raises $100M** - Competitor activity in our space

## Competitor Activity
- Competitor A launched new pricing tier (20% cheaper)
- Competitor B announced partnership with Fortune 500 company

## Recommendations
- Monitor BTC breakout for potential trading opportunity
- Review our pricing strategy in light of Competitor A changes
- Reach out to Fortune 500 contacts before Competitor B
```

## Version History

- **1.0.0** (2025-11-18): Initial release
