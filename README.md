# Multi-Agent Research Assistant (n8n)

A planner agent that splits a research question into subtasks, runs specialist sub-agents in parallel, and writes one cited research report.

This is an n8n port of my original Python project, **MCP-Powered Multi-Agent Research Assistant** (Python, Claude API, MCP SDK, pytest).

## How it works

```
User question
     |
     v
Public chat page (n8n Chat Trigger)
     |
     v
Planner agent  --- Research Planning & Routing skill
     |   splits the question into 2-6 subtasks
     |
     +--> Market data sub-agent  (Market Data Research skill + web search)
     +--> Web research sub-agent (Web Research skill + web search)
     |        run in parallel
     v
Report Synthesis skill --> cited report back to the chat
```

**Report format:** Summary, Research plan, Market data table, Key findings, Analysis, Gaps & caveats, Sources. Market reports end with a "Not financial advice" note.

## Repo layout

| Path | What it is |
| --- | --- |
| `agent/agent-config.json` | Agent model, instructions, memory, and web search settings |
| `agent/skills/*.md` | The four skills the planner and sub-agents follow |
| `workflows/public-research-chat.json` | n8n workflow: public chat page that forwards messages to the agent |

## Set it up in your own n8n

1. Create a new n8n Agent. Copy the instructions from `agent/agent-config.json`, add the four skills from `agent/skills/`, and turn on web search.
2. Publish the agent and copy its ID.
3. In n8n, import `workflows/public-research-chat.json`.
4. Open the **Ask Research Agent** node and replace `REPLACE_WITH_YOUR_AGENT_ID` with your agent ID.
5. Publish the workflow. The public chat URL is `https://<your-n8n>/webhook/<chat-webhook-id>/chat`.

## Differences from the original Python version

- Market data comes from web search, so prices may be delayed by about a day. The original used custom MCP servers.
- It runs on Claude only. The original also supported Gemini and Groq.
- There is no pytest suite. Testing was done through n8n test runs.

## Tech

n8n Agents, sub-agent delegation, agent skills, Claude with native web search, n8n Chat Trigger.
