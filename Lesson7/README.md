# Questionnaire for Lesson 7

**Q: What is another name for weight decay?**

**A:** L2 regularization


**Q: Write the equation for weight decay (without peeking!).**

**A:** `loss += wd * (weights**2).sum()`


**Q: Write the equation for the gradient of weight decay. Why does it help reduce weights?**

**A:** `grad += WD * weights`


**Q: Why does reducing weights lead to better generalization?**

**A:** It yields a shallower loss curve.


**Q: What does argsort do in PyTorch?**

**A:** returns the indices that sort a tensor


**Q: Does sorting the movie biases give the same result as averaging overall movie ratings by movie? Why/why not?**

**A:** No. Bias is more related to whether the product/item meets the expectations of the users.


**Q: How do you print the names and details of the layers in a model?**

**A:** `learn.model`


**Q: What is the "bootstrapping problem" in collaborative filtering?**

**A:** shortage of user history


**Q: How could you deal with the bootstrapping problem for new users? For new movies?**

**A:** by asking relevant questions to newly registered users


**Q: How can feedback loops impact collaborative filtering systems?**

**A:** If the recommendation system is skewed by a small number of users, it will keep on skewing toward the same direction with amplified velocity.


**Q: When using a neural network in collaborative filtering, why can we have different numbers of factors for movies and users?**

**A:** -


**Q: Why is there an nn.Sequential in the CollabNN model?**

**A:** -


**Q: What kind of model should we use if we want to add metadata about users and items, or information such as date and time, to a collaborative filtering model?**

**A:** -


**Q: What is a continuous variable?**

**A:** numeric variable


**Q: What is a categorical variable?**

**A:** variable whose value is limited to a discrete set


**Q: Provide two of the words that are used for the possible values of a categorical variable.**

**A:** discrete levels, categories


**Q: What is a "dense layer"?**

**A:** a linear layer


**Q: How do entity embeddings reduce memory usage and speed up neural networks?**

**A:** -


**Q: What kinds of datasets are entity embeddings especially useful for?**

**A:** datasets with lots of high cardinality features


**Q: What are the two main families of machine learning algorithms?**

**A:** ensembles of decision trees, multilayered neural networks learned with SGD


**Q: Why do some categorical columns need a special ordering in their classes? How do you do this in Pandas?**

**A:** Ordering these columns in their natural ordering makes the training more efficient.
```
df['column'] = df['column'].astype('category')
df['column'].cat.set_categories(ordered_cat_list, ordered=True, inplace=True)
```


**Q: Summarize what a decision tree algorithm does.**

**A:** -


**Q: Why is a date different from a regular categorical or continuous variable, and how can you preprocess it to allow it to be used in a model?**

**A:** Dates have periodical components. `df = add_datepart(df, 'date')`


**Q: Should you pick a random validation set in the bulldozer competition? If no, what kind of validation set should you pick?**

**A:** No, the validation set should be from the recent dates in the training set, to ensure the model does not see the validation set in its training phase.


**Q: What is pickle and what is it useful for?**

**A:** It is a Python package that is useful for saving (consequently, also loading) any Python object.


**Q: How are mse, samples, and values calculated in the decision tree drawn in this chapter?**

**A:**

*samples:* Number of data in the leaf
*value:* Mean of the target values of the data in the leaf
*mse:* MSE of the mean and actual target values


**Q: How do we deal with outliers, before building a decision tree?**

**A:** -


**Q: How do we handle categorical variables in a decision tree?**

**A:** 'it just works': The tree splits the categories into groups.


**Q: What is bagging?**

**A:** Bagging is training several models on randomly chosen subsets of the dataset, and taking the average of these models' predictions.


**Q: What is the difference between max_samples and max_features when creating a random forest?**

**A:**

*max_samples:* max number of rows
*max_features:* max portion of columns


**Q: If you increase n_estimators to a very high value, can that lead to overfitting? Why or why not?**

**A:** -


**Q: In the section "Creating a Random Forest", just after <<max_features>>, why did preds.mean(0) give the same result as our random forest?**

**A:** Random forest takes the mean of its predictions, too.


**Q: What is "out-of-bag-error"?**

**A:** error of a row on trees in the training of which that row was not used


**Q: Make a list of reasons why a model's validation set error might be worse than the OOB error. How could you test your hypotheses?**

**A:** -


**Q: Explain why random forests are well suited to answering each of the following questions:**

**How confident are we in our predictions using a particular row of data?**

**A:** `preds.std(0)`

**For predicting with a particular row of data, what were the most important factors, and how did they influence that prediction?**

**A:** -

**Which columns are the strongest predictors?**

**A:**

```
def rf_feat_importance(m, df):
    return pd.DataFrame({'cols':df.columns, 'imp':m.feature_importances_}
                       ).sort_values('imp', ascending=False)

fi = rf_feat_importance(m, xs)
fi[:10]
```

**How do predictions vary as we vary these columns?**

**A:** `sklearn.inspection.plot_partial_dependence`


**Q: What's the purpose of removing unimportant variables?**

**A:** better intuition, clearer analysis


**Q: What's a good type of plot for showing tree interpreter results?**

**A:** waterfall


**Q: What is the "extrapolation problem"?**

**A:** Random forests cannot produce prediction values outside of the range that they have faced during training.


**Q: How can you tell if your test or validation set is distributed in a different way than your training set?**

**A:** fitting the random forest with the target value indicating whether the input belongs to the training set


**Q: Why do we make saleElapsed a continuous variable, even although it has less than 9,000 distinct values?**

**A:** It is an indicator of time.


**Q: What is "boosting"?**

**A:** adding models instead of averaging them, also after first iteration, switching target values for the residuals


**Q: How could we use embeddings with a random forest? Would we expect this to help?**

**A:** The inputs of the random forest are replaced by the embeddings. -


**Q: Why might we not always use a neural net for tabular modeling**

**A:** Random forests and/or gradient boosting machines might yield as successful, if not more successful results without taking as much time to train.
