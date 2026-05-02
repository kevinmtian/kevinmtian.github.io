---
title: "Multimodal Video Transformer"
# excerpt: "Short description of portfolio item number 1<br/><img src='/images/500x300.png'>"
excerpt: "A multimodal video Transformer system for harmful-content understanding, combining video/audio/text contrastive pretraining, temporal sequence modeling, supervised fine-tuning, attention-based harmful-content localization, and PyTorch/TorchScript productionization. It contributed to substantial reductions in harmful-content prevalence, including a major reduction in political misinformation, while improving reviewer efficiency through temporal localization."
collection: portfolio
permalink: /projects/mm_video_transformer/
---

*Senior Research Scientist, Meta (Seattle/Menlo Park, US), 2017-2020*

### Background

Large-scale video understanding requires more than visual classification. A harmful or policy-violating video may reveal its intent through visual frames, spoken audio, overlaid text, captions, metadata, or the interaction between these signals. For example, misinformation, adult content, violence, regulated goods, misleading ads, and otherwise normal videos can look similar under a single modality but become easier to distinguish when video, audio, and text are modeled together.

At Meta, I worked on multimodal foundation-model pretraining for video, audio, and text understanding, with downstream applications in harmful video detection, content integrity and video understanding.

### Situation and Challenge

The main challenge was to build models that could learn from large-scale, noisy, weakly aligned video data and then transfer to high-impact integrity tasks.

Key challenges included:

- Single-modality models were insufficient for many harmful-content cases, especially when the violation depended on the relationship between visual content, speech, captions, or text overlays.
- Facebook ad/video data contained rich but noisy multimodal signals: frames, audio, speech/text, and metadata were not always perfectly aligned.
- Downstream policy categories were long-tailed and heterogeneous, including sexual content, violence, political misinformation, alcohol/drug sales, misleading ads, and normal videos.
- The system needed to support both video-level classification and reviewer-facing localization signals so that human reviewers could quickly inspect suspicious moments.
- Production deployment was difficult at the time because many research models were trained in PyTorch, while production workflows were still heavily Caffe2/graph-deployment oriented.

### What I Built

I worked on a multimodal video-transformer framework that used video, audio, and text signals for large-scale video understanding. The model was first pretrained on large-scale Facebook ad/video data through self-supervised multimodal learning, then fine-tuned on supervised harmful-content classification labels.

The system supported downstream multi-class video classification across policy categories such as sexual content, violence, political misinformation, alcohol/drug sales, misleading advertising, and normal content. Beyond video-level prediction, the transformer attention structure also helped identify suspicious temporal regions or content segments, making it easier for reviewers to locate the part of the video responsible for a policy decision.

### How It Works

The system was built around a multimodal Transformer encoder for video, audio, and text understanding. The input sequence combined visual frame tokens, audio/speech tokens, and text tokens from transcripts, captions, metadata, or OCR-like signals. The encoder learned contextualized representations over both time and modality.

The pretraining stage had two goals. First, I aligned video, audio, and text representations through contrastive learning: matched segments from the same video were treated as positive cross-modal pairs, while mismatched segments were used as negatives. This helped place semantically related visual, audio, and textual signals into a shared representation space. Second, I used temporal prediction objectives over video/audio/text sequences, similar in spirit to wav2vec-style self-supervised learning, so the model could learn sequence-level temporal context rather than only static clip features.

After pretraining, I fine-tuned the encoder on supervised harmful-content labels, including categories such as sexual content, violence, political misinformation, alcohol/drug sales, misleading ads, and normal videos. On top of the encoder, I used a label-wise attention pooling layer: each policy label attended to the encoded video sequence and produced a video-level prediction. The same attention scores also provided temporal evidence, helping reviewers quickly locate suspicious segments instead of inspecting the entire video manually.

### Productionization

I also helped bridge the research-to-production gap during Meta’s transition from Caffe2-heavy deployment workflows to PyTorch/TorchScript-based serving. Around that period, moving models from research to production often required translating PyTorch research code or trained models into graph-mode production representations such as Caffe2, which could be manual, time-consuming, and error-prone. [Meta’s PyTorch 1.0 effort](https://engineering.fb.com/2018/05/02/ai-research/announcing-pytorch-1-0-for-both-research-and-production/?utm_source=chatgpt.com) was explicitly designed to combine PyTorch’s research flexibility with Caffe2/ONNX-style production capabilities and reduce this friction.

By using PyTorch JIT/TorchScript-style deployment, I helped make research models more directly deployable for production inference. This reduced the engineering overhead of rewriting or translating models, shortened the path from model development to online evaluation, and enabled faster iteration for integrity and video-understanding applications.

### Impact

The system improved harmful-content understanding by using multimodal signals rather than relying on vision, audio, or text alone. In downstream integrity applications, it contributed to a major reduction in political misinformation prevalence and improved average prevalence reduction across other harmful-content categories.

It also improved reviewer efficiency. Instead of only producing a video-level label, the transformer framework could help localize suspicious regions through attention or temporal scoring, allowing reviewers to inspect likely violation segments more quickly.

More broadly, this project strengthened my experience in building foundation-model systems that connect self-supervised pretraining, multimodal alignment, supervised fine-tuning, model productionization, and real-world content-understanding impact.