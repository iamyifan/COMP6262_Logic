# Mid-Term Assessment

**Name: Yifan Luo**

**UID: u7351505**

## Q1

The valid sequent to be proved: 
$$
\begin{align*}
\neg{\forall{x}P{x}} \vdash \exist{x}\neg{P{x}}
\end{align*}
$$
By ND:

| Assumption | Line  |           Formula           |          Derivation           |
| :--------: | :---: | :-------------------------: | :---------------------------: |
| $\alpha_1$ | $(1)$ |   $\neg{\forall{x}P{x}}$    |          $\text{A}$           |
| $\alpha_2$ | $(2)$ | $\neg{\exist{x}\neg{P{x}}}$ |          $\text{A}$           |
| $\alpha_3$ | $(3)$ |        $\neg{P{a}}$         |          $\text{A}$           |
| $\alpha_3$ | $(4)$ |    $\exist{x\neg{P{x}}}$    |      $3\ \exist\text{I}$      |
| $\alpha_2$ | $(5)$ |      $\neg\neg{P{a}}$       | $2, 4[\alpha_3] \ \text{RAA}$ |
| $\alpha_2$ | $(6)$ |           $P{a}$            |        $5 \neg\neg{E}$        |
| $\alpha_2$ | $(7)$ |      $\forall{xP{x}}$       |     $6 \ \forall\text{I}$     |
| $\alpha_1$ | $(8)$ |   $\exist{x{\neg{P{x}}}}$   | $1, 7[\alpha_2] \ \text{RAA}$ |

The above derivation includes $\exist\text{I}, \forall{\text{I}} \text{ and RAA(} \neg{I}, \neg{E}\text{)}$ as required.

By ST:

| Line  | Truth Value |         Formula         |    Derivation     |
| :---: | :---------: | :---------------------: | :---------------: |
| $(1)$ | $\text{T}$  | $\neg{\forall{x}P{x}}$  |                   |
| $(2)$ | $\text{F}$  | $\exist{x{\neg{P{x}}}}$ |                   |
| $(3)$ | $\text{F}$  |    $\forall{x}P{x}$     | $\text{from} (1)$ |
| $(4)$ | $\text{F}$  |         $P{a}$          | $\text{from} (3)$ |
| $(5)$ | $\text{F}$  |      $\neg{P{a}}$       | $\text{from} (2)$ |
| $(6)$ | $\text{T}$  |       $P{a} \ ↯$        | $\text{from} (5)$ |

No open case was found, hence the proof of validity.

## Q2

1. Merits of ND

   Mistake: ND allows more complex proof structures and is better for more intricate theorems.

   Explanation: For complex proofs, ST is more suitable in general since the automatic reasoning. ND is more intrusive yet more challenging in some cases.

   Mistake: ND has a wider range of inference rules.

   Explanation: ND and ST both have their own rules and are used in different scenarios based on different problems.

2. Demerits of ND

   None.

3. Merits of ST

   Mistake: ST is good for simple proofs and checking the validity.

   Explanation: In general, ND is more intrusive and more suitable for simple proofs and checking validity.

   Mistake: ST can quickly identify contradictions and determine their validity/invalidity.

   Explanation: ST explores all possible truth value assignments hence less efficiency, especially for complex formulae.

4. Demerits of ST

   Mistake: ST is not suited for more complex proofs.

   Explanation: ST is more suited for complex proofs due to its automatic reasoning and completeness.

## Q3

### Introduction of Sorites Paradox

#### What is Sorites paradox?

Let's denote $G(s)$ as the predicate of whether $s$ is a grain of sand, i.e., an insignificant amount of sand. Consider $S \coloneqq \{S_1, S_2, ..., S_k, ... \}$ as a set of $k\in ℤ^+$ amount of grains of sand

Following Modus Ponens, we have:
$$
\begin{align*}

G(S_1) & &\text{(Start with one grain of sand)}\\
G(S_k) &\rightarrow G(S_{k+1}) &\text{(The sand after adding one grain of sand is still a grain of sand)}\\

\end{align*}
$$
Use the implication elimination rule $\rightarrow\operatorname{E}$, we can easily derive that
$$
\begin{align*}

G(S_1), G(S_2), G(S_3), ..., G(S_{10^2}), ..., G(S_{10^{5}}), ..., G(S_{10^{10}}), ... \\

\end{align*}
$$
The derivation tells us that $S_k$ is always considered as some grains of sand regardless of how big $k$ is, which is not true in reality.

#### Another Paradox of Baldness

Denote $NB(h)$ to indicate that a person with $h$ amount of hair is not considered as bald. Assume an average student with a head of full hair, e.g., $h=100,000$. According to Harvard University [1], we derive that $NB(100,000)$ is true.

Suppose whenever students study one hour of logic, we notice that losing one hair doesn't impact the baldness: $NB(h_k) \rightarrow NB(h_{k+1})$. Following the same procedure, we derive another paradox: after studying $100,000$ hours, a person with no hair is still not bald.

#### Reasons Behind Paradoxes

The reasons behind the paradoxes can be covered into two domains:

