# Pneumonia-Detection-Project
COMPARISON OF PERFORMANCE OF DIFFERENT CNN ARCHITECTURES IN PNEUMONIA DETECTION 

ARCHITECTURES USED : 
  1. VGG19
  2. InceptionV3
  3. Xception

Dataset used for training, testing and validation :
  https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia
    dataset : 
      trainining set : 
              PNEUMONIA : 3875 images
              NORMAL : 1341 images
      test set :
              PNEUMONIA : 390 images
              NORMAL : 234 images
      validation set : 
              PNEUMONIA : 16 images
              NORMAL : 16 images
              
  -> All the images in the training set were converted to numpy arrays and stored (images) and the labels of each class were also stored in a numpy array (labels)
  -> the training set was split into training and validation set in an 80:20 ratio
  -> to handle the imbalance between the amount of data avaiable for both the classes (Pneumonia has more number of images), class weights are computed and used

Building the model :
  with the help transfer learning, existing architectures trained on large datasets such as 'imagenet' were used to build the final model
  -> the top layer of the base model was removed and the classifier was alone modified to suit our problem 
  -> the weights were frozen and the model was trained in inference mode 
  -> adam optimizer and binarycrossentropy were the optimizer and loss function used for training the model
  -> once the training was finished, the base model was unfreezed and the model was fine tuned by training it using a low learning rate

Testing the model :
  -> the training vs validation accuracy and loss graphs were plotted 
  -> the model was evaluated on the test set 
  -> performance metrics : F1 score, Recall, and Precision and confusion matrix were calculated for each of the models
  -> the comparison of the models' performances was tabulated based on the performance metrics
  -> the final best model was selected for Pneumonia Detection
  
  
