# A Maximum Satisfiability Based Approach to Bi-Objective Boolean Optimization

My Master's thesis at the University of Helsinki in the Constraint Reasoning and Optimization research group under supervision of Matti Järvisalo, Jeremias Berg and Andreas Niskanen.

This thesis presents and approach to MaxSAT-based bi-objective optimization also presented in [Jabs et al. 2022] at SAT'22.

The published thesis is available [here](http://urn.fi/URN:NBN:fi:hulib-202206132323).

## Citation

Cite this work as:
```
@MastersThesis{Jabs2022MaximumSatisfiabilityBased,
  author   = {Christoph Jabs},
  school   = {University of Helsinki},
  title    = {A Maximum Satisfiability Based Approach to Bi-Objective Boolean Optimization},
  year     = {2022},
  type     = {M. Sc. thesis},
  url      = {http://urn.fi/URN:NBN:fi:hulib-202206132323},
}
```

## Abstract

Many real-world problem settings give rise to NP-hard combinatorial optimization problems.
This results in a need for non-trivial algorithmic approaches for finding optimal solutions to such problems.
Many such approaches—ranging from probabilistic and meta-heuristic algorithms to declarative programming—have been presented for optimization problems with a single objective.
Less work has been done on approaches for optimization problems with multiple objectives.

We present BiOptSat, an exact declarative approach for finding so-called Pareto-optimal solutions to bi-objective optimization problems.
A bi-objective optimization problem arises for example when learning interpretable classifiers and the size, as well as the classification error of the classifier should be taken into account as objectives.
Using propositional logic as a declarative programming language, we seek to extend the progress and success in maximum satisfiability (MaxSAT) solving to two objectives.
BiOptSat can be viewed as an instantiation of the lexicographic method and makes use of a single SAT solver that is preserved throughout the entire search procedure.
It allows for solving three tasks for bi-objective optimization: finding a single Pareto-optimal solution, finding one representative solution for each Pareto point, and enumerating all Pareto-optimal solutions.

We provide an open-source implementation of five variants of BiOptSat, building on different algorithms proposed for MaxSAT.
Additionally, we empirically evaluate these five variants, comparing their runtime performance to that of three key competing algorithmic approaches.
The empirical comparison in the contexts of learning interpretable decision rules and bi-objective set covering shows practical benefits of our approach.
Furthermore, for the best-performing variant of BiOptSat, we study the effects of proposed refinements to determine their effectiveness.},

## License

<a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/"><img alt="Creative Commons Licence" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-nd/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/">Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License</a>.

## References

- Christoph Jabs and Jeremias Berg and Andreas Niskanen and Matti Järvisalo (2022): _MaxSAT-Based Bi-Objective Boolean Optimization_, Schloss Dagstuhl - Leibniz-Zentrum für Informatik.