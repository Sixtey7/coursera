Binary Classification
---
* don't typically want to iterate over the dataset using a for loop
* forward pass followed by a backward pass
* logicstic regression - algorithm for binary classification
    * input - image
    * output - label (cat or non-cat)
* define a feature vector with the given inputs    
    * in this case, the red, green, and blue values for the image
        * create a vector of 64x64x3 = 12288
        * n(x) = 12288
    * goal in this case is to take in a feature vector (x) and output a label (y)
* m is used to denote the number of training samples
* m(train) for training samples, m(test) for test samples
* X (capital X) is used to denote a matrix of all training samples (has m columns, one column per training sample)
    * (n(x), m) sized matrix
* Y (captical Y) same as X but for the output
    * (1, m) sized matrix

Logistic Regression
---
* used for binary classification problems
    * output is 0 or 1
* y(hat) = Probability that y is equal to 1 (between 0 and 1)
* parameters
    * W an nx dimensional vector
    * b a real number

Logistic Regression Cost Function
---
* superscript (i) means that training sample
* loss (error) function --> how well your algorithm is doing
    * y(hat) vs y (true y)
    * covers how well you are doing on a single training example
* cost function - summation of loss functions over all samples (divided by m)
    * J (w, b)

Gradient Descent
---
* algorithm that can be used to train or to learn the parameters w and b on a training set
    * want to find w,b that minmize J(w, b)
* initiate W and b to an initial value
    * usually initialize to 0
        * Random also works, but not typically done
* takes a step in the steepest downhill fashion
    * should eventually converge to the global optimium or close to global optimum
* learning rate - how big of a step to take 

Derivatives
---
* "you may be thinking you haven't seen derivatives since college" - YUP!
* slope of a line representing a function

More Derivative Examples
---
* d/da a^2 = 2a
    * a = 2 f(a) = 4
    * a = 2.001 f(a) = 4.004
    * d/da a^2 = 4
* d/da a^3 = 3a^2

Computation graph
---
* forward propogation step (forward pass) followed by backward propogation step (backward pass)
* organizes a computation as a sequence of steps

Derivatives with a computation graph
---
* chain rule - if a --> v --> J, the amount dJ/da is the product of derivative dv/da and dJ/dv
* in the code we will write dFinalOutputVar/dVar as just "dvar"
    * represents the derivative of a final output variable with respect to various intermediate quanities
    * dJ/dv will be "dv" and so on
* derivative calculation with a computation graph is done through a backward pass across the computation graph, starting with the final product (J) and determining how each variable affects that final value (dJ/d_)
* forward pass is used to compute the function we want to optimize, and then backward pass to compute the derivatives

Logistic Regression Gradient Descent
---

Gradient Descent on m Examples
---
* vectorization is a technique that has removed the need for 2 massive for loops

Vectorization
---
* art if getting rid of explicit for loops in your code
    * better for large data sets
* z = w transpose x + b
    * w is a vector
    * x is a vector
* in a non vectorized implementation, you would need to for loop through both x and w
    * vectorized allows you to do the transpose directly
        * numpy (python library) can do this directly
            * c = np.dot(a, b)
                * a and b are vectors
                * np is numpy library
* parallel functions on a GPU/CPU are SIMD functions - single instruction multiple data
    * GPUs are better than CPUs at SIMD functions

More Vectorization Examples
---
* whenever possible, avoid explicit for-loops
* numpy is the greatest!

vectorizing logistic regression
---
* reminder:
    * X is a (nx, m) matrix holding all of the training samples
    * Z is a (1, m) matrix holding the z values for each sample
        * Z = np.dot(w transpose, X) + b   
    * A is a (1, m) matrix holding the a values for each sample
        * programming assignment will capture how to calculate this

Vectorizing Logistic Regression's Gradient Output
---
* dZ = A - Y = [a1-y1, a2-y2 ...]

broadcasting in python
---
* example of a broadcast in python
    * divide a 3x4 matrix by a 1x4 matrix
        * python auto expands the target (1x4) matrix to fit the 3x4 (i.e. repeat the 1x4 three times)
            * works for a row vector or a column vector
    * (m, n) +-*/ (1, n) copies it m times to make a (m, n) matrix and then perform the operation
        * same thing for (m, 1)

a note on python/numpy vectors
---
* a = np.random.randn(5) returns neither a row vector or column vector
    * return a "rank 1" array which is (5,)
        * (5, ) is returned by a.shape
        * rather do a = np.random.randn(5, 1)