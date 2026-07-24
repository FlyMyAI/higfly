# higfly - Build Log

Goal: a "Higgsfield killer" - cinematic AI video (camera moves, viral looks) built as ONE frozen FlyMy.AI agent + a thin CLI, with the camera "presets" shipped as open prompt templates. Built live with Claude (brain) + FlyMyAI MCP (hands). Only numbers from our own bill.

All dates UTC.

## 2026-07-23

### Research - who is Higgsfield, really

- **Valuation / traction (public):** $80M Series A extension led by Accel in Jan 2026 at a **$1.3B valuation**; ~$138M raised total; reportedly in talks to raise at ~$5B; ~$500M annualized revenue (Sacra est.). Sources at the bottom.
- **What it actually is:** its center of gravity is **camera control** - Cinema Studio + Viral Presets + director-style prompting (dolly/crash/crane/pan/tilt/tracking). It **aggregates 15+ frontier models** - Sora 2, Veo 3.1, Kling 3.0, **Seedance 2.0**, WAN 2.6 (+ its own DoP model) - under one subscription.
- **Pricing:** Basic $5/mo (70 credits), Plus $39/mo (1,000), Ultra $99/mo (3,000-9,000), Business $62/seat. Monthly credits **do not roll over**; top-ups **expire in 90 days**; annual plans non-refundable.
- **The opening:** the models are commodities Higgsfield resells, and the "presets" are prompts. FlyMy.AI hosts the same frontier video models. So the killer angle is honest and simple: **call the models directly, ship the presets as open text, pay per clip.**

### FlyMyAI model check (via recommend_model)

Same-tier frontier text-to-video available on FlyMy.AI today, with our catalog price (billed to our key):

| Model | Price / clip | Notes |
|---|---|---|
| bytedance-seedance-2_0-fast-text-to-video | **$0.20** | fastest/cheapest |
| veo31-fast-generate | $0.25 | 720p |
| minimax-hailuo-02 | $0.27 | strong motion |
| bytedance-seedance-2_0-text-to-video | $0.40 | highest quality |
| veo31-generate | $0.50 | 1080p, best realism |

Image-to-video and reference-to-video variants exist at the same prices (animate a still / keep a subject consistent).

### First real render (self-test)

- Model: `flymyai/bytedance-seedance-2_0-fast-text-to-video`, prediction `2f5b41e25ada44469ad479d44692dfab`.
- Prompt (crash-zoom preset + shot): "Cinematic crash zoom onto a lone astronaut standing at the edge of a vast red desert canyon at golden hour, dramatic volumetric god rays, drifting dust, anamorphic lens flare, shallow depth of field, 35mm film grain, epic sci-fi mood, slow push-in camera move", 720p, 4s, no audio, no watermark.
- Result: a real .mp4 rendered in **~140s wall**. **Our price: $0.20/clip** (Seedance 2.0 Fast catalog rate). A full-quality Seedance/Veo pass is $0.40-0.50.
- Reproduce: run the same model with the same input, or run the frozen agent (agent/prompt.md).

### Honest scope of this V1

- Shipped: the frozen-agent design (`agent/prompt.md`), the camera-move presets as open prompts (`presets/`), a thin CLI (`client/`), and this log. The agent IS the engine - one `run_model` per clip, no discovery at runtime.
- Not shipped (yet): a full desktop studio UI and a one-click viral-VFX library on Higgsfield's scale. Their studio polish and their own DoP model are a real edge - we do not claim to out-polish them. We claim you can **own the same frontier models + editable presets at ~$0.20-0.50/clip** instead of renting them monthly.
- Balance-delta billing is unreliable here: the FlyMy.AI wallet is a shared team account with scheduled agents running, so per-clip cost is taken from the model's catalog rate (billed to the key), not a wallet diff.

## Sources
- Higgsfield valuation/funding: Sacra, Dealroom, TechTimes, AOL/Reuters (Jan 2026 $1.3B round).
- Higgsfield features/pricing: bleap.finance, mcstarters, makerstack reviews (2026).
