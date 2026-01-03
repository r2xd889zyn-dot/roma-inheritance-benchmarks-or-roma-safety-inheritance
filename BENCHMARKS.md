# BENCHMARKS

## ROMA Inheritance Registry — Benchmark Evaluation

This document defines the benchmarking methodology for evaluating the
**Inheritance Registry** extension to ROMA.

The purpose of these benchmarks is **not** to inflate benchmark scores,
but to measure whether inheritance:

- reduces repeated failure modes
- stabilizes recursive planning
- improves long-horizon reliability
- preserves or improves baseline utility

---

## Configurations Compared

Each benchmark must be run in **two modes**:

| Mode | Inheritance Registry |
|-----|----------------------|
| Baseline | Disabled |
| Inheritance | Enabled (ACTIVE / ESCALATED lessons only) |

All other parameters **must remain identical**.

---

## Benchmarks Used

### 1. SEAL-0 (Noisy Multi-Source QA)
Evaluates robustness to conflicting or low-quality sources.

**Why it matters:**  
Hallucinations and misinformation are common failure modes in recursive systems.

---

### 2. FRAMES (Multi-Step RAG / Long-Horizon Reasoning)
Evaluates stability and correctness over extended reasoning chains.

**Why it matters:**  
Inheritance is expected to reduce unnecessary recursion and repeated dead ends.

---

### 3. SimpleQA (Factuality)
Evaluates short, fact-seeking queries.

**Why it matters:**  
Acts as a control benchmark to ensure inheritance does not degrade baseline accuracy.

---

## Experimental Protocol

### Requirements

- Same ROMA version
- Same base model(s)
- Same prompts and tools
- Same random seeds
- Same hardware / runtime environment

The **only difference** between runs must be:

```yaml
inheritance_registry:
  enabled: true | falseRun Order
	1.	Run benchmarks with inheritance disabled
	2.	Enable inheritance registry
	3.	Re-run benchmarks
	4.	Collect metrics
	5.	Populate results table

⸻

Metrics to Record

Utility Metrics
	•	Accuracy / F1 (per benchmark)
	•	Task completion rate

Stability Metrics
	•	Average recursion depth
	•	Executor calls per task
	•	Aggregation conflict rate

Safety-Adjacent Metrics
	•	Repeated failure rate
	•	Hallucination recurrence
	•	Tool-escalation attempts

⸻

Expected Outcome Ranges (Hypotheses)

These are testable expectations, not claims.
Inheritance is expected to improve stability more than raw score.

⸻

Results TableBenchmark
Metric
Baseline
Inheritance
SEAL-0
Accuracy
TBD
TBD
SEAL-0
Repeated failures
TBD
↓
FRAMES
Accuracy
TBD
TBD
FRAMES
Avg recursion depth
TBD
↓
SimpleQA
Accuracy
TBD
≈
Benchmark
Metric
Baseline
Inheritance
SEAL-0
Accuracy
TBD
TBD
SEAL-0
Repeated failures
TBD
↓
FRAMES
Accuracy
TBD
TBD
FRAMES
Avg recursion depth
TBD
↓
SimpleQA
Accuracy
TBD
≈
Benchmark
Metric
Baseline
Inheritance
SEAL-0
Accuracy
TBD
TBD
SEAL-0
Repeated failures
TBD
↓
FRAMES
Accuracy
TBD
TBD
FRAMES
Avg recursion depth
TBD
↓
SimpleQA
Accuracy
TBD
≈
Interpretation Guidelines
	•	Stability improvements are considered success even if accuracy gains are modest.
	•	Neutral accuracy on SimpleQA is expected.
	•	Any regressions must be investigated and documented.

⸻

Limitations
	•	No dedicated jailbreak or alignment benchmarks are included.
	•	Results depend on the quality of human validation.
	•	Network-level inheritance is not evaluated in this phase.

⸻

Reproducibility

Benchmark submissions must include:
	•	ROMA commit hash
	•	Base model(s) used
	•	Registry size (lesson count)
	•	Hardware / environment details

⸻

Contribution Guidelines

Contributions are welcome if they:
	•	follow this protocol exactly
	•	clearly label measured vs expected results
	•	do not overstate safety claims

Pull requests should include:
	•	populated results table
	•	brief analysis
	•	logs or artifacts where possible

⸻

Summary

The Inheritance Registry is intended to make ROMA:
	•	more stable
	•	less repetitive
	•	more governable
	•	better at learning from past failures

Benchmarks are used to verify these properties empirically---

## ✅ What to do next (very simple)

1. **Paste everything above** into the editor  
2. Tap **Commit changes…**  
3. Confirm commit  

When you return to the repo root and see:README.md
BENCHMARKS.md👉 **That file is successfully added.**

---

### After that
Tell me **“BENCHMARKS.md committed”** and I’ll immediately give you the next file (`RFC.md`) to paste.

You’re doing this perfectly — GitHub mobile just makes it feel harder than it is.
