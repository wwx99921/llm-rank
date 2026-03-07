# llm-rank

BM25 and LLM-based passage reranking in a single C++ header.

## Features
- BM25 local reranking (no API, instant)
- LLM reranking via OpenAI scoring prompt
- Hybrid mode: BM25 first pass, LLM refines top-k
- Standalone BM25 class for direct use
- Single-header, C++17, namespace `llm`

## Quick Start
```cpp
#define LLM_RANK_IMPLEMENTATION
#include "llm_rank.hpp"

auto results = llm::rerank_local("machine learning", passages);
for (auto& r : results)
    std::printf("[%d] %.3f  %s\n", r.new_rank, r.score, r.passage.c_str());
```

## API
```cpp
std::vector<RankResult> rerank_local(const std::string& query, const std::vector<std::string>& passages, const LocalRankConfig& = {});
std::vector<RankResult> rerank_llm(const std::string& query, const std::vector<std::string>& passages, const LLMRankConfig&);
std::vector<RankResult> rerank_hybrid(const std::string& query, const std::vector<std::string>& passages, const LocalRankConfig&, const LLMRankConfig&, size_t llm_top_k = 10);
class BM25 { ... };
```

## License
MIT — Mattbusel, 2026

## See Also

| Repo | Purpose |
|------|---------|
| [llm-stream](https://github.com/Mattbusel/llm-stream) | SSE streaming |
| [llm-cache](https://github.com/Mattbusel/llm-cache) | Response caching |
| [llm-cost](https://github.com/Mattbusel/llm-cost) | Token cost estimation |
| [llm-retry](https://github.com/Mattbusel/llm-retry) | Retry + circuit breaker |
| [llm-format](https://github.com/Mattbusel/llm-format) | Markdown/code formatting |
| [llm-embed](https://github.com/Mattbusel/llm-embed) | Embeddings + cosine similarity |
| [llm-pool](https://github.com/Mattbusel/llm-pool) | Connection pooling |
| [llm-log](https://github.com/Mattbusel/llm-log) | Structured logging |
| [llm-template](https://github.com/Mattbusel/llm-template) | Prompt templates |
| [llm-agent](https://github.com/Mattbusel/llm-agent) | Tool-use agent loop |
| [llm-rag](https://github.com/Mattbusel/llm-rag) | Retrieval-augmented generation |
| [llm-eval](https://github.com/Mattbusel/llm-eval) | Output evaluation |
| [llm-chat](https://github.com/Mattbusel/llm-chat) | Multi-turn chat |
| [llm-vision](https://github.com/Mattbusel/llm-vision) | Vision/image inputs |
| [llm-mock](https://github.com/Mattbusel/llm-mock) | Mock LLM for testing |
| [llm-router](https://github.com/Mattbusel/llm-router) | Model routing |
| [llm-guard](https://github.com/Mattbusel/llm-guard) | Content moderation |
| [llm-compress](https://github.com/Mattbusel/llm-compress) | Prompt compression |
| [llm-batch](https://github.com/Mattbusel/llm-batch) | Batch processing |
| [llm-audio](https://github.com/Mattbusel/llm-audio) | Audio transcription/TTS |
| [llm-finetune](https://github.com/Mattbusel/llm-finetune) | Fine-tuning jobs |
| [llm-rank](https://github.com/Mattbusel/llm-rank) | Passage reranking |
| [llm-parse](https://github.com/Mattbusel/llm-parse) | HTML/markdown parsing |
| [llm-trace](https://github.com/Mattbusel/llm-trace) | Distributed tracing |
| [llm-ab](https://github.com/Mattbusel/llm-ab) | A/B testing |
| [llm-json](https://github.com/Mattbusel/llm-json) | JSON parsing/building |
