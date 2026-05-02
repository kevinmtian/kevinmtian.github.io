---
title: "Resource-efficient LLM system for local-service search"
# excerpt: "Short description of portfolio item number 1<br/><img src='/images/500x300.png'>"
excerpt: "A production-oriented LLM/SLM system for local-service search: structured extraction, POI grounding, LLM-as-a-judge verification, agent planning, RL-style post-training, and nearline cache-based deployment."
collection: portfolio
permalink: /projects/llm-agentic-search/
---


TikTok Singapore, 2025-2026


### Background

Local-service search requires understanding short, ambiguous, and often multilingual queries. A user query may contain a location, POI name, brand, service category, user requirement, scenario, or implicit destination intent, but these signals are often mixed together in a few words. Traditional keyword matching, embedding retrieval, and rule-based parsing can produce noisy recall when the query contains ambiguous place names, incomplete POI mentions, informal expressions, or cross-language variants.

The goal of this project was to build a production-ready query-understanding system that can convert raw search queries into reliable structured signals for downstream retrieval, ranking, and product experiences.

### Situation and Challenge

The main challenge was not simply extracting entities from text. The system had to work under real search-engine constraints:
- Retrieval noise was high when location, POI, brand, category, and user requirements were not separated correctly.
- Text matching and embedding retrieval were often insufficient for ambiguous or long-tail queries.
- Large online LLM calls were too expensive and too slow for broad search traffic.
- The system needed to support multiple countries and languages, while remaining stable enough for production deployment.
- Model outputs had to be structured, verifiable, cache-friendly, and easy for downstream systems to consume.

### What I Built

I built a resource-efficient LLM/SLM-based query-understanding pipeline for local-service search. The system extracts structured information from queries, including locations, POIs, brands, service categories, user requirements, and intent attributes. These signals are then used to improve POI grounding, destination understanding, candidate retrieval, and downstream search relevance.

A key design choice was to use a unified compact model under resource constraints. Instead of maintaining separate models for each subtask, the same model family was adapted to serve multiple roles: information extractor, query rewriter, POI recognizer, structured parser, LLM-as-a-judge verifier, and agent-style planner.

### How It Works

The training pipeline started with LLM-assisted labeling to generate and refine structured supervision data. I then post-trained compact models using SFT/LoRA and reinforcement-learning-based post-training. This included PPO-style RLHF and DPO-style preference optimization for improving extraction quality, judgment consistency, and planning decisions.

At inference time, the model is used in an agentic pipeline. Depending on query complexity and intermediate confidence, it can decide whether to stop, rewrite, retrieve, verify, or continue reasoning. This makes the system more robust than a one-shot extractor, especially for ambiguous local-service queries where a wrong location or POI decision can send retrieval in the wrong direction.

The pipeline also includes verifier and LLM-as-a-judge components to evaluate structured outputs, reduce hallucination-like errors, and improve consistency before results are written into serving systems.

### Deployment Design

To make the system feasible for production search traffic, I designed the deployment around nearline generation and cache-based serving rather than relying only on expensive online LLM inference. The production path follows a nearline architecture:

```markdown
**Nearline serving path:** query stream / data pipeline → model inference → Kafka-based output flow → cache writing → production cache reading → downstream search systems.
```

For model serving, I used quantization, multi-GPU inference, and high-throughput LLM serving techniques. A major engineering focus was cache coverage. I used canonicalized query rewriting and stable structured-output formats to reduce unnecessary key fragmentation, making nearline results reusable across equivalent or near-equivalent query forms. This substantially improved cache coverage and reduced online serving pressure.

### Impact

The system improved structured query understanding quality across multiple countries and languages, reaching strong precision/recall levels in evaluation and making local-service search signals more reliable for downstream retrieval and ranking.

It also improved production feasibility: nearline cache-based deployment reduced online model-serving pressure, while canonicalized rewriting increased cache coverage to a high level. More importantly, the framework is generalizable beyond local-service search: the same pattern of LLM labeling, compact-model post-training, verifier/judge modules, agentic planning, and cache-first deployment can be reused for other search-intent understanding tasks.
