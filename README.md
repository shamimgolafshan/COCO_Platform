# Comparing CMA-ES to DE using COCO
This project utilizes the COCO (Comparing Continuous Optimizers) platform to benchmark and compare the performance of CMA-ES (Covariance Matrix Adaptation Evolution Strategy) and Differential Evolution (DE) algorithms in a black-box optimization setting.
## Table of Contents
- [What Is COCO?](#what-is-coco)
- [The Experiment](#the-experiment)
- [Running the Experiment](#running-the-experiment)
- [Results](#results)
- [Functions](#functions)
- [Conclusion](#conclusion)

## What Is COCO?
COCO is a platform designed to automate the benchmarking of numerical optimization algorithms. It specifically addresses the continuous black-box optimization problem, evaluating algorithms based on the number of function evaluations required to find solutions that satisfy predefined constraints.

## The Experiment
1. **Download Experiment Code**: Download the Python experiment code from [COCO's GitHub repository](https://github.com/numbbo/coco/tree/master/code-experiments/build/python).
2. **Modify Solver**: Replace the default solver with CMA-ES and DE. Ensure both are installed via pip:
    ```bash
    pip install cma scipy
    ```
3. **Run Experiment**: Execute the following command to run the experiment for each algorithm:
    ```bash
    python example_experiment_new_name.py
    ```
   This will store the experiment data in a specified folder.

4. **Post-Processing**: After the experiments, perform post-processing to generate comparative figures and tables. The final results are stored in an HTML file.

## Running the Experiment
To run the experiment on your local setup:
1. Ensure Jupyter Notebook is installed, or install it using pip:
    ```bash
    pip install jupyter
    ```
2. Navigate to the directory containing the experiment notebook.
3. Launch the notebook:
    ```bash
    jupyter notebook example_experiment_new_name.ipynb
    ```
4. Execute the cells within the notebook to run the experiment.

## Results
Results are detailed in an HTML file, highlighting:
- **Empirical Cumulative Distribution Functions (ECDF)**: Comparing performance across different dimensions.
- **Detailed Results**:
  - **Lower Dimensions**: DE outperforms CMA-ES.
  - **Higher Dimensions**: Both algorithms perform comparably.

## Functions
The bbob suite tests the algorithms across a variety of functions, categorized into:
1. **Separable Functions**
   - Sphere
   - Ellipsoid separable
2. **Low/Moderate Conditioning**
   - Attractive sector
   - Rosenbrock original
3. **High Conditioning and Unimodal**
   - Sharp ridge
   - Sum of different powers
4. **Multi-Modal with Adequate Global Structure**
   - Rastrigin
   - Schaffer F7
5. **Multi-Modal with Weak Global Structure**
   - Schwefel x*sin(x)
   - Gallagher 101 peaks

### Detailed Function Analysis
- **Dimension 2**: DE outperforms except in low/moderate conditioning functions.
- **Dimension 3**: DE generally performs better, with exceptions noted.
- **Dimension 5 and beyond**: Performance of DE and CMA-ES aligns more closely.

### Average Running Time
- DE exhibits a higher average running time compared to CMA-ES.

## Conclusion
DE generally demonstrates superior performance over CMA-ES in various test scenarios, albeit with a longer average running time. For a detailed analysis and visual comparisons, refer to the HTML file produced during post-processing.

For more detailed information on the functions used in the experiments, visit the [COCO documentation](http://numbbo.github.io/coco-doc/bbob-biobj/functions/#the-single-objective-bbob-functions).
