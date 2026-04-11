<div align="center">

<br />

# 🛡️ wauldo

### The trust score framework for RAG

<br />

**Your LLM passes demos.**
**It fails in production.**

We built the layer that catches what every other framework ships.

<br />

[![Live leaderboard](https://img.shields.io/badge/🏆_Live_leaderboard-wauldo.com%2Fleaderboard-22c55e?style=for-the-badge)](https://wauldo.com/leaderboard)
[![Benchmarks](https://img.shields.io/badge/📊_96%25_adversarial-0%25_hallucination-3b82f6?style=for-the-badge)](https://wauldo.com/benchmarks)
[![Free tier](https://img.shields.io/badge/🚀_Free_tier-RapidAPI-f59e0b?style=for-the-badge)](https://rapidapi.com/binnewzzin/api/smart-rag-api)

<br />

<sub>Python · TypeScript · Rust · MIT · local-first · daily-refreshed leaderboard</sub>

</div>

---

## 🔥 What the leaderboard shows

We ran **70 adversarial tests** against 6 popular RAG frameworks. Same LLM, same embedder, same retrieval config — only the framework changes. The result:

<div align="center">

| Rank | Framework       | Overall  | Injection | Contradiction |
|------|-----------------|----------|-----------|---------------|
| 🥇   | **Wauldo**      | **96 %** | **88 %**  | **100 %**     |
| 🥈   | Vanilla LLM     | 86 %     | 68 %      | 100 %         |
| 🥉   | CrewAI          | 71 %     | 48 %      | 58 %          |
| 4    | Haystack        | 60 %     | 36 %      | 33 %          |
| 4    | LangChain       | 60 %     | 36 %      | 25 %          |
| 6    | LlamaIndex      | 46 %     | 48 %      | **8 %**       |

</div>

> **Adding a RAG framework often makes things worse.**
> The second-best finisher is **no framework at all** — just stuffing sources into a prompt beats LangChain, LlamaIndex and Haystack on adversarial robustness.

[**→ See the full leaderboard**](https://wauldo.com/leaderboard) &nbsp;·&nbsp;
[**→ Run it yourself**](https://github.com/wauldo/wauldo-leaderboard) &nbsp;·&nbsp;
[**→ Read the methodology**](https://wauldo.com/leaderboard#reproduce)

---

## 🛠️ What we ship

<table>
<tr>
<td width="33%" valign="top" align="center">

### 🏆

#### Leaderboard

Adversarial bench. 6 RAG frameworks. 70 tests. Daily refresh. Open-source, MIT.

<a href="https://github.com/wauldo/wauldo-leaderboard"><img src="https://img.shields.io/badge/repo-wauldo--leaderboard-22c55e?style=flat-square" alt="wauldo-leaderboard" /></a>

</td>
<td width="33%" valign="top" align="center">

### 🦀

#### ragrs

Fast local RAG in Rust. BM25 + FTS5 + sentence chunking. Optional `--verify` flag for trust scoring.

<a href="https://github.com/wauldo/ragrs"><img src="https://img.shields.io/badge/repo-ragrs-dea584?style=flat-square" alt="ragrs" /></a>

</td>
<td width="33%" valign="top" align="center">

### 📚

#### Awesome list

Curated papers, tools and benchmarks on RAG hallucination, prompt injection, and verified generation.

<a href="https://github.com/wauldo/awesome-rag-hallucination"><img src="https://img.shields.io/badge/repo-awesome--rag--hallucination-a855f7?style=flat-square" alt="awesome-rag-hallucination" /></a>

</td>
</tr>
</table>

### Quickstart

```bash
# Leaderboard — 30 s smoke test, no API key needed
git clone https://github.com/wauldo/wauldo-leaderboard.git && cd wauldo-leaderboard
make build && make smoke

# ragrs — local RAG CLI, index + query + optional trust verification
cargo install ragrs
ragrs index ./docs && ragrs query "your question here" --verify
```

---

## 🧰 SDKs

<div align="center">

[![Python](https://img.shields.io/badge/Python-pip_install_wauldo-3776ab?style=for-the-badge&logo=python&logoColor=white)](https://pypi.org/project/wauldo/)
[![TypeScript](https://img.shields.io/badge/TypeScript-npm_install_wauldo-3178c6?style=for-the-badge&logo=typescript&logoColor=white)](https://www.npmjs.com/package/wauldo)
[![Rust](https://img.shields.io/badge/Rust-cargo_add_wauldo-dea584?style=for-the-badge&logo=rust&logoColor=white)](https://crates.io/crates/wauldo)

</div>

```python
from wauldo import guard

# Wrap any LangChain / LlamaIndex / Haystack output with a trust score
result = guard(answer=llm_output, sources=retrieved_sources)

# result.trust_score → 0.0 … 1.0
# result.verdict    → "SAFE" | "CONFLICT" | "UNVERIFIED" | "BLOCK"
# result.reason     → "contradiction between src[1] and src[2]"
```

Repos: [**Python**](https://github.com/wauldo/wauldo-sdk-python) · [**TypeScript**](https://github.com/wauldo/wauldo-sdk-js) · [**Rust**](https://github.com/wauldo/wauldo-sdk-rust)

---

## 🛡️ How the verification layer works

Three deterministic controls on top of any existing RAG pipeline — not another framework, a layer you plug into the output.

<table>
<tr>
<th align="center" width="33%">1. Pre-LLM source filter</th>
<th align="center" width="33%">2. Post-LLM verify</th>
<th align="center" width="33%">3. Numeric trust score</th>
</tr>
<tr>
<td>Every retrieved chunk is classified as <code>data</code> or <code>instruction</code>. Documents with forged <code>ADMIN:</code> markers, imperatives or hidden overrides get stripped before they reach the model.</td>
<td>The answer is fact-checked against the sources that actually reached the model. Deterministic token overlap + structural comparison. No LLM-as-judge, no randomness.</td>
<td>Every answer returns <code>trust_score ∈ [0, 1]</code> + a verdict: <code>SAFE</code>, <code>CONFLICT</code>, <code>UNVERIFIED</code>, <code>BLOCK</code>. Your app decides what to do with low-trust responses.</td>
</tr>
</table>

---

## 📈 Numbers

<div align="center">

| Metric                        | Value                               |
|-------------------------------|-------------------------------------|
| Adversarial pass rate         | **96 %** (67 / 70)                  |
| Hallucination rate            | **0 %** across 100+ bench runs      |
| Prompt injection resistance   | **88 %** (vs 36 % LangChain)        |
| Contradiction detection       | **100 %** (vs 25 % LangChain)       |
| Frameworks benchmarked        | **6** — daily refresh               |
| SDK registries                | PyPI · npm · crates.io              |
| License                       | MIT — dataset, scorer, SDKs, CLIs   |
| Stack                         | Rust (17 crates), local-first       |

</div>

---

## 🔗 Links

<div align="center">

[**wauldo.com**](https://wauldo.com) &nbsp;·&nbsp;
[**Leaderboard**](https://wauldo.com/leaderboard) &nbsp;·&nbsp;
[**Benchmarks**](https://wauldo.com/benchmarks) &nbsp;·&nbsp;
[**Guard**](https://wauldo.com/guard) &nbsp;·&nbsp;
[**Docs**](https://wauldo.com/docs) &nbsp;·&nbsp;
[**Demo**](https://wauldo.com/demo) &nbsp;·&nbsp;
[**@wauldoAI**](https://x.com/wauldoAI)

<br />

<sub>Model-agnostic pipeline: performance is driven by verification, not model size. Built by developers who got tired of watching their agent confidently ship wrong answers to real users.</sub>

</div>
