# Social Intelligence with XPOZ MCP + Claude

Use [XPOZ](https://xpoz.ai) — a social intelligence MCP server with 1.5B+ indexed posts across Twitter, Instagram, Reddit & TikTok — together with Claude for real-time social media analysis.

<a target="_blank" href="https://colab.research.google.com/github/XPOZpublic/xpoz-cookbooks/blob/main/claude/social-intelligence-with-xpoz-claude.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

## What you'll learn

| Section | Description |
|---------|-------------|
| **Brand Sentiment Analysis** | Fetch social posts via MCP and classify sentiment with Claude |
| **Competitive Intelligence** | Compare two brands' social footprint — volume, sentiment, share of voice |
| **Influencer Discovery** | Find the top voices on any topic using engagement and follower data |
| **Real-time Event Monitoring** | Social sentiment overlay for prediction markets and crisis detection |
| **HTML Report Generation** | Export a styled brand sentiment report to HTML |

## How it works

1. Connect to the XPOZ MCP server (`https://mcp.xpoz.ai/mcp`)
2. Call tools like `getTwitterPostsByKeywords`, `countTweets`, `getRedditPostsByKeywords`
3. Feed the results to Claude for structured analysis

No local MCP server setup — XPOZ runs as a remote MCP endpoint.

## Prerequisites

- **XPOZ API Key** — Free at [xpoz.ai](https://xpoz.ai) (100K results/month)
- **Anthropic API Key** — [console.anthropic.com](https://console.anthropic.com)

## Quick Start

```bash
pip install mcp anthropic
```

Set your API keys and run the notebook top-to-bottom.

## XPOZ MCP Tools Used

| Tool | Description |
|------|-------------|
| `countTweets` | Count tweets matching a query in a date range |
| `getTwitterPostsByKeywords` | Search tweets by keywords with engagement metrics |
| `getRedditPostsByKeywords` | Search Reddit posts by keywords |
| `getTwitterUsersByKeywords` | Find users who posted about a topic |
| `getTwitterPostsByAuthor` | Get recent posts from a specific user |

Full tool list (29+ tools across Twitter, Instagram, Reddit, TikTok) available after connecting to the MCP server.

## Using XPOZ without a notebook

You can also use XPOZ directly in Claude Desktop or Claude Code:

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

## License

MIT
