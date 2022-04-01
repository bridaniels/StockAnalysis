# **TensorFlow Keras**
---

# Tensor: 
- multi-dimensional arrays with a uniform type 
- immutable like Python numbers and strings
    - cannot update contents of a tensor
- alterations to tensor = new tensor 


# models:
---
### `Sequential()`:
- appropriate for a plain stack of layers
- each layer has eactly one input tensor and one output tensor 
- Keras needs to know the shape of all inputs in order to create weights 
- `.add()` allows you to create Sequential model incrementally 
- `.pop()` removes layers 
- `model = Sequential([Dense(), Dense(),...])` allows you to pass lists of layers to Sequential model 



# Layers
---
### `LSTM: LSTM(units, activation='relu', return_sequences=True, input_shape=(steps,features))`
- `units`: 
    - BIAS
    - dimensionality of output space 
- `activation='relu'`: 
    - `'relu'`: Rectified Linear Unit activation function 
    - standard ReLU activation: `max(x,0)`
        - element-wise maximum of 0 and the input tensor 
        - `x` = input tensor or variable 
    - also `sigmoid`, `softmax`, `softplus`, `softsign`, `tanh`, `selu`, `elu`, `exponential`, and custom opportunities 
- `return_sequences=True`: 
    - Boolean value defaulting to `False`
    - wether or not to return the last ouput in the output sequence or the full sequence 
- `input_shape=(steps,features)`: 
    - so model knows input shape from the start
    - only needs to be in the first layer 
    - can also be called separately 

### `Dense: Dense(units)`
- Regular densely-conencted Neural Network (NN) layer 
- implements operation: `output=activation(dot(input, kernel) + bias)` 
    - `activation()`: element-wise activation function passed as `activation` argument
    - `kernel`: weights matrix created by the layer 
    - `bias`: bias vector created by the layer
        - only applicable if `use_bias=True`
- if input to the layer has (rank > 2) -> `Dense()` computes the dot product between the inputs and kernel along the last axis of the inputs and axis 0 of the kernel 
    - uses `tf.tensordot`
    - kernel with dimensions  `(batch_size, d0, d1)`: 
        - create a kernel with shape `(d1, units)` on every sub-tensor of shape `(1,1,d1)`
            - operates along axis 2 of the input 
        - output with shape `(batch_size, d0, units)`
- `units`: 
    - dimensionality of the output space 





# `.fit()`:
#### `epochs=100`:
- epoch is an arbitrary cutoff generally defined as "one pass over the entire dataset"
- separate training into distinct phases 
- useful for logging and periodic evaluation 
- using `validation_data` or `validation_split` with the `fit` method 
    - evaluations run at the end of every `epoch` 
- ability to add callbacks deigned to be run at end of an epoch
    - ex. learning rate changes and model checkpointing(saving)
    
#### `verbose=0`
- only show epochs
- never show batch bars 
- `verbose=1` will show animated progress bar like `[=====...===]`
- `verbose=2` will show number of epoch like `Epoch 1/10`

#### `use_multiprocessing=True`
- Multiprocessing: breaking application into smaller routines to run independently 
    - threads allocated to processors to improve performance








# Keras Documentation References
---
- [models: Sequential()](https://keras.io/guides/sequential_model/)
- [.fit()](https://keras.rstudio.com/reference/fit.html)
- [.fit(.... epoch=_,....)](https://keras.io/getting_started/faq/#what-do-sample-batch-and-epoch-mean)
- [The Model Class](https://keras.io/api/models/model/)
- [layers: LSTM](https://keras.io/api/layers/recurrent_layers/lstm/)
- [layers: activation functions: relu](https://keras.io/api/layers/activations/)
- [layers: Dense](https://keras.io/api/layers/core_layers/dense/)


# Other References 
---
- [GeeksforGeeks: Multiprocessing](https://www.geeksforgeeks.org/multiprocessing-python-set-1/)
- [TensorFlow Documentation: Tensor](https://www.tensorflow.org/guide/tensor)