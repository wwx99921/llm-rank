# llm-rank

Single-header C++17 library for BM25 and LLM-based passage reranking.

## Structure
- `include/llm_rank.hpp` — single-header implementation
- `examples/` — usage examples
- `CMakeLists.txt` — cmake build (requires vcpkg curl where applicable)

## Build
```bash
cmake -B build && cmake --build build
```
