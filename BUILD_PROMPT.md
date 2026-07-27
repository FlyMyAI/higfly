# The prompt that builds this project

Prerequisite: an AI coding agent (Claude Code / Codex / Antigravity) with the FlyMyAI MCP connected (see README, one line) and a free [flymy.ai](https://app.flymy.ai) account.

## Option A - reproduce THIS on your account (~3 min)

Paste into your agent:

```text
Clone https://github.com/FlyMyAI/higfly and read its README + agent/prompt.md.
Set it up on MY FlyMyAI account using the FlyMyAI MCP tools:
1. Create the agent from agent/prompt.md (pin the flymy-mcp tool, bake the model
   flymyai/bytedance-seedance-2_0-fast-text-to-video). Input schema:
   {prompt, preset?, model?, duration?, resolution?}.
2. Run it ONCE with prompt "a lone astronaut at the edge of a red desert canyon,
   golden hour" and preset "crash-zoom". Verify it returns a real .mp4 URL, then
   freeze it.
3. Tell me the frozen agent id and how to render another clip from it.
Show me the real billed cost of that run via get_execution_price.
```

## Option B - build your own from scratch (what we did)

```text
I want a cinematic AI video generator like the higfly demo
(github.com/FlyMyAI/higfly) - a "Higgsfield killer":
- Research Higgsfield first (product, the camera-control presets, pricing,
  which frontier models it resells) and put the findings in BUILD_LOG.md.
- Confirm FlyMyAI hosts the same frontier video models (Seedance 2.0, Veo 3.1,
  Kling) via recommend_model, and pick the best cost/quality one.
- Build ONE FlyMyAI agent: input = a shot prompt + an optional camera-move
  preset; it prepends the preset phrasing and calls run_model exactly once to
  render a clip. Freeze it after one verified run so repeats are a cheap fixed
  pipeline.
- Ship the "camera presets" as plain editable prompt templates in presets/.
- Write the thinnest CLI client that renders a clip from a prompt + preset.
- Measure the REAL billed cost per clip with get_execution_price and put every
  number, dead end and platform bug in BUILD_LOG.md as you go.
Only claim numbers from our own bill. Do not out-claim Higgsfield on polish.
```
