# Colloquium Presentation

- Introduce myself
- MaxSAT-Based Bi-Objective Boolean Optimization
- CoReO Group (Matti, Jeremias, Andreas)
- Research assistant

## Introduction

- Outline
  - Motivating and defining bi-objective optimization
  - Contribution and high-level overview of BiOptSat algorithm
  - Results comparing to 2 competitors
  - What I take away from my thesis project
- Paper with same title currently under review for SAT'22

## Motivation - Optimization

- Imagine you want to choose a flat
  - At least two rooms
  - As cheap as possible
  - Options in table
- ➡️ C out because of rooms
- ➡️ B is the cheapest and therefore the best candidate
- Optimization problems like this often in real-world
- Algorithms for solving this exist
- ➡️ But what if we also want an optimal commute distance?

## Motivation - Multiple Objectives

- Same task, but: as cheap as possible while _also_ as short of a commute as possible
- ➡️ Again, C out because of rooms
- ➡️ If only A, B, C; B is the best (it is **clearly** better than A) 
- ➡️ However, what if D is there as well
  - B is cheapest, D has shortest commute
- For multiple objectives, there is no single definition of optimality, it depends on your preference
- ➡️ For algorithm development: **Pareto optimality**: consider all optimal where no other is **clearly** better

## Motivation - Implicit Solution Set

- Another example: find smallest decision trees that also minimize classification error
- ➡️ First DT with 1 decision node and error 1
- ➡️ Second DT with 2 decision nodes and error 0
- Both Pareto-optimal
- ➡️ Difference: when solutions are defined implicitly, problem is **hard**

## Thesis Contribution

- What I actually did
- ➡️ Development of BiOptSat
  - Algorithm for enumerating **Pareto-optimal** solutions
  - For **hard** problems
- ➡️ Implementation
  - Will be released openly when paper is published
- ➡️ Evaluation of variants and competitors
- ➡️ Evaluation of refinements

## High-Level Overview of BiOptSat

- Given: problem (e.g., all valid DTs over dataset)
- Wanted: Pareto-optimal solutions (e.g., smallest and best DTs)
- ➡️ Obvious approach: problem specific algorithm
  - Disadvantage: needs to be done for every problem
- ➡️ Alternative: declarative approach
  - Detour through generic encoding language
  - Generic solver for this language
  - BiOptSat is such a **generic** algorithm
- ➡️ Some facts
  - Boolean logic as encoding language
  - Lexicographic method (**next slide**)
  - Based on so-called MaxSAT algorithms (hence title)
  - Makes use of so-called SAT solvers (hence name)

## Search Progression of BiOptSat

- How does BiOptSat search for Pareto-optimal solutions?
- Objective space; two axes are two objectives
- Infeasible area of the problem (e.g., choose at least 3 in total)
- ➡️ Feasible solution with objective values `O_I=3` and `O_D=3`
- ➡️ Area of clearly better solutions and Pareto-optimal solutions
- ➡️ Now for the search: BiOptSat minimizes `O_I` first
- ➡️ Once it can't minimize `O_I` further, it starts minimizing `O_D`
- ➡️ First Pareto-optimal solution found
- ➡️ Continue search with better value for `O_D`
- ➡️ Continue search with better value for `O_D`
- ➡️ Do the same: minimize first `O_I`, then `O_D`
- ➡️ Ordered enumeration of Pareto-optimal solutions from top left to bottom right
  - Lexicographic method
- More details too much for this scope

## Results - Solved Instances

- How does BiOptSat (best variant) compare to two competitors
- Horizontal: #instances, vertical: for given (per-instance) timeout (up to 1,5h)
- The further in the bottom right a line is, the better
- Right is magnified version to see details
- 2 benchmark domains
  - Set covering (2 variants)
  - **Pareto-optimal decision rules**
- ➡️ Competitor 2: poor performance, only solves 123 instances
- ➡️ Competitor 1: a lot better, solves 219 instances
- ➡️ BiOptSat: best, solves 223 instances
  - Separation from Competitor 1 for harder instances

## Results - Instance Runtimes

- Previous plot was for one benchmark domain (Decision Rules)
- We use 3
- Here: instance runtime comparison between Competitor 1 (horizontal) and BiOptSat (vertical)
- Diagonal is equal runtime, below BiOptSat is better, above Competitor 1 is better
- Other two lines are factor 2 in each direction
- ➡️ Decision Rules: better performance by about 1.5x for most instances
- ➡️ SetCovering 1: similar results
- ➡️ SetCovering 2: strongest results, BiOptSat does **very** clearly outperform Competitor 1
- ➡️ Summary
  - BiOptSat outperformed both competitors
  - Amount depends on benchmark domain

## Take Away Points

- Content
  - Paper is in review means high novelty and significance
  - Exact bi-obj optimization is great field of research
- Process
  - Starting with a summer internship is great
    - Unfortunately, application deadline was already in January
    - Maybe next year
  - Research assistant allows to dive deep
    - Would highly recommend writing thesis that way

## Appendix

### Pareto Optimality

- Formal Definitions

### BiOptSat

- Pseudo-code

### Search Details of BiOptSat

- Detailed animation with blocking