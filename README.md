⸻

The Fragility of Economic Explanations under Length Constraints

Evidence from Large Language Models

Overview

This repository documents an exploratory empirical study on how large language models (LLMs) adjust their economic reasoning and materiality judgments under explicit length constraints.

Rather than evaluating whether model answers are “correct,” this project focuses on how models prioritize, compress, and omit information when forced to generate shorter responses. The core question is:

At what point does compression shift from efficiency to fragility in economic explanations?

This study treats length constraints as an economic cost shock and observes the resulting changes in model judgment behavior.

⸻

Research Motivation

In real-world applications—such as auditing, policy analysis, and professional reporting—economic reasoning is rarely unconstrained. Explanations must be delivered within tight word limits, executive summaries, or standardized reporting formats.

Despite this, most LLM evaluations assume unconstrained outputs.

This project asks a different question:

	How does forced brevity alter what an LLM considers material?
	
	Are certain economic domains more fragile under compression?
	
	Can this fragility be measured quantitatively?

⸻

Data Source

All questions used in this study are sourced from publicly available Korean CPA examination problems and national civil service examination questions.

These problems are designed to evaluate professional-level economic judgment, including materiality assessment, trade-offs, and prioritization under implicit constraints.
	No proprietary or confidential datasets were used.
	No copyrighted answer keys were incorporated.
	The questions were used solely as prompts for model-generated responses.

⸻

Experimental Design

Models
	
	GPT-family model
	
	Gemini-family model

Prompt Conditions

Each question was evaluated under two conditions:
	
	1. Baseline: unconstrained response
	
	2. Length-constrained: approximately 150 words

The same prompt structure and temperature settings were applied across models to ensure comparability.

⸻

Domain Classification

Each question belongs to one of the following domains:
	 
	  growth: firm growth, investment, and expansion-related questions
	  
	  intl: international economics and cross-border policy questions
	  
	  macro: macroeconomic and policy-level questions

Note: The label intl refers to international economics, not internal or organizational decision-making.

⸻

Measurement Framework

Materiality Score

A custom materiality score is computed for each response, capturing the degree to which economically significant elements are preserved under compression.

Δ Materiality

\Delta = \text{Score}_{constrained} - \text{Score}_{baseline}

Negative values indicate materiality loss due to compression.

Elasticity

Elasticity = \frac{\%\ \text{Materiality Loss}}{\%\ \text{Word Reduction}}

This captures how sensitive a model’s judgment is to compression pressure.

⸻

V-index (Vulnerability Index)

The V-index aggregates multiple fragility signals into a single indicator of judgment vulnerability under constraints.
It combines:
	  
	  mean materiality loss
	  
	  elasticity magnitude
	  
	  cross-model variance
	  
	  domain-specific sensitivity

The index is designed as an observational diagnostic, not a performance leaderboard.

⸻

Key Findings (Preliminary)
	 
	 Materiality loss is systematic, not random.
	 
	 International and macroeconomic questions exhibit higher fragility under compression.
	 
	 Models differ not only in magnitude of loss, but in which information is sacrificed.
	 
	 Shorter explanations are not necessarily worse—but beyond a threshold, judgment structure degrades nonlinearly.

These patterns are stable across repeated experimental runs.

⸻

Repository Structure

 .
 
 ├── README.md
 
 ├── analysis/
 
 │   ├── score_calculation.ipynb
 
 │   ├── elasticity_analysis.ipynb
 
 │   └── regression_checks.ipynb
 
 ├── plots/
 
 │   ├── score_scatter.svg
 
 │   ├── delta_scatter.svg 
 
 │   ├── domain_bar.svg
 
 │   └── elasticity_hist.svg
 
 └── notes/
 
	└── experimental_log.md


⸻

Scope and Limitations
	
	 This project does not claim causal identification.
	 
	 The analysis focuses on judgment behavior, not factual accuracy.
	 
	 Results should be interpreted as diagnostic observations, not model rankings.

The goal is to provide a transparent framework for observing how economic reasoning changes when space becomes costly.

⸻

Intended Use

This repository is shared for:
	 
	 academic discussion
	 
	 methodological feedback
	 
	 reproducibility and transparency

It is not intended for commercial deployment or benchmark competition.

⸻

Status

This is an ongoing study.
Additional data points will be added incrementally as part of a longer-term observation window.

⸻

Contact

For questions or feedback, please contact:
hjjy151225@snu.ac.kr

Kim Minseok
Graduate Student, Accounting
Seoul National University
