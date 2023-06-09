# Bayesian Optimization LightGBM

### In this case study, we will be using the BayesianOptimization library to perform hyperparmater tuning. I will Predict if a flight departure is going to be delayed by 15 minutes based on the variables and then find the best results.

In addition to the random search and the grid search methods for selecting optimal hyperparameters, we can use Bayesian methods of probabilities to select the optimal hyperparameters for an algorithm.

## 1. How does Bayesian optimization work?

- Bayesian optimization works by constructing a posterior distribution of functions (Gaussian process) that best describes the function you want to optimize. As the number 
of observations grows, the posterior distribution improves. The algorithm becomes more certain of which regions in parameter space are worth exploring and which are
not. As seen in the picture below:

![image](https://user-images.githubusercontent.com/86930309/229310647-c42078e9-dadf-4d9c-987c-f7ec149c814a.png)

- As you iterate over and over, the algorithm balances its needs of exploration and exploitation while taking into account what it knows about the target function.
At each step, a Gaussian Process is fitted to the known samples (points previously explored), and the posterior distribution, combined with an exploration strategy
(such as UCB — aka Upper Confidence Bound), or EI (Expected Improvement). This process is used to determine the next point that should be explored. Just like in the next 
picture:

![image](https://user-images.githubusercontent.com/86930309/229310742-f79adf2a-adf1-4588-a1ca-bd7eaf54ec32.png)

## 2. Simple Bayesian optimization example:

The first step is to create an optimizer. It uses two items:

- Function to optimize
- Bounds of parameters

## 3. Test the Bayesian optimization on real flight departures data using the Light GBM:

The dataset we will be working with is the famous flight departures dataset. There is a [train](https://github.com/GHASS19/Bayesian_Optimization_LightGBM_Case_Study/blob/main/Data/flight_delays_test%20(Bayesian_Optimization).csv) and [Test](https://github.com/GHASS19/Bayesian_Optimization_LightGBM_Case_Study/blob/main/Data/flight_delays_train%20(Bayesian_Optimization).csv) dataset. Our modeling goal will be to predict if a flight departure is going to be delayed by 15 minutes based on the other attributes in our dataset. As part of this modeling exercise, we will use Bayesian hyperparameter optimization to identify the best parameters for our model.

### - Load the two datasets

### - Explore the data

### - Feature Engineering for additional features for our model

### - Define a function for the light GBM

### - Apply the Bayesian optimizer to the function

### - Print the best result:

- 'target': 0.7437957745277676

- 'params': 'lambda_l1': 0.041819147371004145
 
- 'lambda_l2': 0.021821284561502632
  
- 'max_depth': 34.283687656153106
  
- 'min_child_samples': 3428.2342923499978
  
 - 'min_data_in_leaf': 1983.1789349865503
  
 - 'num_leaves': 2265.9330311780527

### The best results were using a iteration of 3 for the light GBM.

