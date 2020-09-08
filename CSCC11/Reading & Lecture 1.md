GitHub doesn't render inline markdown, if you fancy the original notion notes you can find them [here](https://www.notion.so/CSCC11-Reading-1-a45683eeaf394409a43ebab35d24f2c4)

---

# 1 Introduction to Machine Learning

Often, machine learning methods are broken into two phases:

1. `Training`, A model is learned from a collection of training data.
2. `Application`, The model is then used to make decisions about some new test data.

Machine learning is a large field, and learning problems abound, often in very different forms, discrete and continuous, with various degrees of labeled supervisory information. Some of the main types of machine learning are:

1. `Supervised Learning`, in which the training data is labeled with the correct answers. The two most common types of supervised learning are classification (outputs are discrete labels) and regression (outputs are real-valued).
$\text{given } \vec{x} \in \mathbb R^n \text{ find a parameter/configuration } \theta \text{ of } f(\vec{x}, \theta) \text{ to predict an output } y \in \mathbb R \ni: y = f(\vec{x}, \theta)$

    Classification outputs discrete y, where as Regression outputs y that is continuous in the reals

2. `Unsupervised Learning`, in which we are given a collection of unlabeled data, which we wish to analyze and discover patterns within. The two most important examples are dimension reduction and clustering.

    Clustering: Given a bunch of documents, return the ones that are similar, such as news articles and their related topics (sports, entertainment ...)

    Dimensionality Reduction: Given high dimensional inputs, we want to find the a lower dimensional encoding. (image compression: `1920 x 1080 RGB` picture to `100 x 100 grayscale`) Useful for feature selection (not all dimensions are useful).

    Density Estimation: Given imputs, return the probability distribution over the data. For example, probability distribution that describes which images are `likely` 

3. `Reinforcement Learning`, in which an agent (a robot/controller) seeks to learn the optimal actions to take based on the state of the world, and hence the consequences of past actions.

There are many other types of machine learning as well, most of which won't be covered in this course key examples include:

1. Semi-supervised Learning
2. Active Learning
3. Transfer/Meta/Few-Shot Learning
4. Structured Prediction
5. Time-series Forecasting
6. Anomaly Detection
7. Deep Learning

## 1.1 A simple Problem

<p align="center">
  <img src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/e65bc114-e5f6-45ab-bd77-eb388dcc7abc/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200908%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200908T172300Z&X-Amz-Expires=86400&X-Amz-Signature=3299e8282e905bf479b3900d21c982144629493b4c6200d2de6cf5a7cb2a2424&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22" />
</p>


The figure above represents a simple linear regression problem. The blue circles are the measurements/training data and the red curves are possible ways to fit the data. There is no one 'right answer'. The solution we prefer depends on the problem. However, in general we prefer the simple smooth models like the one on the lower right over some of the other clearly overfitted models.

### Central questions:

There are infinitely many ways curves can fit the data, and, because the data might be noisy, we might not even want to fit the data precisely. Hence, machine learning requires we make the following choices:

1. How do we parameterize the `model` we fit. In Figure 1, how do we parameterize the curve; should we try to explain the data with a linear function, quadratic, or sinusoidal curve?
2. What criteria (objective function or `loss function`) do we use to judge the quality of the fit? For example when fitting a curve to noisy data, its common to measure the quality of the fit in terms of the squared error between the data we are given and the fitted curve. Minimizing the equared error results in a fit that is called a `least-squares estimate`. 

    Typically, the loss is 0 if there are no mistakes, positive otherwise. More examples if ways to measure the quality of the fit includes `vertical distance` and `orthogonal distance`

    For `classification`, we can count the number of errors.

3. Some types of models and some model parameters can be expensive to optimize. How long are we willing to wait for a solution, or can we use approximation/hand tuning-instead?
4. Ideally we want to find a model that will provide useful predictions in future situations. That is, although we might learn a model from training data, we ultimately care about how well it works on future test data. When a model fits training data well but performs poorly on real data, this is called overfitting the training data. Properties such as noise has a significant effect on this, when this happens we say that the model does not generalize well to the test data.

Some advanced methods provide ways of automating these choices. Using machine learning in practice requires that you make your own use of prior knowledge and experimentation to solve problems.
