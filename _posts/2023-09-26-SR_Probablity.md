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
    - Discrete uniform law: P(A) = $$\frac{Number \ Of \ Elements \ Of \ A}{Total \ Number \ Of \ Sample \ Points}$$
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


Lecture 3 Independence
------

- Independence of two event

  "Defn:" $ P(B \mid A) = P(B)$ or occurence of A provides no information about B's occurence

  "Defn:" $ P(A \cap B ) = P(A) * P(B)$

  Symmetric with respect to A and B

  (Venn diagram is never enough to decide independence)

  Conditioning may affect independence

- Independence of a collaction of events

    $$P(A_i \cap A_j \cap ... \cap A_q) = P(A_i)P(A_j)...P(A_q) $$

    for any distinct indices i,j,...,q(chosen from 1-n)

    Pairwise independence does not imply independece


[Lecture record](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/resources/lecture-3-independence/)
[Recitation](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/resources/mit6_041f10_rec03/)


Lecture 4 Counting
------

- Principles of counting

  r stages, $n_i$ choices at stage i, then the number of choices is $n_1 n_2 n_3 ... n_r$

  permutations: Number of ways of ordering n element: n(n-1)(n-2)...1 = n!

  Combinations: Number of k-element subsets of a given n-element set: $\tbinom{n}{k}=\frac{n!}{k!(n-k)!}$

- Binomial Probabilities:

  $$ P(k heads) = \tbinom{n}{k}p^k (1-p)^{n-k}$$

[Lecture record](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/resources/lecture-4-counting/)
[Recitation](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/resources/mit6_041f10_rec04/)


Lecture 5 Discrete Random Variables
------

- Random variables
  - A function from the sample space $\Omega$ to the real numbers
  - can have several random variables defined on the same sample space
  - Notation:
    - random variables X
    - numerical value x

- Probability mass function(PMF)
  - $p_X(x) = P(X = x) = P({ \omega \in \Omega \ s.t. \ X(\omega) = x })$
  - $\sum\limits_x p_X(x) = 1 \ \ \ p_X(x) \leq 0$ 

- How to compute a PMF
  - collect all possible outcomes for which X is equal to x
  - add their probabilities 
  - repeat for all x

- Binomial PMF
  - X: number of heads in n independent coin tosses
  - $p_X(k) = \tbinom{n}{k}p^k(1-p)^{n-k} , k=0,1,...,n$

- Expectation
  - Definition: $E[x] = \sum\limits_x p_X(x)$
  - Interpretations:
    - Center of gravity of PMF
    - Average in large number of repetitions of the experiment 

- Properties of expectations
  - Let X be a r.v. and let Y = g(X):
    - $E[Y] = \sum\limits_y yp_Y(y)$ = $E[Y] = \sum\limits_x g(x)p_X(x)$  
    - Caution! $E[g(X)] \ne g(E[X])$


  - If $\alpha, \beta$ are constants, then:
    - $E[\alpha] = \alpha$
    - $E[\alpha X] = \alpha E[X]$
    - $E[\alpha X + \beta] = \alpha E[X] + \beta$

- Variance 
  - $E[g(X)] = \sum\limits_xg(x)p_X(x)$
  - $E[X^2] = \sum_x x^2 p_X(x)$
  - var(X) = $E[(X - E[X])^2] = \sum\limits_x(x-E[X])^2p_X(x) = E[X^2] - (E[X])^2$
  - Properties:
    - var(X) $\leq$ 0
    - $var(\alpha X+\beta) = \alpha^2var(X)$
    - standard deviation: $\sigma_X = \sqrt{var(X)}$


[Lecture record](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/resources/lecture-5-discrete-variables-probability-expectations/)
[Recitation](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/resources/mit6_041f10_rec05/)



Lecture 6 Discrete Random Variables 2
------

- Conditioal PMF and expectation
  - $p_{X \mid A}(x) = P(X=x \mid A)$
  - $E[X \mid A] = \sum\limits_x xp_{X \mid A}(x)$

- Geometric PMF
  - X: number of independent coin tosses until first head
  - $ p_X(k) = (1-p)^{k-1}p  k=1,2,3,...$
  - $ E[X] = \sum\limits_{k=1}\limits^{\infty} kp_X(k)$
  - Memoryless property: Given that X > 2, the r.v. X-2 has same geometric PMF

- Total Expectation theorem
  - Partition of sample space into disjoint events $A_1,A_2,...,A_n$
    - $ P(B) = P(A_1)P(B \mid A_1)+...+ P(A_n)P(B \mid A_n)$
    - $ p_X(x) = P(A_1)p_{X \mid A_1}(x)+...+P(A_n)p_{X \mid A_n}(x) $
    - $ E[X] = P(A_1)E[X \mid A_1 ]+...+ P(A_n)E[X \mid A_n ]$

- Joint PMFs
  - $ p_{X,Y}(x,y) = P(X=x \ and \ Y=y) $
  - $ p_X(x) = \sum\limits_y p_{X,Y}(x,y)$
  - $ p_{X \mid Y}(x \mid y) = P(X=x \mid Y=y) = \frac{p_{X,Y}(x,y)}{p_Y(y)}$


[Lecture record](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/resources/lecture-6-discrete-random-variable-examples-joint-pmfs/)
[Recitation](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/resources/mit6_041f10_rec06/)