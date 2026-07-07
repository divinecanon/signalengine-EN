# Signal for LLM
# Time：2026-7-1

**Runtime state modulation layer for large language models.**  
Not another model. Not another training trick. A decoupled Modulator that writes to the engine while the Generator stays ignorant.

---

## Status: Frozen

Theory — complete.  
Architecture — defined.  
Interfaces — audited.

This repository is a **release**, not a proposal. The achievement is the blueprint. Experiments are an engineering hobby that follows.

---

## One Sentence

> Current LLMs are statically frozen after RLHF — the Generator runs, the constraints are dead.  
> Signal for LLM puts constraints back into the runtime, where they belong.

## The Decoupling

| Role | What it does | Size |
|---|---|---|
| **Generator** | Produces tokens | The whole model you already have |
| **Modulator** | Modulates runtime state (KV Cache, Context Window, Expert Routing, Inference Budget…) | Can be `+` / `-` / `0` |
| **Reward Model** | Learns constraints during training | Already exists |

The Modulator is **not** the Generator.  
The Modulator is **not** the Reward Model.  
It is the third entity that survives deployment.

> 📎 The Generator does **not** read the Modulator's output.  
> It only feels the causal drift in runtime state.  
> If the Generator tries to "understand" the Modulator, Signal degrades into Prompt Engineering.  
> Don't let it.

---

## What Signal Is Not

- Signal is **not** a Prompt.
- Signal is **not** an Embedding.
- Signal is **not** information.

Signal is **runtime state modulation that actually changes the machine**.  
If it can only be read as a symbol, it's a projection. Not Signal.

---

## Repository Map

This repo carries the English release of **Signal for LLM** (engineering architecture).  
The TGR theoretical system (10 docs, Chinese-primary) is the upstream; this repo is the downstream engineering surface.

| Layer | Doc |
|---|---|
| Engineering entry | [Signal for LLM](./Signal%20for%20LLM.md) |
| Spec | Signal |
| Mapping | Signal Mapping |
| Taxonomy | Signal Taxonomy |
| Runtime | Signal Runtime |
| API | Signal API |
| Engine | Signal Engine (evolving) |

Full TGR index → [Live site](https://github.com/divinecanon/tgr.git)

---

## License

[CC0 1.0](LICENSE). No rights reserved. The architecture is a fact; facts don't belong to anyone.

---

## "Proof"

There is no benchmark to chase.  
If modulating runtime state changes generation — and it does — the only remaining question is engineering pace, not existence.

> 🔻 *Modulator proposed → architecture complete → experiment optional.*
