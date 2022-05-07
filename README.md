# Image-Emotion-Recognition-using-CNN


In this repo we have used FER-2013 dataset which has 48x48 pixels grey-scale images of face with 7 different emotions lable. The 7-different emotions are- 0=Angry, 1=Disgust, 2=Fear, 3=Happy, 4=Sad, 5=Surprise, 6=Neutral. 

We have used Keras to create a Sequential Convolutional Network. Which means that our neural network will be a linear stack of layers. 

Addition to this, I have used Adam(Adaptive Moment estimation algorithm) optimizer which is a stochastic gradient-descent that is based on first and second-order statistical moments (i.e.,mean and variance).  Since Adam converges faster than the regular gradient descent, I choose to use this with categorical cross entropy.

Categorical Cross Entropy is a loss function. I used categorical cross entropy because this is a multi-class classification problem. metric is based on accuracy.

I used epochs = 30, learning rate = 0.0001 , steps_per_epoch = 28709 // 64 = 448 for this model. 

**What is model.add(Conv2D(32, kernel_size=(3, 3), padding='same', activation='relu', input_shape=(48, 48,1))) ?    **
    A Conv2D layer with 32 filters ,  kernel size of 3x3 , padding = same (so that the size of the image does not change in output), Rectified linear Unit(relu) as an activation function and  shape of image is 48x48x1 (height x width x channel). Lastly, adding this layer to the sequential model.

**What is layers.MaxPooling2D(pool_size=(2, 2), strides=(2, 2)) ?**
  MaxPooling2D layer which picks the max value out of a matrix of size (2*2) with a stride of 2 pixels.

**What is (layers.Flatten() ?**
  Flatten is used to flatten all its input into a single dimension.

**What is layers.Dense(512, activation='relu') ?**
  Dense layer consists of 512 neurons and a ‘relu’ activation function.


**PROBLEM WITH THE 1ST MODEL **:
      The model was performing well in the training dataset (accuracy = 97.89%) but on the testing dataset the accuracy is extremely low(accuracy = 56.98%). In this model the testing error significantly higher than the training error is probably an indication that this model is overfitted. Shown in the graph below.
