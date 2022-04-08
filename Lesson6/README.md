# Questionnaire for Lesson 6

**Q: Why can't we use torch.where to create a loss function for datasets where our label can have more than two categories?**

**A:** `torch.where()` can decide between two values, given the truth of one condition.


**Q: What is the value of log(-2)? Why?**

**A:** undefined, `-2` cannot be obtained by any power of `10`

Note: If we take into account imaginary numbers, `log(-2) = log(2) + i*pi`


**Q: What are two good rules of thumb for picking a learning rate from the learning rate finder?**

**A:** the steepest point, and one tenth of the minimum point


**Q: What two steps does the fine_tune method do?**

**A:** freeze all layers but the last, then fit a cycle


**Q: In Jupyter Notebook, how do you get the source code for a method or function?**

**A:** `module.function??`


**Q: What are discriminative learning rates?**

**A:** varying learning rates for different layers


**Q: How is a Python slice object interpreted when passed as a learning rate to fastai?**

**A:** First number is the learning rate for the first layer, second number for the last layer. Learning rates of other layers are separated equally.


**Q: Why is early stopping a poor choice when using 1cycle training?**

**A:** Early stopping might stop the training before the learning rate has reached the small loss values.


**Q: What is the difference between resnet50 and resnet101?**

**A:** number of layers


**Q: What does to_fp16 do?**

**A:** converts numbers to 16 bit floating point values


**Q: How could multi-label classification improve the usability of the bear classifier?**

**A:** It can now work on images with no bears or multiple types of bears.


**Q: How do we encode the dependent variable in a multi-label classification problem?**

**A:** one-hot encoding


**Q: How do you access the rows and columns of a DataFrame as if it was a matrix?**

**A:** with its `iloc` property


**Q: How do you get a column by name from a DataFrame?**

**A:** `df['column_name']`


**Q: What is the difference between a Dataset and DataLoader?**

**A:**

*Dataset:* collection with tuples independent and dependent variables
*DataLoader:* iterator of mini-batches over the Dataset


**Q: What does a Datasets object normally contain?**

**A:** training and validation Datasets


**Q: What does a DataLoaders object normally contain?**

**A:** training and validation DataLoaders


**Q: What does lambda do in Python?**

**A:** imitates a function with no name and serialization


**Q: What are the methods to customize how the independent and dependent variables are created with the data block API?**

**A:** `get_x` and `get_y`


**Q: Why is softmax not an appropriate output activation function when using a one hot encoded target?**

**A:** Softmax tries to ensure that one of the classes stand out among the crowd. However, in one hot encoded targets, there may be several or no classes.


**Q: Why is nll_loss not an appropriate loss function when using a one-hot-encoded target?**

**A:** It returns one activation for one label.


**Q: What is the difference between nn.BCELoss and nn.BCEWithLogitsLoss?**

**A:** `nn.BCEWithLogitsLoss` includes the initial sigmoid.


**Q: Why can't we use regular accuracy in a multi-label problem?**

**A:** There may be multiple classes in the target.


**Q: When is it okay to tune a hyperparameter on the validation set?**

**A:** when the plot of the loss against the hyperparameter is a smooth one


**Q: How is y_range implemented in fastai? (See if you can implement it yourself and test it without peeking!)**

**A:** using `sigmoid_range`


**Q: What is a regression problem? What loss function should you use for such a problem?**

**A:** Regression problem is one that tries to approximate a numeric value. `nn.MSELoss` is a nice choice as a loss function for regression problems.


**Q: What do you need to do to make sure the fastai library applies the same data augmentation to your inputs images and your target point coordinates?**

**A:**
```
blck = DataBlock(
    blocks=(ImageBlock, PointBlock),
    ...,
    ...
)
```


**Q: What problem does collaborative filtering solve?**

**A:** recommendations in the case of large numbers of users and products


**Q: How does it solve it?**

**A:** by grouping people with similar histories together, and making suggestions based on a user's 'neighbors'


**Q: Why might a collaborative filtering predictive model fail to be a very useful recommendation system?**

**A:** -


**Q: What does a crosstab representation of collaborative filtering data look like?**

**A:** users as row indices, products/items as column indices


**Q: Write the code to create a crosstab representation of the MovieLens data (you might need to do some web searching!).**

**A:** -


**Q: What is a latent factor? Why is it "latent"?**

**A:** It is a factor/relationship that is not clearly defined by humans.


**Q: What is a dot product? Calculate a dot product manually using pure Python with lists.**

**A:**

```
a = [1, 2, 3]
b = [1, 2, 3]
dot = 'nope'
if len(a)==len(b):
    dot = 0
    for i in range(len(a)):
        dot += a[i] * b[i]
print(dot)
```


**Q: What does pandas.DataFrame.merge do?**

**A:** combines two dataframes by joining the shared column


**Q: What is an embedding matrix?**

**A:** the matrix that is multiplied by the one-hot-encoded matrix


**Q: What is the relationship between an embedding and a matrix of one-hot-encoded vectors?**

**A:** embedding is the multiplication by that matrix


**Q: Why do we need Embedding if we could use one-hot-encoded vectors for the same thing?**

**A:** It is more computationally efficient.


**Q: What does an embedding contain before we start training (assuming we're not using a pretained model)?**

**A:** random values


**Q: Create a class (without peeking, if possible!) and use it.**

**A:**
```
class Person():
    def __init__(self, name):
        self.name =name

    def print_name(self):
        print(self.name)

p = Person('furkan')
p.print_name()
```


**Q: What does x[:,0] return?**

**A:** first column of a 2-d matrix


**Q: Rewrite the DotProduct class (without peeking, if possible!) and train a model with it.**

**A:** -


**Q: What is a good loss function to use for MovieLens? Why?**

**A:** MSELoss: it represents the accuracy of a prediction.


**Q: What would happen if we used cross-entropy loss with MovieLens? How would we need to change the model?**

**A:** -


**Q: What is the use of bias in a dot product model**

**A:** It has the power to represent the individual tendencies of inputs.
