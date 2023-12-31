# german-credit-pytorch
This is an implementation of PyTorch Neural Network for German Credit Dataset. This has accuracy and precision around 90%.


In this project we were tasked with building a classification model using PyTorch Library. The dataset consists of 30 input numerical features and 1 ouput categorical feature. To sucessfully implement this, we first made the dataset balanced using downsampling. 

<img src="ClassImbalance.png" height="300"> <img src="Class balance.png" height="350">

The model is also then validated over the whole dataset with very overall accuracy and precision for detecting fraud. Initially is dataset was extremely unbalanes (<1%). Downsampling was the preferred method out of SMOTE or Downsampling, becase, SMOTE artificially adds datapouints, and this makes the dataset biased, also even after downsampling, we would have enough rows to successfully implement the ML model. There are many outliers detected in the dataset but, removing the dataset also removed the fraud transactions, therefore no ouliers were removed. Then we checked the parameters by comparing means for both the classes' input features using standard deviation. This helped us reduce the input parameters from 30 to 17, which is almost 44% reduction in input dimension.

For the pytorch model we made a simple linear model with layers as (17 nodes - input, 32 nodes - hidden, 1 node - output). Then we created a training function for it that implemented features like early stopping using tolerence for change in loss for each epoch, warmup period, optimiser (ADAM used), loss function (criterion - Binary cross entropy with logits used) and printing loss & accuracy for each epoch. Then in the test function features like precision calculation, plotting the graph for correct and incorrect prediction is used along with plotting confusion matrix.

<img src="TrainingLossAndAcc.png">

Overall this model gets precision of 0.90 with accuracy of 0.94 in testing (downsampled dataset with 0.2 testing) and precision of 0.92 with accuracy of 0.89 in validation over the entire dataset.

<img src="TestingPredictions.png" width="350"> <img src="Validationprediction.png" width="350">

<img src="testingConfusionMatrix.png" width="350"> <img src="validationConfusionMatrix.png" width="350">
