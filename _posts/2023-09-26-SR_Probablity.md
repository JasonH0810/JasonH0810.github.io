---
title: '[Studying record] MIT 6.041 Probabilistic Systems Analysis And Applied Probability'
date: 2023-09-26
permalink: /posts/2023/09/SR_Probobility/
tags:
  - Probability
  - Study Record
---


MIT 6.041

[Course Link](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/)

Lecture 1 Introduction
======
- Probability as a mathematical framework for reasoning about uncertainty

- Probabilistic models
  - sample space $\Omega$:list(set) of possible outcomes
    - Mutually exclusive: Two or more events cannot happen simultaneously
    - Collectively exhaustive: $P_1+P_2+...+P_n=1$ encompass the entire range of possible outcomes

  - probability law
    - Discrete uniform law: P(A) = $$\frac{Number Of Elements Of A}{Total Number Of Sample Points}$$
      Computing probabilities $\equiv$ counting
    - Continues uniform law: Probability = Area
      P((x,y)=(0.5,0.3)) = 0
    - Countably infinite sample space:
      - Countable additivity axiom:
        If $A_1,A_2$,... are disjoint events, then:
        $$P(A_1 \cup A_2 \cup ...) = P(A_1) + P(A_2) +...$$

- Axioms of probability
  - **Event** : a subset of the sample space
  - Probability is assigned to events
  - Axioms:
    - **Nonegativity**: P(A) $\geq$ 0    
    - **Normalization**: P($\Omega$) = 1   
    - **Additivity**: P(A $\cup$ B)=P(A) + P(B) - P(A $\cap$ B)

[Lecture record](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/resources/lecture-1-probability-models-and-axioms/)
[Recitation](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/resources/mit6_041f10_rec01/)

Lecture 2 Conditioning and Bayes' Rule
======
- Conditional Probability:
  P(A|B) = probability of A, given that B occurred (B becomes new universe)

  - Definition: Assuming P(B) $\neq$ 0,

    $$P(A | B) = \frac{P(A \cup B)}{P(B)}$$


- Three important tools:
  - Multiplication rule:

    $$P(A \cup B \cup C) = P(A) · P(B | A) · P(C | A \cup B )$$


  - Total probability theorem:

    $$P(B) = P(A_1)P(B | A_1) + P(A_2)P(B | A_2) + P(A_3)P(B | A_3)$$


  - Bayes' rule:

    $$P(A_i | B) = \frac{P(A_i \cup B)}{P(B)}$$

    $$= \frac{P(A_i)P(B | A_i)}{P(B)}$$

    $$= \frac{P(A_i)P(B | A_i)}{\Sigma_j P(A_j)P(B | A_j)}$$


[Lecture Record](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/resources/lecture-2-conditioning-and-bayes-rule/)
[Recitation](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/resources/mit6_041f10_rec02/)