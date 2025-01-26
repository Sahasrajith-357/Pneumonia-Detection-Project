# Pneumonia-Detection-Project

## COMPARISON OF PERFORMANCE OF DIFFERENT CNN ARCHITECTURES IN PNEUMONIA DETECTION 

### ARCHITECTURES USED:
1. VGG19  
2. InceptionV3  
3. Xception  

### Dataset used for training, testing, and validation:
[Kaggle - Chest X-ray Pneumonia Dataset](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia)  

#### Dataset Details:
- **Training set**:  
  - PNEUMONIA: 3875 images  
  - NORMAL: 1341 images  

- **Test set**:  
  - PNEUMONIA: 390 images  
  - NORMAL: 234 images  

- **Validation set**:  
  - PNEUMONIA: 16 images  
  - NORMAL: 16 images  

### Implementation Details:
- All the images in the training set were converted to numpy arrays and stored (`images`), and the labels of each class were stored in a numpy array (`labels`).  
- The training set was split into training and validation sets in an 80:20 ratio.  
- To handle the imbalance between the classes (Pneumonia has more images), class weights were computed and used.

### Building the Model:
With the help of transfer learning, existing architectures trained on large datasets such as **ImageNet** were used to build the final model.

- The top layer of the base model was removed, and the classifier was modified to suit our problem.  
- The weights were frozen, and the model was trained in **inference mode**.  
- **Adam optimizer** and **binary cross-entropy** were used as the optimizer and loss function, respectively.  
- Once the training was completed, the base model was unfrozen, and the model was fine-tuned by training it using a **low learning rate**.

### Testing the Model:
- Training vs. validation accuracy and loss graphs were plotted.  
- The model was evaluated on the **test set**.  
- **Performance metrics** such as F1 Score, Recall, Precision, and a Confusion Matrix were calculated for each of the models.  
- A comparison of the models' performances was tabulated based on the performance metrics.  
- The final **best model** was selected for Pneumonia Detection.

