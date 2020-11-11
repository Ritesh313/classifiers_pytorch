# Wine-data-classifier-using-pytorch 
Dataset link: https://archive.ics.uci.edu/ml/datasets/Wine
## Goals of this repository:

- Experimenting with different learning rate, number of layers and nodes.
- Trying different loss functions and optimizers.
- There is a create_data_csv function which you can use to evenly divide a dataset like this one, in train, test and valid with the required changes depending on the dataset.

Task: Designing a single hidden layer MLP for wine dataset: The code should run if you just downlaod and run the notebook. You can change the number of layers if you want but no more than 2 layers are required for this dataset. With single layer and appropriate learning rate you should achieve 100% accuracy.
### General information:
I have used pytorch framework for my model and I am using it in the conda environment on
a windows 10 machine.
Please note: If there is no conda environment then the libraries needed for my code would
be:
➔ torch
➔ pandas
➔ numpy
➔ os
➔ sklearn: preprocessing and metrics modules
➔ matplotlib

#### Describing my single layer MLP and results (confusion matrix and analysis):

I have made a one layer network with ReLU non-linearity, the hidden layer has 7
nodes and the input layer has 13 nodes for the 13 features (constituents) provided in
the dataset and finally the output layer has 3 nodes (one for each wine class).
So, here are a few details about my classification model:
* The network looks like this: 13➡7➡3 .
* I have split the data into 80% training and then in the training data 20% is
for validation which I’ve used for early stopping.
* I have encoded the true output (using label encoder) and I normalized
the input columns to be in range 0 to 1 which is the most fundamental
step here, in my opinion.
* The activation function for the hidden layer is ReLU .
* Loss function is Cross entropy and hence no softmax for the predicted
output as it’s already there in the pytorch’s “ nn.crossentropy ”.
* I have used SGD (Stochastic Gradient Descent) optimizer in my code.
* I have trained my model for 100 epochs or 100% validation accuracy
whichever comes first. With 0.4 learning rate it usually achieves 100%
validation accuracy in about 12 epochs (refer to the accuracy and loss plots
below).
* I have used 0.4 learning rate. I experimented with some other values too, that
is in the next section.
I calculated the accuracy in both validation and training and I plotted them against the
epochs. One thing to note is that with 0.4 learning rate the model stops at about 12 epochs
because of the 100% validation accuracy.
