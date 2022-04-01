# Questionnaire for Lesson 2

**Q: Can we always use a random sample for a validation set? Why or why not?**

**A:** We can, but in some cases, we shouldn't. One example of this is time series data, where we might be better off making sure the time period of the training set comes before that of the validation set. This way, the model does not see into the future as it is trained.


**Q: What is overfitting? Provide an example.**

**A:** It is when the model performs well only on the training set data.

Example: A model that is trained on recognizing cats with its training set containing images of only black cats, it will have a hard time recognizing cats of other colors.


**Q: What is a metric? How does it differ from "loss"?**

**A:** A metric is a measure of the model's quality, and it is defined for human consumption. On the other hand, loss is the measure of performance used in training the parameters of the model.


**Q: How can pretrained models help?**

**A:** They allow us to have quicker training with less data and time.


**Q: What is the "head" of a model?**

**A:** The last part of the model that is newly added to be specific to the new dataset.


**Q: What kinds of features do the early layers of a CNN find? How about the later layers?**

**A:** Broad patterns (i.e. diagonal, horizontal, and vertical edges)


**Q: Are image models only useful for photos?**

**A:** No. A lot of other data can be represented as images: matrices, sound spectrograms, time series plots...


**Q: What is an "architecture"?**

**A:** The function whose weights are adjusted according to the problem and the desired input->output relationships.


**Q: What is segmentation?**

**A:** Creation of a model that can recognize the content of every individual pixel in an image.


**Q: What is y_range used for? When do we need it?**

**A:** It is used for ensuring that the predictions of a model does not exceed user defined limits. We need it when we are sure that values outside of this `y_range` are meaningless in our case.


**Q: What are "hyperparameters"?**

**A:** Higher level parameters impacting the performance of the model without being learned in training. (i.e. learning rate, number of epochs)


**Q: What's the best way to avoid failures when using AI in an organization?**

**A:** -


**Q: What is a p value?**

**A:** Probability of a value or its further deviations from the expectation occurring


**Q: What is a prior?**

**A:** Previous knowledge on a subject matter


**Q: Provide an example of where the bear classification model might work poorly in production, due to structural or style differences in the training data.**

**A:** On different animals, on different types of bears...


**Q: Where do text models currently have a major deficiency?**

**A:** They are not guaranteed to provide correct responses.


**Q: What are possible negative societal implications of text generation models?**

**A:** As they are fed with texts from the Internet, they are inclined to spread misinformation, create unrest, and encourage conflict.


**Q: In situations where a model might make mistakes, and those mistakes could be harmful, what is a good alternative to automating a process?**

**A:** Without ditching the model, it should be used as guides to human experts.


**Q: What kind of tabular data is deep learning particularly good at?**

**A:** Those that have variables with lots of discrete levels (high cardinality)


**Q: What's a key downside of directly using a deep learning model for recommendation systems?**

**A:** Its recommendations may not point the user to a direction he/she would not go on his/her own.


**Q: What are the steps of the Drivetrain Approach?**

**A:** Defined Objective -> Levers

-> Data -> Models


**Q: How do the steps of the Drivetrain Approach map to a recommendation system?**

**A:**

*Defined objective:* Recommending items

*Levers:* Possible recommendations

*Data:* User's purchasing habits

*Models:* How often other users with same habits have purchased the possible recommendations


**Q: Create an image recognition model using data you curate, and deploy it on the web.**

**A:**


**Q: What is DataLoaders?**

**A:** A class in fastai that provides the data for the model


**Q: What four things do we need to tell fastai to create DataLoaders?**

**A:**

1. Type of data
2. How to get the list of items
3. How to label them
4. How to create the validation set


**Q: What does the splitter parameter to DataBlock do?**

**A:** It splits the data into training and validation sets.


**Q: How do we ensure a random split always gives the same validation set?**

**A:** With the `seed` parameter
