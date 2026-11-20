# YouTube Comments Scraper: YouTube Scraper API for Python & Node.js (2026)

Scrape comments and replies from any public YouTube video: text, author, likes, reply count and date. No API key or login needed. Export to JSON, CSV or Excel.

**[▶ Try the YouTube Comments Scraper free on Scrapely](https://scrape.ly/store/echofield/youtube-comments-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape YouTube data with the [YouTube Comments Scraper](https://scrape.ly/store/echofield/youtube-comments-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the youtube scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this YouTube scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/echofield/youtube-comments-scraper) or from your code with the SDK.
- **Structured youtube data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $1.70 per 1,000 comment results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when YouTube changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What YouTube data can you extract?

Scrape comments and replies from any public YouTube video: text, author, likes, reply count and date. No API key or login needed. Export to JSON, CSV or Excel.

| Output field |
|---|
| `author` |
| `comment` |
| `type` |
| `voteCount` |
| `replyCount` |
| `publishedTimeText` |
| `hasCreatorHeart` |
| `authorIsChannelOwner` |
| `title` |
| `pageUrl` |

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('echofield/youtube-comments-scraper').call({"startUrls": [{"url": "https://www.youtube.com/watch?v=dQw4w9WgXcQ"}], "maxComments": 10, "sortCommentsBy": "NEWEST_FIRST", "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["DATACENTER"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('echofield/youtube-comments-scraper').call(run_input={ "startUrls": [ { "url": "https://www.youtube.com/watch?v=dQw4w9WgXcQ" } ], "maxComments": 10, "sortCommentsBy": "NEWEST_FIRST", "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "DATACENTER" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/echofield~youtube-comments-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "startUrls": [
    {
      "url": "https://www.youtube.com/watch?v=dQw4w9WgXcQ"
    }
  ],
  "maxComments": 10,
  "sortCommentsBy": "NEWEST_FIRST",
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "DATACENTER"
    ]
  }
}
```

See every input option on the [YouTube Comments Scraper page](https://scrape.ly/store/echofield/youtube-comments-scraper).

## Pricing

**$1.70 per 1,000 comment results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/echofield/youtube-comments-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape YouTube with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape YouTube with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a youtube scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/echofield~youtube-comments-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping YouTube legal?** This scraper collects publicly available data. Check YouTube's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Related YouTube scrapers

- [YouTube Scraper](https://github.com/alexrosuleks/youtube-scraper): Scrape public YouTube videos, channels, playlists, hashtags, and search results. Get titles, views, likes, durations,…
- [YouTube Shorts Scraper](https://github.com/alexrosuleks/youtube-shorts-scraper): Scrape public YouTube Shorts from one or more channels: titles, view and like counts, comment counts, durations,…
- [YouTube Video Downloader](https://github.com/alexrosuleks/youtube-video-downloader): Download public YouTube videos and Shorts as MP4 or MP3 in your chosen quality, with title, channel and duration. No…

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** youtube comments scraper, youtube scraper, youtube scraper api, youtube scraper python, youtube scraper node.js,
scrape youtube, youtube data extraction, youtube crawler, youtube api, export youtube data to csv, youtube-comments-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/echofield/youtube-comments-scraper).
