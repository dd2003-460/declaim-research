# Probability as Approximate Inference: The Information-Theoretic Foundations of Bayesian Reasoning

**PhD Writing Sample #2 — Theory Track**  
*Based on Chapter 5 of an unpublished manuscript on the unified framework of pattern matching, information, and cognition.*

---

## 1. Introduction

What happens when the available information is insufficient for deductive certainty? In such cases, rational agents do not abandon inference; they modulate it. This essay develops the claim that Bayesian reasoning is the unique consistent framework for pattern matching under information incompleteness, and that its formal structure can be derived directly from information-theoretic first principles.

The argument proceeds through three stages. First, Section 2 establishes the historical context through a concrete application: Koopman's (1946) operational search theory for anti-submarine warfare, which demonstrates Bayesian updating as a practical decision framework. Second, Section 3 derives the normative justification through the Cox-Jaynes theorem: any inference system satisfying basic consistency axioms is necessarily equivalent to Bayesian probability theory. Third, Section 4 analyzes the gap between normative Bayesian reasoning and actual human performance through Kahneman and Tversky's (1973) base rate neglect phenomenon, demonstrating that intuitive reasoning systematically discards statistical base rates.

Section 5 applies the framework to the COVID-19 pandemic as a large-scale natural experiment in probabilistic reasoning failure. Section 6 synthesizes the contributions by positioning Bayesian reasoning alongside deductive and intuitive inference as three modes of a single pattern-matching engine, distinguished by their information requirements and error tolerances. A methodological discussion follows.

The novel contribution of this essay is the information-theoretic interpretation: Bayesian inference, deductive reasoning, and intuitive pattern matching are not fundamentally different cognitive processes, but rather the same inference engine operating under different compression regimes. Deduction operates under lossless compression (sufficient information for certainty); intuition under lossy compression (speed-optimized with error tolerance); and Bayesian reasoning maintains explicit uncertainty quantification when information is incomplete.

---

## 2. A Wartime Origin: Koopman and the Search Problem

In 1943, German U-boats were sinking Allied shipping at a rate of hundreds of thousands of tons per month, threatening to starve Britain into submission. The tactical problem appeared straightforward: deploy aircraft to patrol the Atlantic, locate submarines, and destroy them. But the Atlantic Ocean spans thirty-three million square kilometers, and a reconnaissance aircraft's field of vision extends only a few kilometers. Even with intelligence constraining the submarine's approximate region, the search area remained computationally intractable by brute-force methods.

The U.S. Navy recruited Bernard Koopman, an operations research mathematician, who approached the problem not as an engineering challenge but as an information allocation problem. His key insight was that the pre-search state of knowledge—the agent's beliefs about the submarine's location—could be represented as a probability distribution over possible positions. This prior distribution incorporated intelligence estimates, last-known positions, submarine speed constraints, and ocean current models.

The critical step was the update mechanism. When an aircraft searched a region and found nothing, this negative observation was itself informative: it reduced the posterior probability that the submarine occupied the searched region, with the magnitude of reduction depending on the search coverage and detection probability. Koopman formalized this as the iterative application of what we now recognize as Bayes' theorem:

$$P(x \mid y) = \frac{P(y \mid x) \cdot P(x)}{P(y)}$$

where $x$ denotes the submarine's position, $y$ denotes the observation (search-and-fail-to-detect), $P(x)$ is the prior distribution, $P(y \mid x)$ is the likelihood of the observation given the position, and $P(x \mid y)$ is the updated posterior distribution.

The operational impact was dramatic. Beginning in May 1943, Allied forces systematically applied probabilistic search allocation. Within three months, U-boat loss rates doubled. By the end of 1943, the German Navy was forced to temporarily withdraw from the Atlantic. One of the war's pivotal turning points was achieved not through superior weaponry but through superior probabilistic inference (Koopman, 1946).

This case study illustrates a pattern we will encounter repeatedly: Bayesian reasoning is not merely a theoretical construct but a normative framework whose practical implementation produces quantifiable improvements in decision-making under uncertainty.

---

## 3. The Cox-Jaynes Theorem: Bayes as Unique Consistency

The submarine example demonstrates that Bayesian updating works in practice. The deeper question is: *why* does it work? Is it merely an effective heuristic, or does it possess a deeper justification?

Cox (1946) and Jaynes (2003) provided a rigorous answer. Cox showed that any system for reasoning under uncertainty that satisfies four basic consistency requirements is necessarily isomorphic to probability theory, and its update rule is necessarily Bayes' theorem. The requirements are:

1. **Associativity of plausibility**: The order of combining evidence does not affect the final result.
2. **Consistency with Boolean logic**: In the limit of certainty, the system reduces to deductive logic.
3. **Continuity**: Small changes in evidence produce small changes in plausibility.
4. **Universality**: The system can represent any proposition, not restricted to specific domains.

