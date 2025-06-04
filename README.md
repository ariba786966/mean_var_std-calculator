# mean_var_std-calculator
 It's a calculator which calculates mean, variance and standard deviation of 3X3 array using Numpy.
 
import numpy as np
# creating function calculate()
def calculate(lst):
  if len(lst) != 9:
    raise ValueError("List must contain nine numbers.")
    #creation of matrix
  matrix = np.array(lst).reshape(3,3)

  calculation = {
      'mean': [matrix.mean(axis=0).tolist(),
              matrix.mean(axis=1).tolist(),
              matrix.mean().tolist()],
      'variance': [matrix.var(axis=0).tolist(),
                  matrix.var(axis=1).tolist(),
                  matrix.var().tolist()],
      'standard deviation': [matrix.std(axis=0).tolist(),
                            matrix.std(axis=1).tolist(),
                            matrix.std().item()],
      'max': [matrix.max(axis=0).tolist(),
              matrix.max(axis=1).tolist(),
              matrix.max().item()],
      'min': [matrix.min(axis=0).tolist(),
              matrix.min(axis=1).tolist(),
              matrix.min().item()],
      'sum': [matrix.sum(axis=0).tolist(),
              matrix.sum(axis=1).tolist(),
              matrix.sum().item()]
    
  }
  return calculation

lst = [50,13,24,53,14,95,60,76,81]
print(calculate(lst))
