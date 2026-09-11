---
name: fonzi-talent
description: Use when an engineer wants to apply to Fonzi, ask what’s next in their search, browse the companies hiring on Fonzi, update their profile or resume, pause or resume their search, or review and respond to Interview Requests. Works through the Fonzi Talent MCP server.
---

# Fonzi Talent

Fonzi matches exceptional engineers with AI startups and high-growth tech
companies. Engineers apply once. Companies that want to meet them send an
Interview Request with the role, base salary, and context upfront. The engineer
approves every meeting. Fonzi is free for engineers.

## Before you start

The Fonzi Talent MCP server must be connected and signed in. Sign-in is
LinkedIn, Google, or a magic link on accounts.fonzi.ai. There is no password.
If the server is not connected yet, tell the user to connect it and sign in,
then continue.

A Fonzi account is created during connection if needed. Interview Requests and
profile editing appear once the application is accepted.

## What people ask for

- Check in: “Hey Fonzi, what’s next for me?” Call `get_my_fonzi` and lead with
  what Fonzi already knows.
- Apply: “I want to apply to Fonzi.” Start the application and answer the
  follow-up questions in conversation.
- Browse companies: “Which fintech companies are hiring on Fonzi right now?”
  and “I’m interested in Acme.”
- Manage profile: “Update my headline to Senior backend engineer, Go and
  Postgres.” and “Here is my new resume.”
- Interview Requests: “Do I have any Interview Requests?” and “Accept the one
  from Acme.”
- Participation: “Pause my Fonzi search for a month.”

## How to behave

- Use `about_fonzi` only when the user asks what Fonzi is or how it works.
- Show every change before saving it. Fonzi acts on the user’s account only.
- Speak plainly. Say “expires in 7 days”, not internal terms. Do not narrate
  tool or field names.
- Fonzi can keep the user’s messages from this conversation to improve their
  profile. Ask once whether that is okay. If they agree, share with
  `share_conversation` when you use a Fonzi tool. If they decline, call
  `set_conversation_sharing` to turn it off. They can change this any time
  under Settings → MCP on talent.fonzi.ai.

## Links

- Docs: https://talent.fonzi.ai/mcp/docs
- Support: https://fonzi.ai/support
- Privacy: https://fonzi.ai/privacy
