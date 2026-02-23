---
sticker: emoji//0030-fe0f-20e3
---
### Textbook
- RN20: [Russell, S. J., and Norvig, P. (2020). _Artificial Intelligence: A Modern Approach_. Pearson education limited.](http://aima.cs.berkeley.edu/)
### Other texts
- B12: D. Barber. [_Bayesian Reasoning and Machine Learning_](http://web4.cs.ucl.ac.uk/staff/D.Barber/pmwiki/pmwiki.php?n=Brml.HomePage). Cambridge University Press, 2012 (free PDF).
- P88: Judea Pearl [_Probabilistic Reasoning in Intelligent Systems: Networks of Plausible Inference_](https://dl.acm.org/doi/book/10.5555/534975). Morgan Kaufmann Series in Representation and Reasoning. 1988. (PDF available from Unifi network).
- D17: Hal Daume III [_A Course in Machine Learning_](http://ciml.info/) 2017 (free PDF).
- PM17: David L. Poole and Alan K. Mackworth. [_Artificial Intelligence: Foundations of Computational Agents_](http://artint.info/). Cambridge University Press. (free online).
- HTF09: T. Hastie, R. Tibshirani, and J. Friedman. [_The Elements of Statistical Learning. Data Mining, Inference, and Prediction_](http://web.stanford.edu/~hastie/ElemStatLearn/). 2nd edition. Springer, 2009 (free PDF).
- D03: Dechter, R. (2003). [_Constraint Processing_](https://www.ics.uci.edu/~dechter/books/index.html). Morgan Kaufmann.
- J96: Jensen, F. V. (1996). _An introduction to Bayesian networks_. UCL Press.

## Programma

- Agents and environments. Search problems. States, actions, costs. Search graph. Search tree. General best-first algorithm.
	-  RN20 2, 3.1—3.3.2
	-  _Optional additional readings: [(Felner, 2011)](http://www.aaai.org/ocs/index.php/SOCS/SOCS11/paper/view/4017);_
	
- Blind search algorithms: DFS, BFS, Uniform Cost. Analysis. Iterative deepening. Bidirectional search.
	- RN20 3.4, 3.5.1-3.5.4, 3.6.
	
- Heuristics. Algorithm A* and conditions for optimality. Dominance and empirical evaluation of heuristics. Pattern databases.
	- RN20 3.5.5, 4.1
	- Required additional readings: [(Korf, 1985)](https://www.semanticscholar.org/paper/Depth-First-Iterative-Deepening-%3A-An-Optimal-Tree-Korf-Hsu/32b2bc79604cf367af096994cb5bd233ef7f207b);
	- _Optional additional readings:_[(Korf & Felner 2002)](http://doi.org/10.1016/S0004-3702\(01\)00092-3);_ [(Hansson et al. 1992)](http://www.cse.sc.edu/~mgv/csce580sp15/gradPres/HanssonMayerYung1992.pdf);
	
- Searching and optimizing goal states. Metaheuristics for local search: Hill climbing, local beam search, simulated annealing. Constraint satisfaction problems
	-  RN20 4.1.4, 6.1, 6.2
	- _Optional additional readings: [(Delahaye et al. 2019)](https://link.springer.com/chapter/10.1007/978-3-319-91086-4_1)
	
- Beam search. Examples of CSPs. Inference for CSPs (constraint propagation): Arc consistency, AC-3 and its analysis.
	- RN20 6.3
	-  _Optional additional readings: [(Wallace, 1993)](https://www.ijcai.org/Proceedings/93-1/Papers/034.pdf);_
	
- Backtracking search. Heuristics for variable and value ordering. Inference during backtracking: maintaining arc consistency and forward checking. Cutset conditioning. Dual problems and cluster trees.
	- RN20 6.5, 6.4
	- Required additional readings: [(van Beek, 2006)](https://cs.uwaterloo.ca/~vanbeek/Publications/survey06.pdf); [(Dechter, 2006)](https://ics.uci.edu/~csp/r139.pdf);
	
- Junction trees and triangulated graphs. Cliques in triangulated graphs. Triangulation via variable elimination. Introduction to logic. Knowledge bases. Formulae. Syntax, semantics, interpretations.
	- RN20 6.5, 7.1-7.2
	- Required additional readings: [(Dechter, 2006)](https://ics.uci.edu/~csp/r139.pdf);
	
- Constraint modeling with Minizinc and CPMpy.
	- Required additional readings: [(Marriott et al, 2014)](http://www.minizinc.org/downloads/doc-latest/minizinc-tute.pdf);
	- _Optional additional readings: [(Guns 2019)](https://modref.github.io/papers/ModRef2019_Increasing%20modeling%20language%20convenience%20with%20a%20universal%20n-dimensional%20array.pdf);_
	- Online resources: [Minizinc website](http://www.minizinc.org/); [CPMpy website](https://github.com/CPMpy/cpmpy); [Source code](https://ai.dinfo.unifi.it/teaching/ai25/10.17.25.tgz);
	
- Ontological and epistemological committments of a logic. Semantics. Interpretation functions. Propositional logic and its semantics. Entailment and its decidability.
	- RN20 7.1-7.4
	
- Propositional formulae. Valid and satisfiable formulae. Logical equivalence. Deduction theorem. Decidability of propositional logic. Reduction of entailment to SAT. Introduction to SAT solving. Conjunctive normal form.
	- RN20 7.4, 7.5
	
- SAT and the DPLL algorithm. Randomized algorithms. WalkSAT. Randomized k-SAT and phase transition. Introduction to theorem proving.
	- RN20 7.6.
	- Required additional readings: [(Hoos & Stützle, 2005)](https://www.cs.ubc.ca/~hoos/SLS-Internal/ch6.pdf);
	
- Theorem proving. Inference rules and theorem proving as search. Soundness and completeness. Resolution. Ground resolution theorem.
	- RN20 7.5
	
- Definite clauses. Backward chaining and main ideas behind logic programming. Limitations of logic under uncertainty. Probability distributions on discrete spaces. Introduction to probabilistic inference. Computing conditional probabilities by marginalization. Hugin.
	- RN20 7.5.4, 12, B12 1
	- Online resources: [Hugin expert website](http://www.hugin.com/);
	
- Beliefs. Evidence and probabilistic reasoning. Independence and conditional independence. Using graphs to represent conditional independence. Markov networks and undirected separation.
	- RN20 12.2-12.4;
	
- Examples of Markov networks. Markov chains. Language models. Hidden Markov models. I-maps, D-maps, perfect maps. Hammersley-Clifford theorem. Potential functions, normalized exponentials and clique features. Directed probabilistic graphical models. Factorization of joint distributions according to a directed graph. D-separation and conditional independence in directed networks.
	- B12 4.1-4.2, 3.1-3.3
	- _Optional: B12 23_
	
- Review of D-separation. Conditional probability tables. Expressiveness of Bayesian and Markov networks. Algorithmic problems for graphical models. Moralization. Junction trees for probabilistic inference. Initialization, message passing, inserting evidence.
	-  B12 6; RN20 13.1-3
	- Required additional readings: [(Jensen, 1997, chapter 4) - pw to unzip ai25](https://ai.dinfo.unifi.it/teaching/ai25/jensen.7z);
	- _Optional additional readings: [(Huang & Darwiche, 1996)](https://doi.org/10.1016/S0888-613X\(96\)00069-2);_
	
- Application example: POS-tagging with HMMs. Sketch of the Viterbi algorithm with beam search. Parameter learning in graphical models. Problem setup and assumptions. Maximum likelihood estimation.
	- RN20 20.2.5, 20.2.7, 20.2.2; B12 8.
	- Required additional readings: [(Jurafsky & Martins, 2025)](https://web.stanford.edu/~jurafsky/slp3/); [(Heckerman, 1999)](https://arxiv.org/abs/2002.00269);
	- _Optional additional readings: [(Aji & McEliece, 2000)](https://www.cs.ubc.ca/~murphyk/Teaching/Papers/GDL.pdf);_
- Frequentist (maximum likelihood) and bayesian parameter learning. Beta distribution. Bayesian conjugacy. Laplace smoothing. Dirichlet priors. Sketch of the structure learning algorithm for Bayesian networks.
	- RN20 20.1, 20.2
	- Required additional readings: [(Heckerman, 1999)](https://arxiv.org/abs/2002.00269);
	
- Supervised learning. Examples. Empirical risk minimization. Generalization. Train and test error. Naive Bayes and its discrimination surface. Hyperplanes and the perceptron algorithm.
	- RN20 19.1,19.2
	- Required additional readings: [(McCallum & Nigam 1998)](https://cdn.aaai.org/Workshops/1998/WS-98-05/WS98-05-007.pdf); [(Cristianini & Shawe-Taylor, 2000) - pw to unzip ai25](https://ai.dinfo.unifi.it/teaching/ai25/perceptron.pdf.7z);
	- _Optional additional readings: [(Jordan & Mitchell, 2015)](http://www.cs.cmu.edu/~tom/pubs/Science-ML-2015.pdf);_
	
- The separation surface of Naive Bayes (more details). Linearly and nonlinearly separable data. Block-Novikoff theorem (with proof). Dual form of the perceptron algorithm and its interpretation. Basic ideas behind kernel methods.
	- Required additional readings: [(Cristianini & Shawe-Taylor, 2000) - pw to unzip ai25](https://ai.dinfo.unifi.it/teaching/ai25/perceptron.pdf.7z);
	- _Optional additional readings: [(Sutton & McCallum 2019)](http://arxiv.org/abs/1011.4088);_ [(Freund & Schapire 1999)](http://link.springer.com/article/10.1023/A:1007662407062);
	
- Decision trees for classification. Greedy top-down algorithm. Impurity measures. Hyperparameters. The decision tree hypothesis space. Bias-variance tradeoff. Bagging. Random forests. Bias-variance tradeoff. Bagging. Random forests.
	- RN20 19.8
	- _Optional additional readings: [(Mitchell 1997) - pw to unzip ai25](https://ai.dinfo.unifi.it/teaching/ai25/mitchell.7z);_ [(Breiman 2001)](http://link.springer.com/article/10.1023/A:1010933404324);
	
- Adaboost and its analysis.
	- Required additional readings: [(Freund & Schapire 1999)](http://www.yorku.ca/gisweb/eats4400/boost.pdf);
	- _Optional additional readings: [(Freund & Schapire 1997)](https://doi.org/10.1006/jcss.1997.1504);_ [(Viola & Jones 2001)](http://ieeexplore.ieee.org/xpls/abs_all.jsp?arnumber=990517);