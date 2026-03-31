# XPOZ Cookbooks

Jupyter notebooks showing how to use [XPOZ](https://xpoz.ai) social intelligence MCP server with popular AI platforms.

## Notebooks

| Notebook | AI Platform | Description |
|----------|-------------|-------------|
| [social-intelligence-with-xpoz-claude.ipynb](social-intelligence-with-xpoz-claude.ipynb) | Claude (Anthropic) | Brand sentiment, competitive intel, influencer discovery, event monitoring |
| [social-intelligence-with-xpoz-gemini.ipynb](social-intelligence-with-xpoz-gemini.ipynb) | Gemini (Google) | Same structure adapted for Gemini API |

## What's Covered

Each notebook connects to XPOZ via MCP and walks through 5 real-world use cases:

1. **Brand Sentiment Analysis** — Fetch social posts via MCP and classify sentiment
2. **Competitive Intelligence** — Compare two brands' social footprint
3. **Influencer Discovery** — Find top voices on any topic
4. **Real-time Event Monitoring** — Social signals for prediction markets

## Prerequisites

- **XPOZ API Key** — Free at [xpoz.ai](https://xpoz.ai) (100K results/month)
- **AI Platform Key** — Anthropic or Google AI

## Quick Start

```bash
pip install mcp anthropic          # For Claude notebook
pip install mcp google-generativeai  # For Gemini notebook
```

The notebooks connect to the XPOZ MCP server at `https://mcp.xpoz.ai/mcp` — no local server setup required.

## XPOZ MCP Tools Used

| Tool | Description |
|------|-------------|
| `countTweets` | Count tweets matching a query in a date range |
| `getTwitterPostsByKeywords` | Search tweets by keywords with engagement metrics |
| `getRedditPostsByKeywords` | Search Reddit posts by keywords |
| `getTwitterUsersByKeywords` | Find users who posted about a topic |
| `getTwitterPostsByAuthor` | Get recent posts from a specific user |

Full tool list (29+ tools across Twitter, Instagram, Reddit, TikTok) available after connecting to the MCP server.

## MCP Setup for Claude Desktop / Claude Code

You can also use XPOZ as an MCP tool directly in Claude Desktop or Claude Code — no notebook needed.

**Claude Desktop** — add to `~/Library/Application Support/Claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "xpoz": {
      "url": "https://mcp.xpoz.ai/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_XPOZ_API_KEY"
      }
    }
  }
}
```

**Claude Code** — run:

```bash
claude mcp add xpoz https://mcp.xpoz.ai/mcp \
  --header "Authorization: Bearer YOUR_XPOZ_API_KEY"
```

See all setup options at [xpoz.ai/install](https://xpoz.ai/install).

---

## Alternative: Python SDK

If you prefer a direct Python API instead of MCP, XPOZ also offers a Python SDK:

```bash
pip install xpoz
```

```python
from xpoz import XpozClient

xpoz = XpozClient()  # Uses XPOZ_API_KEY env var

# Search tweets
results = xpoz.twitter.search_posts(
    "NVIDIA",
    start_date="2026-03-24",
    limit=50,
    fields=["text", "author_username", "like_count", "retweet_count"]
)

# Count volume
count = xpoz.twitter.count_posts("NVIDIA", start_date="2026-03-24")

# Find influencers
users = xpoz.twitter.get_users_by_keywords(
    "AI ethics",
    start_date="2026-03-01",
    limit=20,
    fields=["username", "followers_count", "relevant_tweets_count"]
)

xpoz.close()
```

The SDK wraps the same data as the MCP tools — use whichever fits your workflow.

## License

MIT
