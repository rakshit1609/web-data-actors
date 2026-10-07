# Public web data actors

Fast, HTTP-based (no headless browser) scrapers for public, non-personal web data, published as [Apify](https://apify.com/flyingnimbus) actors. Pay per result. Failed or empty runs are not charged.

| Actor | What you get | Price |
|---|---|---|
| [Google Trends](https://apify.com/flyingnimbus/google-trends-scraper) | Interest over time, by region, related queries | $2 / 1k terms |
| [Google Flights](https://apify.com/flyingnimbus/google-flights-scraper) | Fares, routes and dates | $10 / 1k searches |
| [Google Hotels](https://apify.com/flyingnimbus/google-hotels-scraper) | Hotel prices, ratings, deals | $10 / 1k searches |
| [AI Search Visibility Tracker](https://apify.com/flyingnimbus/ai-search-visibility-tracker) | Brand mentions and rank in Google AI Overviews | $15 / 1k queries |
| [Google Ads Transparency](https://apify.com/flyingnimbus/google-ads-transparency-scraper) | Competitor ad creatives | $0.80 / 1k ads |
| [Google Jobs](https://apify.com/flyingnimbus/google-jobs-scraper) | Job listings with salaries and apply links | $4 / 1k jobs |
| [Google Shopping](https://apify.com/flyingnimbus/google-shopping-scraper) | Product prices, merchants, discounts | $3 / 1k products |
| [Career Site Jobs](https://apify.com/flyingnimbus/career-site-jobs-scraper) | Workday, Greenhouse, Lever, Ashby, SmartRecruiters jobs | $4 / 1k jobs |
| [YouTube Search](https://apify.com/flyingnimbus/youtube-search-intelligence-scraper) | Video titles, views, duration, channels | $1 / 1k videos |
| [Hacker News](https://apify.com/flyingnimbus/hackernews-intelligence-scraper) | Stories, discussions, jobs | $1 / 1k items |

## Use from code

```python
from apify_client import ApifyClient
client = ApifyClient("<YOUR_APIFY_TOKEN>")
run = client.actor("flyingnimbus/google-jobs-scraper").call(run_input={"queries": ["python developer"]})
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

Check each actor's page for its exact input fields.

## Notes
- Public pages only. No logins, no paywall bypass, no email or personal-profile harvesting.
- Output formats: JSON, CSV, Excel via the Apify dataset API.
- Issues or feature requests: open an issue on this repo.
