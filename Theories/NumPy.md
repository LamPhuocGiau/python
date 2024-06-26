# [NumPy](https://numpy.org/doc/stable/user/absolute_beginners.html)
## Table of contents
- [Introduction](#Introduction)
- [Numpy arrays](#Numpy-arrays)
- [Create an array from csv](#Create-an-array-from-csv)
- [Operations with numpy arrays](#Operations-with-numpy-arrays)
- [Two dimensional arrays](#Two-dimensional-arrays)
- [Selecting elements from a 1D array](#Selecting-elements-from-a-1D-array)
- [Selecting elements from a 2D array](#Selecting-elements-from-a-2D-array)
- [Logical operatios with array](#Logical-operatios-with-array)
- [NumPy and mean](#NumPy-and-mean)
- [Mean and logical operations](#Mean-and-logical-operations)
- [Caculating of 2D array](#Caculating-of-2D-array)
- [Sorting and outliers](#Sorting-and-outliers)
- [Numpy and median](#Numpy-and-median)
- [Percentiles](#ercentiles)
- [Numpy and standard deviation](#Numpy-and-standard-deviation)
- [Introduction](#Introduction)
- [Historgrams](#Historgrams)
- [Types of distributions](#Types-of-distributions)
- [Normal distribution](#Normal-distribution)
- [Standard deviation and normal distribution](#Standard-deviation-and-normal-distribution)
- [Binomial distribution](Binomial-distribution)
- [Binomial distribution and probability](#Binomial-distribution-and-probability)
- [Numpy arrays](#Numpy-arrays)
```
import numpy as np
my_list = [1, 2, 3, 4, 5, 6]
my_array = np.array(my_list)
```
## Create an array from csv
```
csv_array = np.genfromtxt('sample.csv', delimiter=',')
```
## Operations with numpy arrays

Addition, subtraction, multiplication, and division, square, square root.

```
my_list = [1, 2, 3, 4, 5, 6]
my_list_plus_2 = my_list + 2
my_list_square = my_list ** 2
my_list_square_root = np.sqrt(my_list)
## Two dimensional arrays
```
Adding or subtracting arrays.

```
a = np.array([1, 2, 3, 4, 5])
b = np.array([6, 7, 8, 9, 10])
a + b
result: array([ 7,  9, 11, 13, 15])
```

## Selecting elements from a 1D array
```
a = np.array([5, 2, 7, 0, 11])
>>> a[0]
5 
>>> a[-1]
11
>>> a[-2]
0
>>> a[:3]
array([5, 2, 7])
>>> a[-3:]
array([7, 0, 11])
```
## Selecting elements from a 2D array

A 2-d array is a[row,column] where a is the array.

```
a = np.array([[32, 15, 6, 9, 14], 
              [12, 10, 5, 23, 1],
              [2, 16, 13, 40, 37]])

>>> a[2,1]
16
>>> a[:,0]
array([32, 12,  2])
>>> a[1,:]
array([12, 10,  5, 23,  1])
>>> a[0,0:3]
array([32, 15,  6])
```
## Logical operatios with array

```
>>> a = np.array([10, 2, 2, 4, 5, 3, 9, 8, 9, 7])
>>> a > 5
array([True, False, False, False, False, False, True, True, True, True], dtype=bool)
>>> a[a > 5]
array([10, 9, 8, 9, 7])
>>> a[(a > 5) | (a < 2)]
array([10, 9, 8, 9, 7])
```
## NumPy and mean
```
>>> survey_array = np.array(survey_responses)
>>> np.mean(survey_array)
5.220
```
## Mean and logical operations
a logical operator will evaluate each item in an array to see if it matches the specified condition. If the item matches the given condition, the item will evaluate as True and equal 1. If it does not match, it will be False and equal 0. mean value will be equivalent to the total number of True items divided by the total array length.
```
>>> np.mean(survey_array > 8)
0.2
```

## Caculating of 2D array
Find the mean across all the arrays.

```
>>> ring_toss = np.array([[1, 0, 0], 
                          [0, 0, 1], 
                          [1, 0, 1]])
>>> np.mean(ring_toss)
0.44444444444444442
```
Find the means of each interior array, we specify **axis 1 (the “rows”)**:

```
>>> np.mean(ring_toss, axis=1)
array([ 0.33333333,  0.33333333,  0.66666667])
```
Find the means of each index position, **axis 0 (the “columns”)**:

```
>>> np.mean(ring_toss, axis=0)
array([ 0.66666667,  0.        ,  0.66666667])
```
## Sorting and outliers
```
>>> heights = np.array([49.7, 46.9, 62, 47.2, 47, 48.3, 48.7])
>>> np.sort(heights)
array([ 46.9,  47. ,  47.2,  48.3,  48.7,  49.7,  62])
```
## Numpy and median

** should be sort befor calculate**

```
>>> my_array = np.array([50, 38, 291, 59, 14])
>>> np.median(my_array)
50.0
```
## Percentiles

**Should be sort before calculate percentile**

```
>>> d = np.array([1, 2, 3, 4, 4, 4, 6, 6, 7,  8, 8])
>>> np.percentile(d, 40)
4.00
```

## Numpy and standard deviation

```
np.std()
``` 
## Historgrams

```
from matplotlib import pyplot as plt

d = np.array([1, 1, 1, 2, 2, 2, 2, 2, 3, 3, 4, 4, 4, 4, 5])

plt.hist(d, bins=5, range=(1, 6))

plt.show()
```

## Types of distributions
- Unimodal distribution.

- Bimodal distribution.

- Multimodel distribution.

- symmetric shape.

- skew-right shape.

- skew-left shape.

## Normal distribution

Normally, mean and standard deviation will decide the shape of unimodal distribution.

```
a = np.random.normal(0, 1, size=100000)
```
- loc: the mean for the normal distribution.

- scale: the standard deviation of the distribution.

- size: the number of random numbers to generate.

## standard deviation and normal distribution

68% of our samples will fall between +/- 1 standard deviation of the mean.

95% of our samples will fall between +/- 2 standard deviations of the mean.

99.7% of our samples will fall between +/- 3 standard deviations of the mean.

```
lower_bound = mean - std.
upper_bound = mean + std.
```

## Binomial distribution

**np.random.binomial**. The function will return the number of successes for each “experiment”.

It takes the following arguments:

N: The number of samples or trials.

P: The probability of success.

size: The number of experiments.


## Binomial distribution and probability

```
a = np.random.binomial(10, 0.30, size=10000)
np.mean(a == 4)
```