- Impreciseness and vagueness of our natural language
- The difficulty in defining a precise boundary. For example, to decide baldness, the pattern of hair loss is the main consideration in the Hamilton-Norwood scale [2].

### Methods to Address Sorites Paradox

#### Regimentation

To address the vagueness of our natural language, we choose to clarify and facilitate the logic problems by formulating and applying logical generalisations. Let's denote a given natural language logic statement as $S$ that be used in a specific scenario $O$. To regulate $S$, we adopt a certain kind of linguistic policy, to replace $S$ with a corresponding $S'$ that has been regulated with perspicuous logical grammar and used in the same scenario $O$​.

One disadvantage is that regimentation is not guaranteed to succeed. The regimentation of the word "heap" may be lexically ambiguous, i.e., any given paraphrase of a sentence containing the word may be intrepreted in several ways [4]. For example:

- I want a heap of sand to build a sand castle to win a competition. I shove the sand to the scale but it weighs only 10 grams. The rule says one must use at least 100 kilograms of sand and note it as a heap of sand. I keep shoving the sand until it reaches at least 100 kilograms to satisfy the requirement.
- After the end of the competition, I took a photo from 10 kilometres away of my sand castle, where the background is full of dunes. One friend sayid to me after seeing the photo, "Your castle has a heap of sand." I replied, "No, there is not such a heap of sand."
- After I finished the building of the sand castle, heavy rain poured down and dissolved all the sand castles. One friend asked me, "Does your castle contain a heap of sand?" I replied, "No, there is not a heap of sand."

These uses of "heap" suggest that the ways people paraphrase sentences containing "heap" are not fixed in advance of particular contexts in which one uses that word, hence its contextual ambiguity [4]. Nevertheless, it is always possible to disambiguate the regimented predicates to adapt to new uses of the word that are not presented.

#### Fuzzy Logic

Fuzzy logic is designed to handle vagueness or impreciseness by allowing for degrees of truth, rather than the traditional binary true/false values in classical logic. Specifically,

- Degrees of truth: 
- Fuzzy sets: 
- Fuzzy logic semantics

To address the above paradox, we can set three evaluations for the concept of a heap of sand.

- A grain of sand  / $T$ / $1 \leq k < 100$
- More than a grain yet a heap / $i$ / $100 \leq k < 1000$
- A heap of sand / $F$ / $1000 \leq k$

Then we have:

- For $1 \leq k < 100$: $G(S_k);G(S_k) \rightarrow G(S_{k+1})$ has the truth value $T; T \rightarrow T$ as $T$​.
- When $k=99$: $G(S_{99});G(S_{99}) \rightarrow G(S_{100})$ has the truth value $T; T \rightarrow i$ as $i$, indicates that $S_{100}$ is not a grain of sand yet a heap of sand.
- For $100 \leq k < 1000$: $G(S_k);G(S_k) \rightarrow G(S_{k+1})$ has the truth value $i; i \rightarrow i$ as $i$.
- When $k=999$: $G(S_{999});G(S_{999}) \rightarrow G(S_{1000})$ has the truth value $F; i \rightarrow F$ as $F$, indicates that $S_{1000}$ is a heap of sand.

One disadvantage occurs in the subjectivity of the membership function, which depends on human interpretations and different scenarios. Due to the new imported fuzzy logic rules, it may require a large number of fuzzy rules to capture the relationships between inputs and outputs accurately.

One counterexample derives from the ambiguity of choosing the degrees of truth and the membership function. Consider we have $1000$ degrees $\{D_1, D_2, ..., D_{1000}\}$ denotes as that represents the resemblance to the concept of a heap. Each corresponding semantic truth table has $1000 * 1000$ entries to determine its semantics. At the same time, it's hard to regulate which degree is used as the borderline of the definition of a heap.

### Judgement

Both methods can mitigate the paradox to a certain degree, yet have counterexamples that can not be properly handled. For fuzzy logic, there are no clear, precise boundaries that definitively seprate concepts. For example, it is challenging to quantify the pattern on a bald head. However, combined with the regimentation, one may use fuzzy logic to solve a certain part of paradoxes with well-established predicates [4]. However, the computational complexity of the membership function in fuzzy logic and its limited formalisation may stay problematic for complex problems.

### Reference

1. bionumbers.hs.harvard.edu. (n.d.). *Number of hairs on human head - Human Homo sapiens - BNID 101509*. [online] Available at: https://bionumbers.hms.harvard.edu/bionumber.aspx?id=101509.
2. Wikipedia Contributors (2020). *Hamilton*. [online] Wikipedia. Available at: https://en.wikipedia.org/wiki/Hamilton.
3. Hyde, D. and Raffman, D. (2018). *Sorites Paradox*. Summer 2018 ed. [online] Stanford Encyclopedia of Philosophy. Available at: https://plato.stanford.edu/entries/sorites-paradox/#RespPara.
4. Ebbs, G. (2009). Regimentation. *Oxford University Press eBooks*, [online] pp.14–39. doi:https://doi.org/10.1093/acprof:oso/9780199557936.003.0002.