Jaynes (2003) extended this result and argued that Bayesian probability represents the unique *calculus of inductive reasoning*—not a statistical method among alternatives, but the mathematical expression of what it means to reason consistently under incomplete information.

The implication is profound: **any rational agent who avoids self-contradiction is necessarily performing Bayesian updating.** The agent does not "choose" Bayesian reasoning from a menu of alternatives; there are no consistent alternatives. A Cox-satisfying system that is not equivalent to Bayesian probability would contain internal contradictions—statements whose truth values depend on the order in which evidence is processed.

From an information-theoretic perspective, the Cox-Jaynes theorem can be restated as follows: Bayesian updating is the unique procedure that achieves maximum information extraction from observations while maintaining representational consistency. Any non-Bayesian procedure either discards available information (suboptimal extraction) or produces internally contradictory beliefs (violating consistency).

This connects directly to Shannon's source coding theorem: just as entropy defines the unique lower bound on lossless compression, Bayes' theorem defines the unique lower bound on information loss during belief updating. You cannot do better; you can only do worse.

---

## 4. Base Rate Neglect: The Gap Between Normative and Actual

If Bayesian reasoning is the unique consistent framework, we should expect human intuitive reasoning to approximate it. Kahneman and Tversky (1973) demonstrated that it does not—in systematic and predictable ways.

Their most influential finding is **base rate neglect**. Consider the following scenario, adapted from their experimental paradigm:

> A disease affects 0.1% of a population (1 in 1,000). A diagnostic test has 95% sensitivity (if diseased, 95% chance of positive result) and 95% specificity (if healthy, 95% chance of negative result). You test positive. What is your probability of actually having the disease?

The modal human response is "approximately 95%." The correct Bayesian answer is approximately 2%.

**Derivation.** Let $D$ denote disease presence and $+$ denote a positive test result. Bayes' theorem gives:

$$P(D \mid +) = \frac{P(+ \mid D) \cdot P(D)}{P(+)}$$

where:
- $P(+ \mid D) = 0.95$ (sensitivity)
- $P(D) = 0.001$ (base rate)
- $P(+) = P(+ \mid D) \cdot P(D) + P(+ \mid \neg D) \cdot P(\neg D) = 0.95 \times 0.001 + 0.05 \times 0.999 = 0.0509$

Therefore:

$$P(D \mid +) = \frac{0.95 \times 0.001}{0.0509} \approx 0.0187 \approx 1.9\%$$

The discrepancy arises because although the test is highly accurate, the base rate is extremely low. Among 1,000 people, approximately 1 is truly diseased (and likely tests positive), but approximately 50 healthy people also test positive (5% false positive rate). Of the ~51 positive results, only ~1 corresponds to actual disease.

The human error is not random but systematic: subjects anchor on the test's 95% accuracy figure and neglect the base rate entirely. Kahneman and Tversky (1974) identified this as an instance of the *representativeness heuristic*—intuitive reasoning matches the observed pattern (positive test → disease) without integrating the statistical context.

Within the framework developed in this essay, base rate neglect represents a specific failure mode of lossy compression in pattern matching. The intuitive system identifies the most salient pattern ("95% accuracy") and discards the base rate as irrelevant background information. This is precisely the behavior of a lossy compressor optimized for speed: it preserves the dominant signal and filters the noise. But in probabilistic reasoning, the base rate is not noise—it is signal. Discarding it produces systematically biased inferences.

The magnitude of the bias is striking: the intuitive estimate (95%) exceeds the correct value (1.9%) by a factor of 50. This is not a minor rounding error; it is a qualitative misrepresentation of the underlying probability landscape.

---

## 5. A Natural Experiment: COVID-19 and Scale-Level Reasoning Failure

The COVID-19 pandemic transformed base rate neglect from a laboratory curiosity into a global-scale policy challenge. Beginning in early 2020, governments implemented mass nucleic acid testing programs. Individual test characteristics appeared adequate: sensitivity of 70–95% and specificity typically exceeding 99%.

The problem lay in the base rates. During early pandemic phases, actual infection rates in many regions were below 0.1%. At such base rates, even a test with 95% sensitivity and 99.9% specificity yields a positive predictive value below 50%:

$$P(\text{infected} \mid +) = \frac{0.95 \times 0.001}{0.95 \times 0.001 + 0.001 \times 0.999} = \frac{0.00095}{0.001949} \approx 48.7\%$$

More than half of positive results corresponded to healthy individuals. The downstream consequences—unnecessary quarantines, public panic, resource misallocation—were direct consequences of probabilistic reasoning failure at societal scale.

