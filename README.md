# XPOZ Cookbooks

Jupyter notebooks showing how to use [XPOZ](https://xpoz.ai) social intelligence with popular AI platforms.

## Notebooks

| Notebook | AI Platform | Description |
|----------|-------------|-------------|
| [social-intelligence-with-xpoz-claude.ipynb](social-intelligence-with-xpoz-claude.ipynb) | Claude (Anthropic) | Brand sentiment, competitive intel, influencer discovery, event monitoring |
| [social-intelligence-with-xpoz-gemini.ipynb](social-intelligence-with-xpoz-gemini.ipynb) | Gemini (Google) | Same structure adapted for Gemini API |

## What's Covered

Each notebook walks through 5 real-world use cases:

1. **Brand Sentiment Analysis** — Fetch social posts and classify sentiment
2. **Competitive Intelligence** — Compare two brands' social footprint
3. **Influencer Discovery** — Find top voices on any topic
4. **Real-time Event Monitoring** — Social signals for prediction markets
5. **MCP Setup** — Configure XPOZ as a tool for Claude Desktop / Claude Code

## Prerequisites

- **XPOZ API Key** — Free at [xpoz.ai/get-token](https://xpoz.ai/get-token) (100K results/month)
- **AI Platform Key** — Anthropic or Google AI

## Quick Start

```bash
pip install xpoz anthropic  # For Claude notebook
pip install xpoz google-generativeai  # For Gemini notebook
```

## License

MIT
