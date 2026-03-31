# Social Intelligence with XPOZ MCP + Gemini

Use [XPOZ](https://xpoz.ai) — a social intelligence MCP server with 1.5B+ indexed posts across Twitter, Instagram, Reddit & TikTok — together with Google's Gemini for real-time social media analysis.

<a target="_blank" href="https://colab.research.google.com/github/XPOZpublic/xpoz-cookbooks/blob/main/gemini/social-intelligence-with-xpoz-gemini.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

## What you'll learn

| Section | Description |
|---------|-------------|
| **Brand Sentiment Analysis** | Fetch social posts via MCP and classify sentiment with Gemini |
| **Competitive Intelligence** | Compare two brands' social footprint — volume, sentiment, share of voice |
| **Influencer Discovery** | Find the top voices on any topic using engagement and follower data |
| **Real-time Event Monitoring** | Social sentiment overlay for prediction markets and crisis detection |
| **HTML Report Generation** | Export a styled brand sentiment report to HTML |

## How it works

1. Connect to the XPOZ MCP server (`https://mcp.xpoz.ai/mcp`)
2. Call tools like `getTwitterPostsByKeywords`, `countTweets`, `getRedditPostsByKeywords`
3. Feed the results to Gemini for structured analysis

No local MCP server setup — XPOZ runs as a remote MCP endpoint.

## Prerequisites

- **XPOZ API Key** — Free at [xpoz.ai](https://xpoz.ai) (100K results/month)
- **Google AI API Key** — [aistudio.google.com](https://aistudio.google.com)

## Quick Start

```bash
pip install mcp google-generativeai
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

## License

MIT