The information-theoretic interpretation is revealing. Human social information transmission mechanisms—news media, social networks, government announcements—are inherently lossy compressors optimized for transmission efficiency. The headline "500 new cases today" is dramatically more compressible and transmissible than "among today's test-positive results, approximately 200 likely represent true infections with a 95% confidence interval of [150, 260]." The social transmission system systematically discards uncertainty information because uncertainty is incompressible.

This connects to the theme of the next chapter (social systems as distributed pattern matching): when individual Bayesian reasoning is already compromised by base rate neglect, and social transmission mechanisms further compress away uncertainty information, the result is a cascading amplification of probabilistic reasoning errors at the collective level.

---

## 6. Three Modes of Inference: A Synthesis

The preceding chapters have identified three distinct modes of pattern matching, which we can now formalize within a unified information-theoretic framework:

**Deductive inference** (Chapter 4): The known premises $H$ fully determine the conclusion $C$. Information transfer is lossless. The compression ratio is fixed. The path from $H$ to $C$ is uniquely determined, as in solving $2x = 6$ where $x = 3$ is the only valid answer. Formally: $H(C \mid H) = 0$ (zero conditional entropy given the premises).

**Intuitive pattern matching** (Chapter 3): The known premises $H$ partially determine the conclusion $C$. The brain applies lossy compression, skipping intermediate steps in pursuit of speed. Output may be correct or incorrect. Formally: $0 < H(C \mid H) < H(C)$ (partial information, nonzero conditional entropy). The processing is governed by rate-distortion tradeoffs: faster processing requires accepting higher distortion (error).

**Bayesian inference** (this chapter): The known premises $H$ partially determine the conclusion $C$, but the agent *explicitly maintains uncertainty*. Rather than asserting "the answer is $X$," the agent states "the probability that the answer is $X$ is $p$." New evidence $y$ updates this probability via Bayes' theorem. Formally: $H(C \mid H, y) < H(C \mid H)$ (each observation reduces conditional entropy, but never to zero unless sufficient information accumulates).

The critical distinction is not between these three modes but between the *conditions under which each is appropriate*:

| Mode | Information Condition | Error Tolerance | Formal Property |
|------|----------------------|-----------------|-----------------|
| Deduction | $H(C \mid H) = 0$ | Zero | Lossless path exists |
| Intuition | $H(C \mid H) > 0$, time-constrained | Nonzero | Rate-distortion optimal |
| Bayesian | $H(C \mid H) > 0$, time-available | Quantified | Entropy-minimizing update |

The deepest insight is that these are not fundamentally different cognitive processes but **different gears of the same inference engine**. A skilled reasoner shifts between them fluidly: using intuition to rapidly narrow the search space, applying Bayesian reasoning to allocate probability across the remaining hypotheses, and engaging deductive verification for high-probability candidates.

This reinterpretation of deliberate practice (Ericsson et al., 1993) reveals its information-theoretic essence: training is not the accumulation of knowledge but the development of skill in selecting the appropriate inference mode for each situation—the meta-cognitive ability to assess one's own information state and deploy the corresponding gear.

---

## 7. The Prior Problem: Where Does Bayes Begin?

Bayesian updating is optimal as an *update rule*, but its practical application depends critically on the choice of prior distribution $P(x)$. In the submarine search problem, priors derived from intelligence and physical constraints are relatively objective. In many other domains—medical diagnosis with rare diseases, financial forecasting, scientific hypothesis evaluation—the prior is a subjective choice that can dominate the posterior even after substantial evidence accumulation.

This is not a defect of the Bayesian framework but an *essential feature of inference under incompleteness*: when information is genuinely absent, some assumption must be made to initiate the reasoning process. Frequentist approaches attempt to evade this issue by claiming to derive conclusions solely from data, but the prior is merely relocated—to experimental design choices, model selection criteria, and significance thresholds—rather than eliminated (Jaynes, 2003, Ch. 1–3).

Jaynes' maximum entropy principle offers one resolution: choose the prior distribution that satisfies known constraints while maximizing Shannon entropy, representing the "least assumptive" choice. This prior is uniquely determined by the available constraints and represents genuine ignorance about all unspecified aspects of the problem.

From the pattern-matching perspective, the prior corresponds to the *initial pattern library*—the set of hypotheses available for matching before any data is observed. A well-chosen prior accelerates convergence (as in the successful submarine search), while a poorly chosen prior may resist correction by any finite amount of data.

This observation connects directly to the social dimension developed in subsequent chapters: when groups of agents share priors—through cultural transmission, institutional training, or common experience—the resulting collective inference can be either dramatically more efficient (shared expertise) or systematically biased (shared blind spots).

---

## 8. Methodological Discussion

### 8.1 Framework Positioning

This essay occupies a theoretical position at the intersection of information theory, cognitive science, and epistemology. It does not present new empirical data or computational experiments. Its claims are conceptual and formal: that Bayesian reasoning, deductive inference, and intuitive pattern matching can be unified within a single information-theoretic framework defined by the agent's information state and processing constraints.

