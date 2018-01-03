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
    *J (w, b)

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