# Questionnaire for Lesson 4

**Q: Why can't we use accuracy as a loss function?**

**A:** Changes in the model parameters are not always reflected on the accuracy.


**Q: Draw the sigmoid function. What is special about its shape?**

**A:** It limits the input values to an output between 0 and 1.


**Q: What is the difference between a loss function and a metric?**

**A:** Metric is for humans, whereas loss is for the model parameters updates.


**Q: What is the function to calculate new weights using a learning rate?**

**A:** step function


**Q: What does the DataLoader class do?**

**A:** loads data


**Q: Write pseudocode showing the basic steps taken in each epoch for SGD.**

**A:**
```
pred = f(x, params)
loss = loss_func(pred, y)
loss.backward()
params.data -= lr * params.grad.data
params.grad = None
```


**Q: Create a function that, if passed two arguments [1,2,3,4] and 'abcd', returns [(1, 'a'), (2, 'b'), (3, 'c'), (4, 'd')]. What is special about that output data structure?**

**A:**
```
def function(a, b): return list(zip(a, b))
```


**Q: What does view do in PyTorch?**

**A:** changes the shape of a tensor


**Q: What are the "bias" parameters in a neural network? Why do we need them?**

**A:** Offset of the multiplication between the input and the weight matrices. They ensure the model does not stop due to 0 weight matrices.


**Q: What does the @ operator do in Python?**

**A:** matrix multiplication


**Q: What does the backward method do?**

**A:** computes the gradients of the loss with respect to all model parameters


**Q: Why do we have to zero the gradients?**

**A:** to avoid terminating the training


**Q: What information do we have to pass to Learner?**

**A:** data loader, model, optimization function, loss function, and metrics


**Q: Show Python or pseudocode for the basic steps of a training loop.**

**A:** -


**Q: What is "ReLU"? Draw a plot of it for values from -2 to +2.**

**A:** Rectified linear unit; it replaces negative values with 0.


**Q: What is an "activation function"?**

**A:** a nonlinear layer


**Q: What's the difference between F.relu and nn.ReLU?**

**A:** F.relu is an API call to the relu function, whereas nn.Relu() creates an nn.Module that can be added to an nn.Sequential model.


**Q: The universal approximation theorem shows that any function can be approximated as closely as needed using just one nonlinearity. So why do we normally use more?**

**A:** Deepening the model with more nonlinear and linear layers result in a reduced amount of parameters, hence increasing the performance of the model.


**Q: Why do we first resize to a large size on the CPU, and then to a smaller size on the GPU?**

**A:** It results in better focused input images. First resize also ensures a square shape.


**Q: If you are not familiar with regular expressions, find a regular expression tutorial, and some problem sets, and complete them. Have a look on the book's website for suggestions.**

**A:** -


**Q: What are the two ways in which data is most commonly provided, for most deep learning datasets?**

**A:**

1. individual files
2. a table of data


**Q: Look up the documentation for L and try using a few of the new methods is that it adds.**

**A:** -


**Q: Look up the documentation for the Python pathlib module and try using a few methods of the Path class.**

**A:** -


**Q: Give two examples of ways that image transformations can degrade the quality of the data.**

**A:** Cropping can result in loss of information; downsampling can result in blurred images.


**Q: What method does fastai provide to view the data in a DataLoaders?**

**A:** `show_batch()`


**Q: What method does fastai provide to help you debug a DataBlock?**

**A:** `summary()`


**Q: Should you hold off on training a model until you have thoroughly cleaned your data?**

**A:** No, the insight gained after training might help during cleaning the data.


**Q: What are the two pieces that are combined into cross-entropy loss in PyTorch?**

**A:** softmax and log likelihood


**Q: What are the two properties of activations that softmax ensures? Why is this important?**

**A:**

1. positive numbers
2. numbers add up to 1

Since we want these numbers to respresent possibilities, we want them to have positive values that add up to 1.


**Q: When might you want your activations to not have these two properties?**

**A:**

These properties result in the model selecting the highest value as the correct category. When we might face input that does not belong to any of the categories, using softmax on its own is not apt.


**Q: Calculate the exp and softmax columns of <<bear_softmax>> yourself (i.e., in a spreadsheet, with a calculator, or in a notebook)**

**A:** -
