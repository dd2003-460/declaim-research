# PhD Research Statement

**Candidate**: Cheng Lu
**Target Fields**: Computer Science / Computational Social Science / Information Theory

---

## Research Vision

Can we measure the *information content* of scientific progress?

This question sits at the intersection of information theory, natural language processing, and the science of science. My research program—spanning a monograph on pattern matching and cognition, an empirical pipeline for detecting scientific paradigm shifts, and information-theoretic analyses of social phenomena—aims to develop a quantitative framework for understanding how knowledge evolves, propagates, and creates value.

---

## Background: Understanding as Compression

My intellectual starting point is an observation that unifies three seemingly disparate domains: *understanding is compression*.

Shannon's source coding theorem (1948) establishes that any lossless description of a data source requires at least $H(X)$ bits. Kolmogorov complexity (1965) extends this from ensembles to individual objects: the complexity of an object is the length of the shortest program that outputs it. The convergence of these two results suggests a radical reinterpretation of cognition itself—to understand something is to find a compressed representation of it, whether through statistical regularities (Shannon) or algorithmic structure (Kolmogorov).

I developed this framework in an unpublished monograph, *Pattern Matching as Inference: A Unified Framework from Information to Cognition*, structured as five investigations of five questions across five levels of abstraction. The book argues that mathematical proof, scientific intuition, Bayesian updating, and Kahneman's dual-process theory are all instances of the same underlying operation: pattern matching at different compression ratios. Chapter 2 (Understanding as Compression) was selected and polished as a PhD writing sample; Chapter 5 (Probability as Approximate Inference) demonstrates how probability theory emerges as the unique consistent framework for reasoning under incomplete information, drawing on the Cox-Jaynes derivation and empirical cases from submarine search (Koopman, 1946) to COVID-19 social behavior.

This theoretical foundation is not merely philosophical—it yields falsifiable predictions. If understanding is compression, then paradigm shifts should be detectable as *discontinuities in compressibility*: moments when the scientific community's shared model of a field breaks down and must be rebuilt.

---

## Current Work: Detecting Scientific Paradigm Shifts

My current paper, "Detecting Scientific Paradigm Shifts via Automated Topic Changepoint Analysis," operationalizes this insight. The pipeline applies Latent Dirichlet Allocation (LDA) to 1,500 arXiv abstracts across four categories (cs.AI, cs.CL, cs.CV, quant-ph) from January 2024 to March 2026, identifies topic-level time series, and applies Bayesian changepoint detection to locate structural breaks in scientific discourse.

The key methodological contribution is rigorous validation through a control group design. When changepoint-derived "signals" are tested against equity returns in related sectors using event study methodology, initial results appear promising: 13/13 signals show positive cumulative abnormal returns. However, when compared against 100 randomized control events, this "100% hit rate" is statistically indistinguishable from chance at all windows beyond 1 day (3-day, 7-day, 14-day: all p > 0.05). The 1-day result itself is fragile—Bonferroni correction across 8 tests reduces significance to p = 0.0096.

Rather than framing this as failure, I argue it is a contribution. The paper makes four points: (1) an open-source pipeline for real-time discourse changepoint detection, extending Blei & Lafferty (2006) from retrospective to prospective analysis; (2) a case study in how survivorship bias inflates false positives when control groups are absent; (3) a power analysis demonstrating that n = 13 signals yield only 15–20% statistical power for detecting medium effects; and (4) a negative result that saves future researchers from repeating this specific experiment. The paper is prepared for arXiv submission and targeted at FinNLP 2026 / EMNLP 2026.

---

## Future Research Directions

My PhD research would extend this program in three directions:

### 1. Information-Theoretic Measures of Scientific Impact

Current impact metrics (citations, h-index, altmetrics) are lagging indicators. I propose developing *information surprise* measures: quantifying how much a new paper reduces the entropy of the field's knowledge state. A paper that eliminates a major uncertainty (e.g., resolving a long-standing conjecture) should score higher than one that incrementally extends known results, regardless of citation count. This requires formalizing the "knowledge state" of a field as a probability distribution over possible findings and measuring the KL-divergence induced by new publications.

### 2. Cross-Lingual Knowledge Propagation

Scientific knowledge flows unevenly across linguistic boundaries. Using the changepoint detection pipeline applied to multilingual corpora (Chinese, English, and other major research languages), I aim to quantify the *translation lag*—the delay between paradigm shifts in different linguistic communities—and identify factors that accelerate or impede cross-lingual knowledge transfer. This has practical implications for research policy and equitable access to scientific advances.

### 3. Compression as a Model for Scientific Explanation

If understanding is compression, then the *quality* of a scientific explanation should correlate with the compression ratio it achieves. I propose testing this by measuring how much various explanations of the same phenomenon (e.g., different theories of attention in cognitive science) compress empirical data, using modern language models as the compression engine. This would provide a quantitative, model-agnostic framework for comparing competing scientific theories—not by their rhetorical appeal, but by their informational efficiency.

---

## Why a PhD

The questions I pursue require sustained engagement with three communities: information theorists who provide the mathematical foundations, NLP researchers who build the empirical tools, and science of science scholars who define the domain questions. An academic environment offers the interdisciplinary collaboration, computational resources, and peer review infrastructure that independent research cannot sustain.

My background—spanning technical writing, quantitative analysis, and information-theoretic thinking—positions me to bridge these communities. The monograph demonstrates theoretical depth; the paradigm shift paper demonstrates empirical rigor; the negative result demonstrates intellectual honesty. What I lack is the mentorship, collaboration network, and institutional platform that a PhD program provides.

I am particularly drawn to programs that value unconventional intellectual trajectories and interdisciplinary synthesis. The questions I ask—how does knowledge compress? when do paradigms shift? can we measure understanding?—do not fit neatly into existing subfields. They require a PhD program that rewards boundary-crossing over boundary-defending.

---

## Selected References

- Blei, D. M., & Lafferty, J. D. (2006). Dynamic topic models. *ICML*.
- Cover, T. M., & Thomas, J. A. (2006). *Elements of Information Theory*. 2nd ed., Wiley.
- Jaynes, E. T. (2003). *Probability Theory: The Logic of Science*. Cambridge University Press.
- Kolmogorov, A. N. (1965). Three approaches to the quantitative definition of information. *Problems of Information Transmission*, 1(1), 1–7.
- Shannon, C. E. (1948). A mathematical theory of communication. *Bell System Technical Journal*, 27(3), 379–423.

---

*Prepared March 2026. Based on monograph manuscript and empirical research in progress.*
