# **[Predicting Stock Prices with Deep Neural Networks](https://www.alphavantage.co/academy/#ai-for-finance)
---
Deep Learning Framework: [Long Short-Term Memory (LTSM)](https://en.wikipedia.org/wiki/Long_short-term_memory)
- artificial recurrent neural network (RNN) architecture 
    - overcomes technical limitations of RNNs
    - fail to learn when data sequence is greather than 5-10 due to `vanishing gradients problem`
- feedback connections to process single data points, as well as sequences of data
- good for classifying, processing, and making predictions based on time-series data 
    - can 'memorize' patterns from historical sequences of data 
- commonly composed of a **cell**, **input gate**, **output gate**, and a **forget gate**
    - cell remembers values over arbitrary time intervals and the three gates regulate flow of information in and out of the cell 
- learn long sequences of data by enforcing constant error flow through self-connected hidden layers 
- layers contain memory cells and corresponding gate units 

    
- [Gradient Descent:](https://en.wikipedia.org/wiki/Gradient_descent) Optimization Technique
    - requires data to be scaled for LTSM
    - 'steepest descent'
    - find local minimum of a differentiable function 
    - take repeated steps in te opposite direction of gradient -> finding steepest route down 
    - feature values in the model affect step size (skew LTSM model)
    
    
- Data Normalization: 
    - help gradient descent algorithm converge more quickly 
    - bring input data on the same scale and reduce variance 
        - weights in neural network won't be wasted on normalizing
        - LTSM model can more efficiently learn and store patterns 
    - LTSM sensitive to scale of input data -> faster to noramlize it prior 
    
    
- [Supervised Machine Learning Models:](https://en.wikipedia.org/wiki/Supervised_learning)
    - learning function that maps an input to an output based on IO pairs 
    - learns from specific training data (teacher knows the answers)
    - vecor: input (X variables)
    - supervisory signal: output (Y Variables)
    - generalizes from training data and performs on testing data
    - longer the sequence -> longer the training time 
    
    
    