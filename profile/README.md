<p align="center">
  <a href="https://wauldo.com">
    <img src="https://raw.githubusercontent.com/wauldo/.github/main/profile/banner.png" alt="Wauldo — Verified AI answers from your documents" width="700" />
  </a>
</p>

<p align="center">
  <a href="https://wauldo.com/demo"><img src="https://img.shields.io/badge/Live_Demo-Try_Now-3b82f6?style=for-the-badge&logoColor=white" alt="Demo" /></a>&nbsp;
  <a href="https://wauldo.com/docs"><img src="https://img.shields.io/badge/Docs-API_Reference-10b981?style=for-the-badge&logoColor=white" alt="Docs" /></a>&nbsp;
  <a href="https://rapidapi.com/binnewzzin/api/smart-rag-api"><img src="https://img.shields.io/badge/RapidAPI-Free_Tier-f59e0b?style=for-the-badge&logoColor=white" alt="RapidAPI" /></a>
</p>

<h3 align="center">Verified AI answers from your documents — grounded, or refused.</h3>

<p align="center">
  Wauldo is a RAG API that <strong>verifies its own outputs before returning them</strong>.<br />
  Upload documents, ask questions, and get answers grounded in your sources — or no answer if it can't be verified.
</p>

---

<br />

<h2 align="center">Zero Hallucination by Design</h2>

<p align="center">
  <img src="https://img.shields.io/badge/Hallucination_Rate-0%25-22c55e?style=flat-square&labelColor=1e293b" alt="0% hallucination" />&nbsp;
  <img src="https://img.shields.io/badge/Accuracy-83%25-3b82f6?style=flat-square&labelColor=1e293b" alt="83% accuracy" />&nbsp;
  <img src="https://img.shields.io/badge/LLMs_Tested-14_models-8b5cf6?style=flat-square&labelColor=1e293b" alt="14 LLMs" />&nbsp;
  <img src="https://img.shields.io/badge/Avg_Latency-~1.2s-f59e0b?style=flat-square&labelColor=1e293b" alt="~1.2s latency" />
</p>

<p align="center">
  <em>Most RAG systems retrieve context and assume the model gets it right.<br />Wauldo verifies the answer before returning it.</em>
</p>

<br />

---

<br />

<h2 align="center">Anti-Hallucination Arsenal</h2>

<p align="center">
  Most RAG systems have <strong>one</strong> defense: retrieval.<br />
  Wauldo has <strong>seven layers</strong> — each catches what the others miss.
</p>

<br />

<h3 align="center">
  <img src="https://img.shields.io/badge/BEFORE_THE_LLM-4_layers-3b82f6?style=for-the-badge&labelColor=1e293b" alt="Before LLM" />
</h3>

<table align="center">
  <tr><th>Layer</th><th>What it does</th><th>What it catches</th></tr>
  <tr><td align="center"><strong>Hybrid Retrieval</strong></td><td>BM25 + vector search combined</td><td>Exact terms that embeddings miss</td></tr>
  <tr><td align="center"><strong>Entity-Split Retrieval</strong></td><td>"A vs B" queries retrieved independently</td><td>Missing entity in comparisons</td></tr>
  <tr><td align="center"><strong>Critical Chunk Forcing</strong></td><td>Force-include chunks matching query entities</td><td>Important data dropped by scoring</td></tr>
  <tr><td align="center"><strong>Fact Extraction</strong></td><td>Numbers, dates, limits injected as constraints</td><td>Numerical drift ("60 days" → "30 days")</td></tr>
</table>

<br />

<h3 align="center">
  <img src="https://img.shields.io/badge/AFTER_THE_LLM-4_layers-22c55e?style=for-the-badge&labelColor=1e293b" alt="After LLM" />
</h3>

<table align="center">
  <tr><th>Layer</th><th>What it does</th><th>What it catches</th></tr>
  <tr><td align="center"><strong>Grounding Check</strong></td><td>Answer terms checked against source terms</td><td>Invented facts not in any source</td></tr>
  <tr><td align="center"><strong>Numerical Verification</strong></td><td>Answer numbers compared to source numbers</td><td>"$500" vs "$1,000"</td></tr>
  <tr><td align="center"><strong>Contradiction Detection</strong></td><td>Flags "never" vs "12 months" conflicts</td><td>Qualifier drops ("may cover" → "covers")</td></tr>
  <tr><td align="center"><strong>Citation Validation</strong></td><td>Every citation traced to a real source</td><td>Phantom references</td></tr>
</table>

<br />

---

<br />

<h2 align="center">What You Can Do</h2>

<p align="center">
  <img src="https://img.shields.io/badge/Upload-PDF_%7C_DOCX_%7C_30%2B_formats-3b82f6?style=flat-square&labelColor=1e293b" alt="Upload" />&nbsp;
  <img src="https://img.shields.io/badge/Query-Verified_answers_with_citations-22c55e?style=flat-square&labelColor=1e293b" alt="Query" />&nbsp;
  <img src="https://img.shields.io/badge/Fact--Check-Verify_any_LLM_output-8b5cf6?style=flat-square&labelColor=1e293b" alt="Fact-check" />&nbsp;
  <img src="https://img.shields.io/badge/Verify-Citation_validation-f59e0b?style=flat-square&labelColor=1e293b" alt="Verify" />
