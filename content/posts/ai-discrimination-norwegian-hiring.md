+++ 
date = "2025-11-16"
title = "When AI Learns to Discriminate: The surprising way Norwegian hiring algorithms amplify bias"
slug = "ai-discrimination-norwegian-hiring" 
tags = ["AI", "Ethics", "Machine Learning", "Norway"]
categories = ["Product"]
series = ["AI Ethics", "Opinion"]
image = "/library/ai_ethics/ai_ethics_1.png"
+++

[Despite Norway's egalitarian reputation, research shows ample evidence of discrimination against ethnic minorities in hiring processes](https://www.sv.uio.no/iss/english/research/projects/navigate/). 

The adoption of AI and machine-learning algorithms in recruitment has increased significantly in recent years, something the [Norwegian Equality and Anti-Discrimination Ombud (LDO) highlights in its report on algorithms and discrimination](https://ldo.no/content/uploads/2025/05/Algorithms-artificial-intelligence-and-discrimination-report.pdf). Because these systems are trained on historical hiring data shaped by decades of underrepresentation of women, immigrants, and candidates from remote Norway, there is a high likelihood that societal biases were embedded into the models from the beginning. In most cases, algorithms simply inherit these patterns and learn them as if they were normal.

One can suspect it being a technical bug, maybe poor feature engineering or overfitting initially. But most often AI systems simply just inherited our biases from historical data context.


I wanted to explore and document more on this topic as Recruitment AI is explicitly labeled a “high-risk system” under the EU AI Act.


## Stories from the ground

I heard several friends talking about how young immigrant professionals change their names to more “Norwegian-sounding” ones just to get a fair shot at interviews which is also one of the mentioned case in ([NAVIGATE, UiO](https://www.sv.uio.no/iss/english/research/projects/navigate/)). 


## Amplification of Bias

I have now spent quite some time learning about how machine learning models learn from data, technical and ethical consequences of it. When a model makes hiring decisions, over time it creates something we call  "bias amplification", and understanding this feedback loop is critical.

Here's how the cycle works for example:

**Year 0: The Starting Point**  
A company builds an AI hiring system using historical data. This data already contains bias. Women from Northern Norway got 40% fewer interviews than equally qualified men from Oslo in past human led hiring.

**Year 1: First Generation Model**  
The model learns from this biased history. It notices patterns: "Successful candidates tend to be men from Oslo. Women from Tromsø are rare among past hires." The model makes predictions based on these patterns. The gap persists at 40%.

**Year 2: The Amplification Begins**  
The company retrains the model to "improve it" using Year 1's data. But Year 1's data now includes the AI's own biased decisions. The model is learning from itself. The pattern strengthens. The gap grows to 50%.

**Year 3: Normalized Discrimination**  
Another retraining cycle. The model now has two years of its own biased outputs in the training data. The algorithm has learned that this disparity is "normal." The gap reaches 65%.

**Year 4 and Beyond: Runaway Bias**  
Each cycle makes the bias stronger because the model is learning from its own biased outputs. What started as a reflection of human bias becomes algorithmic certainty.

If a company retrain their models quarterly or annually to "improve performance." Without intervention, they're unknowingly building amplification machines. [The Norwegian Equality and Anti Discrimination Ombud has raised concerns about exactly this kind of algorithmic discrimination](https://ldo.no/content/uploads/2025/05/Algorithms-artificial-intelligence-and-discrimination-report.pdf).

## Real example in Norwegian tech sector

While women make up around 49 percent of Norway’s population ([Statistics Norway – Population by gender](https://www.ssb.no/en/befolkning/folketall/statistikk/befolkning)), only about 22 percent of workers in IT occupations are women ([Statistics Norway – Many more have IT-occupations](https://www.ssb.no/arbeid-og-lonn/sysselsetting/artikler/mange-flere-har-it-yrker)). This contrast shows a clear underrepresentation in the tech sector.


When an AI hiring model is trained on this kind of historically imbalanced data, it tends to learn that “successful candidates” look like the majority group. As a result, qualified applicants from underrepresented regions or demographic groups can be treated as statistically unusual by the model, leading to compounded disadvantage with each retraining cycle. This amplification mechanism is well documented in algorithmic fairness research ([Barocas & Selbst, 2016](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2477899), [Raghavan et al., 2020](https://dl.acm.org/doi/10.1145/3351095.3372828)).

## Technology and regulation converging

This brings us to the regulatory landscape. Norway, along with the EU, is moving toward requiring AI systems to meet fairness standards, with the EU AI Act specifically addressing bias in high risk applications like hiring. Given that [one in four Norwegian businesses now uses AI](https://practiceguides.chambers.com/practice-guides/artificial-intelligence-2025/norway/trends-and-developments), this isn't a distant concern, it's happening right now.

## Solution: Starting simple with reweighting

After studying about fairness interventions, I've found that you don't need to start with complex solutions. While there are sophisticated approaches for different fairness goals (demographic parity, equal opportunity, individual fairness, the simplest intervention that actually works is something called reweighting. 

Think of it like this. Imagine you're training a model to recognize "qualified candidates" but your training data is heavily skewed:

**Before reweighting:**

Every candidate, regardless of background, contributes equally to the model's learning:

* Oslo male candidate: weight = 1.0
* Oslo female candidate: weight = 1.0  
* Tromsø male candidate: weight = 1.0
* Tromsø female candidate: weight = 1.0

**After reweighting:**

We adjust how much the model learns from each group to balance representation:

* Oslo male candidate: weight = 0.7 *(reduce overrepresentation)*
* Oslo female candidate: weight = 1.1 *(balance gender in majority region)*
* Tromsø male candidate: weight = 2.0 *(boost underrepresented geography)*
* Tromsø female candidate: weight = 3.5 *(address intersectional disadvantage)*

This way, the model learns that a "typical qualified candidate" isn't just someone who looks like the historical majority. It prevents the system from treating "most common" as "most qualified."

## Looking forward

As I think about these insights, my view is that the future of AI in Norwegian hiring will be shaped by three forces:

Firstly, regulatory pressure from the [EU AI Act ](https://artificialintelligenceact.eu/high-level-summary/) , which classifies recruitment and employment-related AI systems as *high-risk* and therefore subject to strict transparency, data quality, and fairness requirements. 

Secondly, a growing national awareness of algorithmic discrimination, highlighted in multiple investigations by the [Norwegian Equality and Anti-Discrimination Ombud](https://ldo.no/content/uploads/2025/05/Algorithms-artificial-intelligence-and-discrimination-report.pdf). 

Finally, the businesses that choose to implement fairness strategies proactively rather than waiting until compliance becomes mandatory.

What is clear is that bias amplification in AI is not just an abstract risk, it appears in real datasets, in real companies, right now. The encouraging part is that practical solutions exist. 

Honestly, as someone who builds AI systems, I believe we have a responsibility to ensure our models don't amplify the very inequalities we claim to want to eliminate. It starts with acknowledging the problem, understanding the mechanisms, and taking concrete steps toward fairness.

---

**What's your experience with AI in hiring? Have you witnessed these patterns in Norwegian workplaces? I'd love to hear your perspective.**

*This is the first in a series exploring AI fairness. If you're equally or more interested in how technology, fairness in AI systems and geopolitics, feel free to connect with me on LinkedIn.*

**#AIEthics #Norge #Rekruttering #MachineLearning #Diversity #FairnessInAI #NorskArbeidsliv**

---

<br>
<br>

________________________

If you enjoy staying updated on technology, business, and the universe, feel free to read me on Substack.

<iframe src="https://pysaurav.substack.com/embed" width="480" height="320" style="border:1px solid #EEE; background:white;" frameborder="0" scrolling="no"></iframe>

