# QuantumMytheme

**Verifiable runs for hard quantum design — point a capable model at a problem, get a machine-checkable verdict no human scored.**

We build open, reproducible benches where a deterministic judge — not human taste — decides whether a quantum design is correct. Every claim re-runs on a laptop: numpy only, offline, no QPU required.

**The bigger why.** This bench is the wedge — the hardest verifiability case — for a **verifiable-efficiency referee**: one re-checkable yardstick for how machine intelligence gets useful and far more efficient. We're honest about where quantum fits — it will *not* make today's LLMs faster, cheaper, or greener; its genuine role is simulating strongly-correlated materials for better *classical* chips. The full, source-backed map of where efficiency actually comes from is the [curriculum's North Star](https://quantummytheme.com/education).

---

## Do your own harness prep

This org is a workbench, not a gallery. The whole point is that **you** can mint your own run, bring your own model, and produce a verified result that anyone can re-check.

> Use the **[quantum-harness](https://github.com/QuantumMytheme/quantum-harness)** template → spin up a fresh public run repo → point your model at a BRIEF → let it loop until the judge **ACCEPTs** → commit the proof bundle. That repo becomes a permanent, public, re-verifiable record.

No gatekeeping. The judge is hermetic and deterministic, so your result stands on its own — anyone can reproduce the verdict by re-running the judge on your committed bundle.

---

## Three reasons this exists

**1 · Contribute to science.**
Build an open, reproducible, re-verifiable corpus of verified quantum designs that anyone can confirm by re-running the judge. Correctness is scored *without human taste* — a recomputed number either matches or it doesn't.

**2 · A scoreboard across paradigms.**
Compare design approaches — different ansätze, qubit topologies, coupling maps, feature maps — and classical baselines on the *same* judge-scored problems. Which approach currently leads is public, and the frontier moves in the open.

**3 · For the curious, to hill-climb.**
A place to start a harness prompt for a capable model — today **Opus 4.8** / **Fable 5**, and built to be ready for the next-gen models you may know as **Mythos** — and watch it loop to ACCEPT. Point it at a BRIEF, then try to beat the current best verified score.

> Models are model-agnostic fuel. The judge does not care who — or what — produced a bundle; it only re-simulates.

---

## How a run works

1. **Mint a run repo** from the template → a fresh *public* repo in this org (or `bin/new-run.sh`).
2. **Pick or write a BRIEF** — the problem stated conceptually; the answer key stays host-side.
3. **Run the kickoff** with *your* capable model (your subscription, or API / token credits). The model designs the artifact and **self-corrects against the rubric** until the judge ACCEPTs.
4. **Commit the output back** to your run repo — the proof bundle, the judge verdict (exit 0), the scrubbed transcript, the autonomy scorecard. Then push.

The run repo is the permanent, public, re-verifiable record.

---

## What the bench checks

Four hermetic gates. A bundle is ACCEPTed only if it clears all of them — and the judge **re-simulates from scratch**, so a claimed number that isn't real is caught.

| Gate | Exit | What it proves |
| --- | :---: | --- |
| **Structure** | 3 | the circuit parses and respects n-qubits, depth budget, native gates, coupling map, 2-qubit cap |
| **Reproducibility** | 4 | re-simulating reproduces the *claimed* number within tolerance — fabrication is caught |
| **Performance** | 5 | the *recomputed* result meets the threshold **and** beats the classical baseline |
| **Anti-overfit** | 6 | the design also passes a **held-out** check the model never saw — a hidden observable, workload, or test set |

Five task types: **state_prep**, **vqe**, **populations**, **architecture** (qubit-topology / coupling-map design), **classify** (quantum feature-map classifier).

Kept honest: the held-out reference lives *only* with the judge. The model knows the target conceptually from the BRIEF — it never gets the answer key. A bundle can *claim* fidelity 1.0; the judge recomputes it and rejects the lie.

---

## Links

- **Template + flagship** — [quantum-harness](https://github.com/QuantumMytheme/quantum-harness) (a GitHub template repo; "Use this template" to start)
- **Live site** — [quantummytheme.com](https://quantummytheme.com) (the in-browser showcase of the bench — paper + luminous themes)
- **Learn — the North Star** — [quantummytheme.com/education](https://quantummytheme.com/education) (a 39-slice curriculum: where machine intelligence actually gets more efficient, and where quantum does and doesn't fit)
- **How a run works** — [RUN-FLOW.md](https://github.com/QuantumMytheme/quantum-harness/blob/main/RUN-FLOW.md)
- **Contribute** — [CONTRIBUTING.md](https://github.com/QuantumMytheme/quantum-harness/blob/main/CONTRIBUTING.md) (the judge is the merge gate)
- **Scoreboard** — [SCOREBOARD.md](https://github.com/QuantumMytheme/quantum-harness/blob/main/SCOREBOARD.md)
- **Related research** — [Designing more efficient quantum circuits with Claude](https://www.anthropic.com/research/designing-efficient-quantum-circuits) (Anthropic, 2026-10; [arXiv:2610.22367](https://arxiv.org/abs/2610.22367)): the same model → automated judge → iterate loop, beating published circuits on 8 classically checkable primitives. Our notes: [findings](https://github.com/QuantumMytheme/quantum-harness/blob/main/docs/research/2026-10-anthropic-llm-circuit-discovery.md)

---

<sub>**4 gates · 5 tasks · 38/38 judge checks · 107/107 node tests · numpy-only · offline** — MIT licensed.</sub>