</p>

<table align="center">
  <tr><td align="center"><strong>Document Upload</strong></td><td>Native PDF/DOCX with extraction quality scoring</td></tr>
  <tr><td align="center"><strong>Verified Q&A</strong></td><td>Full pipeline — retrieval, generation, verification</td></tr>
  <tr><td align="center"><strong>Fact-Check</strong></td><td>Verify any claim against any source (3 modes)</td></tr>
  <tr><td align="center"><strong>Citation Verify</strong></td><td>Check if text properly cites its sources</td></tr>
  <tr><td align="center"><strong>Auto Routing</strong></td><td>Risk-based model selection across 3 tiers</td></tr>
  <tr><td align="center"><strong>Fast-Path</strong></td><td>High-confidence answers in ~0.3s (bypasses LLM)</td></tr>
  <tr><td align="center"><strong>Audit Trail</strong></td><td>Every response includes routing, sources, confidence</td></tr>
  <tr><td align="center"><strong>OpenAI-Compatible</strong></td><td>Drop-in replacement for existing integrations</td></tr>
</table>

<br />

---

<br />

<h2 align="center">SDKs</h2>

<p align="center">
  <a href="https://pypi.org/project/wauldo/"><img src="https://img.shields.io/badge/Python-pip_install_wauldo-3776ab?style=for-the-badge&logo=python&logoColor=white" alt="Python" /></a>&nbsp;
  <a href="https://www.npmjs.com/package/wauldo"><img src="https://img.shields.io/badge/TypeScript-npm_install_wauldo-3178c6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" /></a>&nbsp;
  <a href="https://crates.io/crates/wauldo"><img src="https://img.shields.io/badge/Rust-cargo_add_wauldo-dea584?style=for-the-badge&logo=rust&logoColor=white" alt="Rust" /></a>
</p>

<p align="center">
  <a href="https://github.com/wauldo/wauldo-sdk-python">Python Repo</a> · 
  <a href="https://github.com/wauldo/wauldo-sdk-js">TypeScript Repo</a> · 
  <a href="https://github.com/wauldo/wauldo-sdk-rust">Rust Repo</a>
</p>

```python
from wauldo import HttpClient

client = HttpClient(base_url="https://api.wauldo.com", api_key="YOUR_KEY")
response = client.query(tenant_id="my-docs", query="What is the refund policy?")

if response.status == "insufficient_evidence":
    print("No verified answer available")
else:
    print(response.answer)
    print(response.citations)
```

<br />

---

<br />

<h2 align="center">Built For</h2>

<p align="center">
  <img src="https://img.shields.io/badge/Production_RAG-Factual_Reliability-3b82f6?style=flat-square&labelColor=1e293b" alt="" />&nbsp;
  <img src="https://img.shields.io/badge/Knowledge_Bases-Customer_Support-22c55e?style=flat-square&labelColor=1e293b" alt="" /><br />
  <img src="https://img.shields.io/badge/Regulated_Domains-Legal_%7C_Insurance_%7C_Healthcare-8b5cf6?style=flat-square&labelColor=1e293b" alt="" />&nbsp;
  <img src="https://img.shields.io/badge/Philosophy-Won't_Guess%2C_Won't_Lie-f59e0b?style=flat-square&labelColor=1e293b" alt="" />
</p>

<br />

<h2 align="center">Architecture</h2>

<p align="center">
  <img src="https://img.shields.io/badge/Rust-17_crates-dea584?style=flat-square&logo=rust&logoColor=white&labelColor=1e293b" alt="" />&nbsp;
  <img src="https://img.shields.io/badge/Retrieval-BM25_%2B_Vector-3b82f6?style=flat-square&labelColor=1e293b" alt="" />&nbsp;
  <img src="https://img.shields.io/badge/Storage-SQLite-22c55e?style=flat-square&labelColor=1e293b" alt="" />&nbsp;
  <img src="https://img.shields.io/badge/Lock--in-None-8b5cf6?style=flat-square&labelColor=1e293b" alt="" />
</p>

<p align="center">
  <em>Model-agnostic pipeline: performance is driven by verification, not model size.</em>
</p>

<br />

---

<p align="center">
  <a href="https://wauldo.com">Website</a> · 
  <a href="https://wauldo.com/demo">Try the Demo</a> · 
  <a href="https://wauldo.com/docs">API Docs</a> · 
  <a href="https://rapidapi.com/binnewzzin/api/smart-rag-api">Free Tier</a> · 
  <a href="https://dev.to/wauldo/how-we-achieved-0-hallucination-rate-in-our-rag-api-with-benchmarks-4g54">Benchmarks</a>
</p>
