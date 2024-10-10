# Smart-Waste-Classifier-for-Germany-s-Recycling-System-using-Neural-Networks

This project utilizes a neural network to classify waste into nine categories: household waste, electronics, clothing, glass, plastics, paper, organic waste, batteries, and hazardous materials. The primary motivation behind this initiative is to teach expats who are new to Germany how to correctly sort their trash, as the recycling system can be quite complex. 

Drawing from my own experience of navigating waste management when I first arrived in Germany, I found it challenging to identify the appropriate disposal methods for different items. Some waste, such as TVs and hazardous materials, must be taken to special facilities, while other items simply need to go in specific bins. This classifier aims to simplify the process by helping users accurately determine the correct bin or disposal method for each item. Ultimately, the goal is to promote proper recycling and sustainability in Germany through effective waste sorting, making it easier for foreigners to adapt to local practices.

## Resources Used

**Python Version**: 3.12.1

**Packages**: numpy,matplotlib,tensorflor.keras,os, imghdr,cv2

## Data Collection and Data Cleaning

Pictures from the 9 different categories were collected from google pictures, downloading them with the expension "Download All Images". The dataset contains more than 1000 pictures.
Some pictures that had non-compatible formats could be eliminated by hand, as well as pictures under 10KB and unrelated pictures that add noise to the analysis.
I was struggling to run the dataset at the beginning for two reasons:
 * There were still pictures that for whatever reason were problematic or corrupted
 * I kept on getting an UTF-8 error since the original names of the pictures contained Non-ASCII characters.
The first problem was solved by coding an identifier that found these corrupted pictures and then deleted them, and the second issue was solved by another piece of code that renames all the pictures by consecutive numbers

## Data Import

The dataset was imported according to the right format for Neural Networks, which means, that the pictures are organized into batches. The data had to be normalized as well.

## Model Building and Training

Three models were built, but I will only go deep into the one that gave the best results.
The arquitecture of this Neural Network can be explained as follow:

* Convolutional Layers: The first layer applies 16 filters (3x3) with ReLU activation and 'same' padding to maintain the input dimensions (256x256x3). This is followed by a max pooling layer that reduces the spatial size. The second and third convolutional layers use 32 and 64 filters, respectively, enhancing feature extraction.

* Flattening: The output is flattened into a 1D vector for input into the dense layers.

* Dense Layers: A dense layer with 256 neurons processes the features, followed by an output layer with 9 neurons and a softmax activation function for multi-class classification. This architecture efficiently learns and classifies images into nine categories.

After training this model I got the following accuracy and loss function values: 

Accuracy:

 * Training accuracy improves significantly, starting from 14.7% in Epoch 1 and reaching 99.3% by Epoch 20.
 * Validation accuracy also increases from 38.1% in Epoch 1, peaking at 76% in Epoch 18, before slightly decreasing to 69.7% by Epoch 20.

Loss:

* Training loss consistently decreases, indicating that the model is learning well, starting at 3.08 and reducing to 0.026 by Epoch 20.
* Validation loss fluctuates, decreasing at first but increasing after Epoch 8, suggesting some potential overfitting. It starts at 1.98, reaches a low of 1.31 in Epoch 14, and ends at 1.65 in Epoch 20.

## Plot Performance


## Testing

The model was evaluated using a dataset consisting of 20 images from each of the nine categories. The results demonstrated strong classification performance, with accuracy ranging from 16 out of 20 to a perfect score of 20 out of 20 in four of the categories.
