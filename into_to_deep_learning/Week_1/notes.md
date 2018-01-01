Intro
---
* of course there's a cat deep learning project

What is A Neural Network
---
* single function in the neural network is a "neuron"
    * size of house --> neuron --> price

* RELU function
    * Goes to zero sometimes and then goes in straight line
    * Rectified Linear Unit
        * Rectified - taking a max of zero

* Larger neural network is a stacking of neurons

* example - other aspects of house price (each subbullet could be a RELU)
    * RELU definition
        * Size and Num bedrooms
        *   family size
        * zip code
            * walkability
        * zip code and wealth
            * school quality
    * Only inputs would be
        * size
        * num bedrooms
        * zip code
        * wealth
    * output is price
    * neural network will figure out how to determine the output given the inputs
        * neural networks will decide what the nodes should be.  All inputs will be provided to the node, and it will determine what to use
* given enough training data, neural networks are very good at determining how to get from x to y


Supervised Learning
-------------------
* This is the primary economic value creation mechanism for machine learning
* used to determine whether or not a user will click on an ad
    * given the ad and user info
* slightly different types of neural networks are better for different cases
    * standard - real estate
    * convolution on neural networks (CNN) - image applications
    * 1D time series is the best way to represent audio
        * RNN - recurrent neural network 
            * best way to process sequenced data
    * language translation using RNN as well
    * autonomous driving typically uses a more hybrid architecutre

* structured data - think databases of data
    * each of the values has a very well defined meaning
* unstructured data - audio, image, text
    * historically its been harder for computers to understand unstructured data
    * thanks to the rise of neural networks, computers have gotten much better at dealing with unstructured data

    Why is Deep Learning Taking Off?
    ---
    * Plateauing of performance v amount of data
        * The amount of data available to solve problems has started to increase greatly
            * factor of the amount of digitaization within society
        * Training neural nets allows for a great increases in the performance with a large amount of data
            * scale has been driving deep learning progress
    * important that it's the amount of _labeled_ data
    * size of training sets is a very important concept
        * in the realm of small training sets, there isn't a lot of difference between small, medium, large NN
    * switching from a sigmoid function based algorithms to RELU functions has granted large performance increases
        * the RELU function is the "activiting" function
        * "gradiant decent algorithm"
    * process to train a NN is very circular
        * idea --> code --> experiment --> idea on how to improve

    About this Course
    ---
    * gonna learn a lot of cool shit!