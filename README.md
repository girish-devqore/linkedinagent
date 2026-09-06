# LinkedIn Agent

A Claude Code agent skill that drafts LinkedIn posts for [DevQore](https://devqore.io)'s
company page and submits them to Metricool's review queue for approval before
publishing.

## What it does

The agent, defined in [`devqore-linkedin-poster.md`](devqore-linkedin-poster.md),
rotates across DevQore's three focus areas — Core Software Development, DevOps &
Cloud Services, and QA & Testing — and drafts one post at a time in an
engineering-perspective voice (not a sales pitch).

Each run:

1. Checks Metricool for posts already scheduled in the next few days, so it
   doesn't repeat a topic or focus area.
2. Picks a focus area and angle that hasn't been covered recently.
3. Drafts the post text.
4. Picks a strong publish time (or uses one you specify).
5. Submits the post to Metricool's review queue — it never publishes directly.

## Requirements

- [Claude Code](https://claude.com/claude-code) with the Metricool MCP connector
  configured.
- A Metricool account with the DevQore blog/brand set up.

## Usage

Place `devqore-linkedin-poster.md` in your Claude Code agents directory and
invoke it directly, or schedule it to run 2-3 times per weekday.
