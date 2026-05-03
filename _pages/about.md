---
permalink: /
title: "Kevin Tian"
excerpt: "Kevin Tian, also publishing as Mu Tian / Tian, Mu, is a Senior Machine Learning Engineer at ByteDance/TikTok Singapore and ex-Meta Research Scientist working on LLM post-training, agentic/RAG search, multimodal foundation models, and generative vision."
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

> I build production AI systems around LLMs, multimodal foundation models, and generative vision.

I am a Senior Machine Learning Engineer at ByteDance/TikTok Singapore, building LLM post-training, agentic/RAG, and production AI systems for search. My career path connects multimodal foundation models at Meta, generative and 3D vision in applied research/startup settings, and LLM-driven search understanding at TikTok. I focus on turning model development into production impact through post-training, retrieval, verification, planning, serving, caching, and evaluation. I also publish under the name *Mu Tian* (*Tian, Mu*, *Tian, M.*) in academic papers.

**[Download Resume](/files/Kevin_Tian_Resume_20260503.pdf)**

## Focus Areas

### LLM Post-training & Agentic Search

At TikTok, I build resource-efficient LLM/SLM systems for search understanding. I used a unified compact model for NER, query rewriting, POI recognition, structured parsing, LLM-as-a-judge verification, and agent-style planning. Through SFT/LoRA and reinforcement learning–based post-training, including PPO-style RLHF and DPO-style preference optimization, the system improved structured understanding quality while controlling latency and serving cost. I also helped design a nearline Kafka-to-cache architecture with cache-oriented query canonicalization, substantially improving cache coverage and reducing online model-serving pressure. For details, check [Resource-efficient LLM system for local-service search]({{ '/projects/llm-agentic-search/' | relative_url }}).

### Multimodal Foundation Models

At Meta, I worked on multimodal foundation-model pretraining for video, audio, and text understanding. My work covered video-transformer and audio-transformer modeling for downstream applications such as harmful video detection, content integrity, video understanding, and ASR/audio transcription.

I also helped bridge the research-to-production gap during Meta’s early transition from Caffe2-heavy deployment workflows to PyTorch/TorchScript-based serving. By using PyTorch JIT/TorchScript to make research models more directly deployable, I reduced the engineering overhead of rewriting or translating models for production inference and enabled faster iteration from model development to online evaluation.

### Generative AI & 3D Vision

After Meta, I worked on applied research and startup-oriented AI for generative and 3D medical vision. I focused on diffusion-based data and annotation synthesis to address limited-label settings, using generative models to expand scarce training data and improve downstream segmentation robustness. I also developed interactive and online-learning segmentation systems that reduced expert annotation cost and made 3D medical AI more adaptable to real-world clinical workflows.

For details, see **Projects**, **Papers**, and **Blog**.


<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Kevin Tian",
  "alternateName": ["Mu Tian", "Tian, Mu", "Kevin M. Tian", "Tian, M"],
  "url": "https://kevinmtian.github.io/",
  "email": "mailto:kevinmtian@gmail.com",
  "jobTitle": "Senior Machine Learning Engineer",
  "worksFor": {
    "@type": "Organization",
    "name": "ByteDance / TikTok"
  },
  "alumniOf": [
    {
      "@type": "CollegeOrUniversity",
      "name": "Stony Brook University"
    },
    {
      "@type": "CollegeOrUniversity",
      "name": "Tulane University"
    },
    {
      "@type": "CollegeOrUniversity",
      "name": "East China Normal University"
    }
  ],
  "sameAs": [
    "https://www.linkedin.com/in/kevinmtian",
    "https://github.com/kevinmtian",
    "https://scholar.google.com/citations?user=sofIFCgAAAAJ&hl=en"
  ],
  "knowsAbout": [
    "LLM post-training",
    "agentic search",
    "RAG pipelines",
    "multimodal foundation models",
    "generative vision",
    "diffusion models",
    "3D medical image segmentation"
  ]
}
</script>