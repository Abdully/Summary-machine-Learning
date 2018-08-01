# Ensembles of Decision Tree
As the method that combine multiple machine lerning models to crete more powerful model.The following are method.
## Random Forest
The main drawback of decision tree is that they tend to overfttinng the train data.The random solve this problem  because this deal
with collection of tree.Due to the deal with collection of tree it reducee the ammount of overfiting by average their result.In older 
to impliment this need to buld many decision tree.On this each tree should an acceptable job of predicting the target and should also 
be diffrent from the other trees.There are two way in wich the tree in random forest can randomized one is by select the data point
used tob buld a tree and another is by selecting the feature in ecah split.
## Bulding Random Forest
First decide number of tree to buld (the n-estimator parameter of RandomForestRegression or RandomForestClassifier). The algorithm 
will make different random choice for each tree to makesure the tree are distinct.Create bootstrap sample of our data (n_sample). 
Bootstrap sample  is a smaller sample that is “bootstrapped” from a larger sample. Bootstrapping is a type of resampling where large 
numbers of smaller samples of the same size are repeatedly drawn, with replacement, from a single original 
sample.You randomly draw three numbers 5, 1, and 49.It look for select a subset of the feature and loock for the best possible test 
involving one of these feature.the number of feature selected controlled by max _feature parameter.The bootstrap sampling lead to 
each decison tree in the random forest being built on slightly different dataset.Selection feature on each node each split in each
tree operate n different subset of features.
A critical parameter inthis process is max_features.If you set max_feature to n_feature it mean that each split can look at  all
feature in the dataset, and no random will be injected in the feature selection (it remain).And if max_feature to 1 mean that split 
have no choice at all which feature to test.The higher max_feature is better.The Random Forest is best fo both classification and 
regression,to make predictin for regresion we can average result but for classificatin 'soft voting' strategy is used.
## Strength ,Weakness and Parameter
###  Strength
Random forest tend to be deeper than decion tree because of the use of feature subsets.
Smaller max_feature reducing overfitting.
### Parameter
max_feature=sqrt(n_feature) for classification and max_feature=log base 2(n_feature) for regression.
### Weakness
Random forest does not perform well on very high dimesion,sparse data such as text data but leaner modelsolve this problem.
