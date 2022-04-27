# 11.03.2022

- Structure: SAT and Multiobjective Optimization chapters
- Shirt and Tie example: Develop own (unsat/sat)
- Not: solves the SAT problem
- Approaches: Pseudocode
- Other approaches: relate lexi opt and minmax to pareto optimality

# 23.03.2022 - Feedback Jeremias

- 2.4
  - Probably better to start from full totalizers and then go to reduced ones, right?
  - Incremental Tot: explain that the solver doesn't need to be restarted?
- 3.1
  - Decision variable x: idea was to go to the context of SAT only in 3.2; but can change x to something else
    -> Change to saying "solution"
- 3.2
  - What stuff where earlier?
  - "Linear objectives with integer coefs" equivalent to "using literals"?
  - What names of algorithms are discussed later?
    -> Subroutines
- 3.4
  - Can I say "_Related_ Approaches to Bi-Objective Optimization"?
    -> Or existing or previous
  - 3.4.1
    - P-minimal
      - What is less 'papery' and what abstraction to lift?
        -> either more formal (preffered) or less formal
    - Seesaw
      - hs and cores ambiguous?
        -> "for decision problems"
      - Highlight on black-box sentence?
        -> point out that it _can_ be a blackbox
  - 3.4.2
    - Repetitive of what?
- 4.1
  - And return is on something?
    -> pay attention to the different taus (from pseudocode and text)
  - b_D lexi?
    -> b_D undefined
- 4.3
  - 4.3.5
    - Has anyone done core exhaustion for MSU3? Can I mention that it could be done but then not do it?
- 5.1
  - 5.1.1
    - objective mixing
    - weird rule notation
      -> change fs to xs
  - 5.1.2
    - P-minimal is as much defined as in the paper
      -> define P-minimal as a name more clearly

# 25.03.2022

- Better reusing of models: some improvement for reporting all solutions
  - Can we update the data in the paper?
- Colloquium presentation 10.04.
  - Don't spend too much time
  - Mention submission
  - Don't go into detail
  - Motivate properly
  - Show results
  - Mention hardness and exactness

# 01.04.2022 - Feedback Matti

## Chap 1

- P1: can't read some stuff
- P2: NN loss?
- P4: what's that stuff regarding the commute?
- P5: Pareto-optimality
  - So far: pareto optimality and pareto-optimal
  - Capitalization?
  - Hyphens?
  - (In the paper as well, btw)
  - "considers" -> ?
- Other notions of optimality: what?
- P7: good but sightly what?
- P8
  - Intuition on NP-completeness/-hardness?
- P9
  - Specialized algs
    - Are they completely independent from these categories?
    - Specialized example: DP murtree alg
  - Last sentence?
- P10
  - Comment at top of p4?
  - Problem vs. instance: what exactly? (not encoded vs. original)
  - Illustration (am thinking of Jeremias' thesis or my colloquium slides)
- What to say about solving in declarative paradigms?
- P14
  - What is unnecessary about Seesaw ref?
  - Idea was to show that there is a research opportunity (therefore "therefore")
- P16 (and in general)
  - Always using absolute references to chapters/sections feels repetitive, hence was trying to mix absolute and relative
  - Is absolute just more common? Reason for preference?

## Chap 2

- 2.1: can title be the same as chapter title?
- 2.2: title comment? References?
- 2.3: soundness?

## Chap 3

- Signposting: first underline? comment?
- 3.1
  - solution x and feasible set?
  - subject to?
  - Domination?
  - x \prec x'?
- 3.2: ???
- 3.3: last part of comment
- 3.4.1
  - Seesaw: different in style in what way?

# 04.04.2022 - Meeting Matti

- Signposting can be list-like
- Rework reference style
- Conclusions past tense

- Mention what we're focusing on once it comes up
- _The_ declarative approach with different paradigms

- Millions of vars and clauses: only _some_
- Example 2.2: Change from instance to problem (with real-world representation)
- Expand on CDCL
  - Intuitively, what is learned clause
- CP 21 branch-and-bound MaxSAT paper

- Other notions: We have those enumerated, they are presumably easier

# 06.04.2022 - Intro Outline

- Being upfront: What is this thesis about?
- What are optimization problems and where do they occur
- Applications of optimization in literature
- Hardness of optimization problems
- Approaches to solving optimization
- Solving pipeline for declarative approaches
- Advantages of declarative approaches
- Runtimes in declarative approaches
- Reveal conflicting second objective
- Conflicting objectives and why there might be no single optimal solution
- Pareto optimality
- Bi-objective vs multi-objective
- Applications of bi-objective optimization in literature
- MaxSAT (and SAT)
- SAT-based bi-/multi-objective optimization not very active in last years
- Contributions
- Signposting for chapters

# 26.04.2022 - Feedback and Meeting Jeremias

## Intro

- Vagueness in parts intentional (how to do better?)
  - easily encoded: succinctly
  - e.g. "small enough encoding": should I say "polynomial size encoding"? Technically it should be something like "an encoding of size smaller than the worst-case runtime of the problem"
- Earlier version: multi-objective earlier, Matti asked to move declarative/SAT earlier
  - Need to find balance
- Complexity discussion?
  - Unse NP-hard _informally_
  - Discuss real-world runtimes
- Encoding size: "the efficiency of the pipeline depends on the size of the encoding"
- "MaxSAT as the declarative programming language": is something like "SAT-based language similar to MaxSAT" better?
- p4: Pareto point definition move forward?
- Struggle to find balance between not making the intro more lengthy and explaining enough so that it is understandable

> **_SUMMARY:_** Make sure the reader gets the idea (_exact_, _multi-objective_ optimization for _hard_ problems) early

## SAT

- Learned clause "can be deleted"?
- SAT encoding example: change from arbitrary meal to pizza
- Cooking/pizza example for incremental SAT

## Bi-Opt

- MaxSAT notation using O for soft clauses: was intentional because S seems overloaded and O is basically the same in MaxSAT and Bi-Opt
- Other notions: Matti asked to point out that they can be considered "easier"
- SAT cores for Seesaw: how much detail is needed, since it is not a main contribution but still new
- Seesaw cores, rework paragraph

## BiOptSat

- Point out that the first solution is lexicographically optimal
- $\tau^r$ as "running model" was an attempt to make sure what $\tau$ I'm talking about in the text
  - Maybe better to rename superscript-less $\tau$s in text
- MSU3 connection to optimization cores
- Spell out relaxation of cores in OLL
- Mention that we tried double bound hardening and did not get enough advantage to justify more clauses

## Experiments

- Shorten objective swapping discussion in results