# Questionnaire for Lesson 3

**Q: What letters are often used to signify the independent and dependent variables?**

**A:** x for the independent, y for the dependent variables


**Q: What's the difference between the crop, pad, and squish resize approaches? When might you choose one over the others?**

**A:**

*crop:* Crops the centers of the images to fit the requested size

*pad:* Pads the images with black pixels

*squish:* Squishes/stretches the images

Crop is not a viable option when there might be useful information outside the center of the image.
Padding results in images with useless pixels.


**Q: What is data augmentation? Why is it needed?**

**A:** Data augmentation is the creation of random variations of the input data. It reduces the possibility of overfitting the training set.


**Q: What is the difference between item_tfms and batch_tfms?**

**A:** `batch_tfms` is applied to a whole batch of items, instead of a single item as in the case of `item_tfms`. Besides, `batch_tfms` runs on GPU.


**Q: What is a confusion matrix?**

**A:** A matrix that compares the actual and predicted values.


**Q: What does export save?**

**A:** the architecture, along with the trained parameters


**Q: What is it called when we use a model for getting predictions, instead of training?**

**A:** inference


**Q: What are IPython widgets?**

**A:** GUI components that bring together JS and Python funcionalities, and can be used in a Jupyter notebook


**Q: When might you want to use CPU for deployment? When might GPU be better?**

**A:** If you're processing a single input at a time, don't want your users to wait for batch handling, and want cheaper server options, CPU is the better option. GPU is better for batch inputs, video inputs or in the training phase.


**Q: What are the downsides of deploying your app to a server, instead of to a client (or edge) device such as a phone or PC?**

**A:** -


**Q: What are three examples of problems that could occur when rolling out a bear warning system in practice?**

**A:**

- detecting other animals as bears
- low image in nighttime images
- possible low resolution camera images


**Q: What is "out-of-domain data"?**

**A:** data that the model sees in production, but not in training


**Q: What is "domain shift"?**

**A:** changes in the type of data that the model faces


**Q: What are the three steps in the deployment process?**

**A:**

1. Manual process
  - Run model in parallel
  - Humans check all predictions
2. Limited scope development
  - Careful human supervision
  - Time or geography limited
3. Gradual expansion
  - Good reporting systems needed
  - Consider what could go wrong


**Q: How is a grayscale image represented on a computer? How about a color image?**

**A:**

*grayscale:* image intensities
*color:* image intensities for each color channel


**Q: How are the files and folders in the MNIST_SAMPLE dataset structured? Why?**

**A:**

```
valid
└───3
|   |    1.png
|   |    2.png
|   |    ...
└───7
|   |    1.png
|   |    2.png
|   |    ...
train
└───3
|   |    1.png
|   |    2.png
|   |    ...
└───7
|   |    1.png
|   |    2.png
|   |    ...
```

This way, 2 target classes are separated clearly in the folder structure.


**Q: Explain how the "pixel similarity" approach to classifying digits works.**

**A:** The mean pixel intensities of both classes are computed, and the pixels of the images in the training set are compared against those means.


**Q: What is a list comprehension? Create one now that selects odd numbers from a list and doubles them.**

**A:**

```
new_list = [num*2 if num%2==1 else num for num in old_list]
```


**Q: What is a "rank-3 tensor"?**

**A:** a three-dimensional tensor


**Q: What is the difference between tensor rank and shape? How do you get the rank from the shape?**

**A:** Shape has the size of each axis. Rank is the number of axes.

```
rank = len(shape)
```


**Q: What are RMSE and L1 norm?**

**A:**

*RMSE:* root mean squared error, or L2 norm
*L1 norm:* mean absolute difference


**Q: How can you apply a calculation on thousands of numbers at once, many thousands of times faster than a Python loop?**

**A:** using tensors/arrays with linear algebra


**Q: Create a 3×3 tensor or array containing the numbers from 1 to 9. Double it. Select the bottom-right four numbers.**

**A:** -


**Q: What is broadcasting?**

**A:** expansion of a tensor to have the same size as one with a larger rank


**Q: Are metrics generally calculated using the training set, or the validation set? Why?**

**A:** validation set, to avoid overfitting


**Q: What is SGD?**

**A:** stochastic gradient descent


**Q: Why does SGD use mini-batches?**

**A:** to balance the speed and accuracy of the model


**Q: What are the seven steps in SGD for machine learning?**

**A:**

1. Initialize the weights.
2. For each image, use these weights to predict whether it appears to be a 3 or a 7.
3. Based on these predictions, calculate how good the model is (its loss).
4. Calculate the gradient, which measures for each weight, how changing that weight would change the loss
5. Step (that is, change) all the weights based on that calculation.
6. Go back to the step 2, and repeat the process.
7. Iterate until you decide to stop the training process (for instance, because the model is good enough or you don't want to wait any longer).


**Q: How do we initialize the weights in a model?**

**A:** randomly


**Q: What is "loss"?**

**A:** the deviation from the goal that is used to change the parameters of the model


**Q: Why can't we always use a high learning rate?**

**A:** We might diverge from the minimum loss


**Q: What is a "gradient"**

**A:** derivative


## Own questions for future reference

**Q: How do you get information on `path.ls()`?**

**A:**

```
path.ls?
path.ls??
doc(path.ls)
```