The framework extends the dual-process theory of cognition (Kahneman, 2011) by providing formal criteria for distinguishing System 1 (intuitive, lossy-compression) from System 2 (deliberative, lossless or probabilistic) processing. Where Kahneman's original formulation relies on phenomenological descriptions (fast vs. slow, effortless vs. effortful), the information-theoretic reformulation offers precise formal boundaries: System 1 operates at high compression ratios with quantifiable distortion; System 2 operates at lower compression ratios (or losslessly) with explicit uncertainty maintenance.

### 8.2 Limitations

Several limitations should be acknowledged:

1. **Theoretical scope**: The framework is developed through illustrative case studies (submarine search, medical diagnosis, pandemic testing) rather than formal derivation from axioms to full cognitive theory. A complete treatment would require formalizing the rate-distortion boundaries for specific cognitive tasks and empirically validating the predicted compression-error tradeoffs.

2. **Base rate neglect interpretation**: The claim that base rate neglect represents "lossy compression discarding background information" is a post-hoc interpretation consistent with the data, not a uniquely determined explanation. Alternative cognitive mechanisms (e.g., causal model neglect, as proposed by Tversky & Kahneman, 1980) may provide equally valid accounts.

3. **Bayesian cognitive science**: The claim that human cognition *should* be Bayesian (the "Bayesian brain" hypothesis, cf. Griffiths, Chater, Norris, & Pouget, 2010) is itself contested. Resource-rational analysis (Lieder & Griffiths, 2020) suggests that bounded agents may optimally deviate from Bayesian updating when computation itself is costly.

### 8.3 Testable Predictions

The framework generates several empirically testable predictions:

- **P1**: Tasks requiring explicit base rate integration should show longer response times and higher error rates than matched tasks where base rates are incorporated into the likelihood function—because the latter can be processed by the lossy-compression (intuitive) system.
- **P2**: Expert diagnosticians should show reduced (but not eliminated) base rate neglect compared to novices, representing training-induced recalibration of the intuitive compression algorithm.
- **P3**: Explicit uncertainty displays (e.g., "1.9% probability of disease") should substantially improve decision quality compared to categorical displays ("positive/negative"), with the improvement magnitude proportional to the base rate deviation from 50%.

---

## Conclusion

This essay has argued that Bayesian reasoning occupies a precise position in the information-theoretic landscape of inference: it is the unique consistent framework for pattern matching when information is incomplete and uncertainty must be explicitly maintained. The Cox-Jaynes theorem provides the normative foundation (Bayesian updating is the only consistent belief revision procedure), while the empirical phenomena of base rate neglect reveal the systematic failures that occur when intuitive lossy compression substitutes for explicit probabilistic reasoning.

The synthesis across three chapters yields a unified picture: deduction, intuition, and Bayesian inference are not fundamentally different cognitive processes but different operating modes of a single pattern-matching engine, governed by the available information, time constraints, and error tolerance. Understanding when to deploy each mode—and developing the metacognitive skill to assess one's own information state—may be the deepest form of intelligence.

---

## References

- Cox, R. T. (1946). Probability, frequency and reasonable expectation. *American Journal of Physics*, 14(1), 1–13.
- Ericsson, K. A., Krampe, R. T., & Tesch-Römer, C. (1993). The role of deliberate practice in the acquisition of expert performance. *Psychological Review*, 100(3), 363–406.
- Griffiths, T. L., Chater, N., Norris, D., & Pouget, A. (2010). How the Bayesians got their beliefs (and what those beliefs really are). *Psychological Bulletin*, 136(3), 395–406.
- Jaynes, E. T. (2003). *Probability Theory: The Logic of Science*. Cambridge University Press.
- Kahneman, D. (2011). *Thinking, Fast and Slow*. Farrar, Straus and Giroux.
- Kahneman, D., & Tversky, A. (1973). On the psychology of prediction. *Psychological Review*, 80(4), 237–251.
- Kahneman, D., & Tversky, A. (1974). Judgment under uncertainty: Heuristics and biases. *Science*, 185(4157), 1124–1131.
- Koopman, B. O. (1946). Search and screening. *Operations Evaluation Group Report No. 56*.
- Lieder, F., & Griffiths, T. L. (2020). Resource-rational analysis: Understanding human cognition as the optimal use of limited resources. *Topics in Cognitive Science*, 12(3), 933–980.
- Shannon, C. E. (1948). A mathematical theory of communication. *Bell System Technical Journal*, 27(3), 379–423.
- Tversky, A., & Kahneman, D. (1980). Causal schemas in judgments under uncertainty. In M. Fishbein (Ed.), *Progress in Social Psychology* (Vol. 1, pp. 49–72). Erlbaum.
