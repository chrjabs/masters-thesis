# Colloquium Presentation

- Introduce myself
- MaxSAT-Based Bi-Objective Boolean Optimization
- CoReO Group (Matti, Jeremias, Andreas)

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
- ➡️ If only A, B, C; B is the best (it is _clearly_ better than A) 
- ➡️ However, what if D is there as well
  - B is cheapest, D has shortest commute
- For multiple objectives, there is no single definition of optimality, it depends on your preference
- ➡️ For algorithm development: **Pareto optimality**: consider all optimal where no other is _clearly_ better

## Motivation - Implicit Solution Set

- Another example: find smallest decision trees that also minimize classification error
- ➡️ First DT with 1 decision node and error 1
- ➡️ Second DT with 2 decision nodes and error 0
- Both Pareto-optimal
- ➡️ Difference: when solutions are defined implicitly, problem is _hard_