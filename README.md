# Tech / Startup / Discovery Aggregator

A lightweight Python agent that collects the latest technology news, startup
announcements, and scientific discoveries from free, publicly available
APIs and RSS feeds — no raw HTML scraping, no API keys required for the
core sources.

## Sources

| Category  | Source                                              | Content                          |
|-----------|------------------------------------------------------|-----------------------------------|
| `hn`      | [Hacker News API](https://github.com/HackerNews/API) | Top tech discussions/news        |
| `arxiv`   | [arXiv API](https://arxiv.org/help/api)              | New AI / ML / Robotics papers    |
| `rss`     | TechCrunch, The Verge, Wired, MIT Tech Review, Product Hunt | Startup + tech news        |
| `github`  | [GitHub Search API](https://docs.github.com/en/rest/search) | Trending new repos/tools  |

## Setup

```bash
git clone <your-repo-url>
cd <your-repo-name>
pip install -r requirements.txt
```

## Usage

```bash
# Fetch everything and print a summary
python3 tech_agent.py

# Fetch only one category
python3 tech_agent.py --category rss    # hn | arxiv | rss | github

# Save full results as JSON
python3 tech_agent.py --save results.json
```

## Notes

- All sources are accessed via official APIs or public RSS feeds — this is
  more reliable than HTML scraping (feeds don't break on site redesigns)
  and avoids Terms-of-Service issues.
- GitHub's public search API has a low rate limit for unauthenticated
  requests. To raise it, set a personal access token as an environment
  variable and pass it in the `HEADERS` dict inside `tech_agent.py`
  (`Authorization: token YOUR_TOKEN`).
- Feel free to extend: add keyword filtering, a database sink, a cron
  schedule, or a small web dashboard.

## License

MIT (or your choice — update this section).
