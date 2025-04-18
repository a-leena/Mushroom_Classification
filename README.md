# Mushroom Classification

<p> The objective of this project is to classify mushrooms as ‘edible’ or ‘poisonous’, using several different machine learning models, based on various physical features of mushrooms such as their cap shape and color, gill size and color, odor, bruises, population, etc.</p>
<p>The dataset used, that was obtained from <a href="https://www.kaggle.com/datasets/uciml/mushroom-classification?resource=download">Kaggle</a>, contains 8124 instances of mushrooms with 22 physical characteristics and a binary target/class label – ‘p’ for poisonous and ‘e’ for edible.</p>

## Models Used
<p> The below models were trained and tested on the 2 pre-processed datasets (with 20 and 6 features). </p>
<ol>
<li> Logistic Regression </li>
<li> Softmax Regression </li>
<li> Decision Tree </li>
<li> Bagging Classifier </li>
<li> Pasting Classifier </li>
<li> Random Forest Classifier </li>
<li> AdaBoost Classifier </li>
<li> Gradient Classifier </li>
<li> Hard Voting Classifier </li>
<li> Soft Voting Classifier </li>
<li> Stacking Classifier </li>
<li> Linear Kernel SVC </li>
<li> Polynomial Kernel SVC </li>
<li> RBF Kernel SVC </li>
</ol>

## Results & Observations
<p> In summary, all the models that involved decision trees in some manner, such as decision trees themselves or ensemble learning models (Bagging, Pasting, Random Forest, AdaBoost, and Gradient Boosting) using decision trees as base estimators, were the models that performed best in classification, with both datasets. </p>

<p> Other than the tree-based models, support-vector classifier using the polynomial kernel of degree 5 also gave 100% accuracy, precision, and recall, in classifying the mushrooms, with both datasets. </p>

<p> On the other hand, SVC with RBF kernel gave 100% accuracy, precision, and recall, when classifying mushrooms using the smaller dataset (6 features), while giving 100% precision but only 98% accuracy and 97% recall with the bigger dataset (20 features). </p>

<p> Logistic Regression, Softmax Regression, and SVC with Linear Kernels, couldn’t meet the performance levels of the other models even after hyperparameter tuning, and their performances declined even more when using the dataset of smaller feature-space. </p>

<p> The voting are not very reliable either. Since, softmax and logistic regressors were the poor performing estimators, voting classifiers were used on them alongside decision trees to make an attempt at improving their predictive capabilities. Neither hard voting nor soft voting gave 100% performance with either datasets, but their performances were better than the individual performances of Logistic and Softmax regressors. However, similar to the component estimators, the performance of the voting classifiers also decreased when fitted on the 6D data, although this decline was more pronounced for the hard-voting classifier than soft-voting. </p>

<p> The stacking classifier was used with logistic regressor and decision tree, as well as, with softmax regressor and decision tree, using another logistic regressor as the final estimator. When fitted on both the 20D and 6D data, the two pairs of stacking classifiers classified the mushrooms with 100% accuracy, precision, and recall. </p>

<p style="color: red;">View the confusion matrices and values to all performance metrics for individual models in the Jupyter Notebooks - Mushroom Classiification 20D and Mushroom Classification 6D.</p>

## Conclusion
<p> Since, tree-based models gave the best results, Decision Tree Classifier could be the best option among all as it’s the least computationally intensive model, least complex, and also highly explainable. Although, support-vector classifier with the polynomial kernel also performed equally well, it required a polynomial of degree 5. When thinking about applying these models in a real-life scenario, where, it is likely that non-ML-experts will also be involved, a simpler and easily interpretable model, that is able to predict with high accuracy, precision, and recall, should be preferred. </p>
