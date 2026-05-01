---
permalink: /
title: "Kevin Tian"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

# Kevin Tian

> I build production AI systems that connect large-scale machine learning, search understanding, multimodal modeling, and real-world user intent.

I am a Senior Machine Learning Engineer at ByteDance/TikTok in Singapore, working on AI systems for search and local services. My work focuses on building end-to-end machine learning systems that understand user intent, retrieve relevant entities, and serve reliable predictions at production scale.

My recent work spans LLM-based query understanding, POI and destination recognition, local service search, multimodal representation learning, and large-scale model deployment. I am especially interested in the intersection of **LLMs, search systems, retrieval, multimodal learning, and scalable inference**.

Previously, I worked at Meta, where I contributed to machine learning and representation learning systems. I obtained my PhD from the State University of New York at Stony Brook, with research experience in medical image analysis, 3D vision, and learning from limited annotations.

## What I work on

### LLMs for search and user intent understanding

I am interested in using large language models not only as text generators, but also as structured reasoning and understanding modules inside search systems. In local service search, user queries are often short, ambiguous, multilingual, and context-dependent. A query such as “best rooftop bar near times square” may involve intent classification, location understanding, POI recognition, category matching, and ranking constraints.

My work explores how LLMs, smaller task-specific models, retrieval systems, and rule-based safeguards can be combined into practical production pipelines.

### Large-scale ML systems

A large part of my engineering work is about making models actually useful in production: data pipelines, feature generation, distributed computation, model serving, caching, evaluation, monitoring, and launch review. I have worked with large-scale Spark/Hive workflows, online and nearline systems, RPC services, and high-throughput inference jobs.

I care about the full path from model idea to product impact.

### Multimodal and representation learning

Before my recent LLM/search work, I worked on multimodal modeling for risk control, content integrity, and medical AI. This included combining text, image, audio, video, behavior, and graph signals to detect abnormal patterns or improve structured understanding.

My long-term interest is to build AI systems that can reason across language, vision, behavior, and structured knowledge.

## Selected projects

### LLM-based POI and destination understanding for local service search

Built components for an end-to-end local service understanding pipeline that maps user queries to structured signals such as destination, POI, service category, and local intent. The system combines LLM-based extraction, NER, retrieval, candidate selection, caching, and evaluation across multiple countries.

Key themes:

- Query understanding for ambiguous and multilingual local-service searches
- LLM-based destination rewriting and POI selection
- Real-time NER for search queries
- Offline evaluation with precision/recall analysis by country and query type
- Production deployment and launch-readiness analysis

### Multimodal fraud and integrity detection

Worked on machine learning systems for detecting fake accounts, abnormal engagement, and coordinated behavior patterns. This involved graph mining, multimodal behavior features, unsupervised detection, and production defense pipelines.

Key themes:

- Graph-based fraud ring discovery
- Multimodal behavior modeling
- Automated discovery-propagation-elimination workflows
- Large-scale production monitoring and iteration

### High-throughput LLM inference and model optimization

Worked on practical problems around serving and processing large language models efficiently, including quantization, distributed inference, throughput optimization, and cost-aware deployment. I am interested in how large models can be made useful under real production constraints such as latency, GPU budget, reliability, and quality.

Key themes:

- Large-model inference optimization
- Quantization and model format conversion
- Batch processing and GPU resource efficiency
- Tradeoffs between model size, latency, and output quality

### Medical image analysis and interactive 3D segmentation

My PhD and research background focused on medical image analysis, 3D segmentation, and learning with limited annotations. I worked on interactive and continual learning methods that reduce annotation cost while maintaining segmentation quality.

Key themes:

- 3D medical image segmentation
- Interactive learning with limited supervision
- Online model adaptation
- Computer vision for clinical and biomedical applications

## Research and engineering interests

| Area | Topics |
|---|---|
| LLM systems | Query understanding, structured extraction, verifier models, RAG, agentic workflows |
| Search | Local service search, POI matching, destination understanding, retrieval and ranking |
| Multimodal AI | Vision-language learning, behavior modeling, content understanding |
| ML systems | Distributed data processing, model serving, caching, evaluation, monitoring |
| Applied research | Medical AI, 3D vision, annotation-efficient learning |

## What I am writing about

I use this website to organize technical notes, project reflections, and system-design writeups. Some topics I plan to write about include:

- Designing an LLM-based POI understanding system for local service search
- Precision and recall evaluation for geo-intent and destination signals
- Lessons from scaling LLM inference under GPU constraints
- How to combine small models, LLMs, retrieval, and verification in production
- Practical tradeoffs in ML system design: quality, latency, cost, and maintainability

## Professional direction

I am most excited by roles that combine deep machine learning with real-world systems: LLM applications, search and recommendation, multimodal understanding, AI infrastructure, and production ML platforms.

My goal is to keep building AI systems that are technically deep, practically useful, and robust enough to work at scale.