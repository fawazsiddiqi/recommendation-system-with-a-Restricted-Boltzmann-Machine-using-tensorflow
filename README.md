# Build a Recommendation Engine with a Restricted Boltzmann Machine using TensorFlow
In this code pattern, we are going to build a Restricted Boltzmann Machine using TensorFlow that will give us recommendations based on movies that have been watched already. The datasets we are going to use are acquired from <a href="http://grouplens.org/datasets/movielens/">GroupLens</a> and contains movies, users, and movie ratings by these users. We are using a sigmoid activation function for the Neural Network and the recommendations are given based on the recommendation score generated by a Restricted Boltzmann Machine (RBM).

## What is a Restricted Boltzmann Machine (RBM)?
But before we start, let's talk a bit about the basics of RBM. An RBM is a two-layered (input layer and hidden layer) Artificial Neural Network which learns a probability distribution based on a set of inputs, it is a stochastic (non-deterministic) which helps us solve different combination based problems. RBM's can be used for dimensionality reduction, classification, regression, collaborative filtering, feature learning, and topic modeling.

As the name suggests, RBM is a class of Boltzmann machines, but they are restricted in certain ways when considering the connections between the input and the hidden nodes of the Neural Network, and thus it is easier to implement an RBM than a Boltzmann machine. The layers and the nodes within those layers are connected in a one-to-many fashion where each node in the input layer is connected to every node in the hidden layer, but no node within each layer is connected. The restriction allows more streamlined training algorithms than what is generally used in Boltzmann machines.

This is how an RBM looks like, as you can see all the nodes in the input layer are connected to each node in the hidden layer, and the structure of the Neural Network itself makes it efficient when it comes to training our Neural Network as one input layer can use many hidden layers for training. Multiple RBMs can be stacked on as well creating a Deep Belief Network which will allow deeper learning of the neural network and incorporate further learning.

![rbm_networks](https://github.com/fawazsiddiqi/recommendation-system-with-a-Restricted-Boltzmann-Machine-using-tensorflow/blob/master/images/rbm_network.png?raw=true)


## How does a Restricted Boltzmann Machine (RBM) work?

There are two steps involved when it comes to the working of an RBM:
- Multiple Inputs
- Reconstructing

#### Multiple Inputs

![rbm_multi](https://github.com/fawazsiddiqi/recommendation-system-with-a-Restricted-Boltzmann-Machine-using-tensorflow/blob/master/images/multiinputs.png?raw=true)

Multiple inputs are considered to be the first step when it comes to the training of the Neural Network, the inputs are taken into the input layer, multiplied by the weights, and is added to the bias. After which it goes through the activation function (sigmoid) and thus the outputs decide if the hidden state gets activated. 

The weights in the Neural Network are in a matrix, where the number of input nodes is the number of rows and the number of hidden nodes is the number of columns. Furthermore, the primary hidden node will obtain the vector multiplication of the inputs and will be multiplied by the first column of weights before the corresponding bias term is added to it.

#### Reconstruction

![rbm_recon](https://github.com/fawazsiddiqi/recommendation-system-with-a-Restricted-Boltzmann-Machine-using-tensorflow/blob/master/images/reconstruction.png?raw=true)

In reconstruction, the logic is pretty simple, we habe the activations which are the inputs at this point, which are then passed to the hidden layer and then to the input later after which new biases are obtained and the reconstruction is the new output.

**So how does the learning process really work?** As these two steps happen subsequently, where first we generate activations using multiple inputs phase and then reconstruction takes place when the reconstruction is taking place in an epoch, our main goal here is to decrease the reconstruction error, thus the weights are then adjusted per-iteration accordingly by the algorithm to decrease the reconstruction error which will result in giving us a good prediction/higher accuracy.

<p align="center">
<img src="https://github.com/fawazsiddiqi/recommendation-system-with-a-Restricted-Boltzmann-Machine-using-tensorflow/blob/master/images/films.png?raw=true"  width="600">
</p>

## Where else is RBM used?

- Recommendation Systems
- Representation Learning (Feature Learning)
- Image Recognition
- Natural Language Understanding (Deep Belief Network)

## Lets Get Started

1. Sign up or log in.

    * Activate Watson Studio by logging in to your IBM Cloud account from the [Try IBM Watson](https://dataplatform.cloud.ibm.com/registration/stepone?cm_sp=ibmdev-_-developer-tutorials-_-cloudreg) page.
    * Access Watson Studio, by logging in at [https://dataplatform.cloud.ibm.com](https://dataplatform.cloud.ibm.com?cm_sp=ibmdev-_-developer-tutorials-_-cloudreg).

1. Create an empty project.

    * Click either **Create a project** or **New project**.
    * Select **Create an empty project**.
    * Give the project a name.
    * Choose an existing Object Storage service instance or create a new one.
    * Click **Create**.

1. Add the Notebook.

   * Click **+Add to project**.
   * Click **Notebook**.
   * Click **From URL**.
   * Provide a **Name**.
   * Under **Select runtime**, choose **Default Python 3.6 Free**.
   * Enter `https://raw.githubusercontent.com/fawazsiddiqi/recommendation-system-with-a-Restricted-Boltzmann-Machine-using-tensorflow/master/notebooks/CollaborativeFilteringwithRBM.ipynb` as the **Notebook URL**.
   * Click **Create Notebook**.

1. Run the Notebook.

   In the open Notebook, click **Run** to run the cells one at a time. The rest of the tutorial follows the order of the Notebook.
