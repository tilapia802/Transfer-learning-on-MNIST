# Transfer learning on MNIST
Training on MNIST digits 5-9 with DNN using transfer learning with previous checkpoint.
## Training process
### Freeze hidden layer 1-5, only train softmax layer
1. Load model from previous checkpoint.
2. Get tensor from previous checkpoint. (Be sure that you have correct naming in your previous checkpoint.)
3. Get softmax layer trainable variables with tf.get_collection().
4. Feed input (MNIST digits 5-9) to model and start training!
### Cache the fifth layer output, so it will train faster
1. Get tensor from fifth layer. (run once and get result from fifth layer)
2. Use the result from fifth layer as input to train softmax layer.
3. Use time.time() to measure training time, it will be faster with caching.
### Remove hidden layer 5
1. Get tensor from fourth layer.
2. Add a new softmax layer.
### Also freeze third and fourth layer, but train first, second and softmax layer
1. Use tf.get_collection() to get trainable variables of first, second and softmax layer.

