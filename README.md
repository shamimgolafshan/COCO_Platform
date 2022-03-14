# COCO
using COCO to compare CMA-ES to DE
Part One: What Is COCO?
COCO is a platform for Comparing Continuous Optimizers in a black-box setting. It aims at automatizing the tedious and repetitive task of benchmarking numerical optimization algorithms to the greatest possible extent.
We consider the continuous black-box optimization or search problem to minimize
 
Such that for the   constraints
 
we have   for all  . More specifically, we aim to find, as quickly as possible, one or several solutions   in the search space   with small value(s) of   that satisfy all above constraints  . We generally consider time to be the number of calls to the function  .
A continuous optimization algorithm, also known as solver, addresses the above problem. Here, we assume that   is known, but no prior knowledge about   or   is available to the algorithm. That is,   and   are considered as a black-box which the algorithm can query with solutions   to get the respective values   and  .[1]
Part Two: The experiment
I downloaded the experiment code for python from this link: https://github.com/numbbo/coco/tree/master/code-experiments/build/python
I changed the solver to the solver of my choosing, in this case, I was comparing CMA and DE so I used fmin from CMA package of python (which I installed using pip install) and DE from scipy package (scipy.optimize.differential_evolution)

[1]: http://numbbo.github.io/coco-doc/
 
Using cmd, I entered the following command to do the experiment on each algorithm separately:
python example_experiment_new_name.py
This command runs the experiment for the chosen solver and stores the data in a folder. 
To compare two algorithms, we do the post-processing for both of them.
The final result, including the figures and table comparing two algorithms from different aspects, is stored as an HTML file. 
In the first part of the result in ECDF (Empirical Cumulative Distribution Functions), in lower dimensions DE is higher and in high dimensions, there are almost equal.

The functions the bbob tests the algorithm on, are generally categorized in 5 categories (1):
•	Separable functions
o	Sphere (function 1 in bbob suite)
o	Ellipsoid separable (function 2 in bbob suite)
•	Functions with low or moderate conditioning
o	Attractive sector (function 6 in bbob suite)
o	Rosenbrock original (function 8 in bbob suite)
•	Functions with high conditioning and unimodal
o	Sharp ridge (function 13 in bbob suite)
o	Sum of different powers (function 14 in bbob suite)
•	Multi-modal functions with adequate global structure
o	Rastrigin (function 15 in bbob suite)
o	Schaffer F7, condition 10 (function 17 in bbob suite)
•	Multi-modal functions with weak global structure
o	Schwefel x*sin(x) (function 20 in bbob suite)
o	Gallagher 101 peaks (function 21 in bbob suite)
Considering the ECDF for each function, in dimension 2 DE is better than all except “Functions with low or moderate conditioning”
In dimension 3 is better than all except in “Multi-modal functions with adequate global structure” and “Functions with low or moderate conditioning” and “Multi-modal functions with weak global structure”
And in dimension 5 is also the same and from dimension 10 and on DE and CMA are performing almost the same.
Seems that DE works better than CMA except in “Functions with low or moderate conditioning” and “Multi-modal functions with adequate global structure” but in overall result, DE is working better.
In the comparison of average running time, DE is higher.
[1]: http://numbbo.github.io/coco-doc/bbob-biobj/functions/#the-single-objective-bbob-functions
