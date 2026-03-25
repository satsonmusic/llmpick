# 🎯 LlmPick - Dynamic Model Router

> **Optimizing Inference ROI.** A vendor-agnostic routing gateway that selects the best LLM for any task based on quality, cost, and latency constraints.

In a multi-model world, using a frontier reasoning model for every task is a massive waste of resources. **LlmPick** acts as an intelligent traffic controller—routing simple tasks to high-speed "Flash" models and escalating complex logic to "Reasoning" models, all while maintaining a 99.9% uptime via automated fallback paths.

## 🚀 Key Features
* **Multi-Constraint Optimization:** Dynamically ranks candidates based on User Quality Targets vs. Latency Budgets.
* **Resilient Fallback Architecture:** Automatically detects transient provider errors (429/503) and re-routes to the next best candidate.
* **Vendor-Agnostic Filtering:** Supports `allow` and `deny` lists to strictly control which providers (OpenAI, Anthropic, Google, DeepSeek) process specific data.
* **Production Observability:** Emits structured JSON logs for audit trails and cost-per-request tracking.

## 🛠️ Tech Stack
* **Engine:** Python 3.12 (Standard Library)
* **Strategy:** Deterministic Selection & Graceful Degradation
* **Observability:** Structured JSON Logging

## ⚙️ How to Run
```bash
# Clone the repo
git clone [https://github.com/satsonmusic/LlmPick.git](https://github.com/satsonmusic/LlmPick.git)
cd LlmPick

# Run a high-quality request with a 1500ms budget
python router.py "Analyze this legal document." --quality high --latency 1500 --cost 1.2