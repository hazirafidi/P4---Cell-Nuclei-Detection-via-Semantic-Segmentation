# P4 - Cell Nuclei Detection via Semantic Segmentation

Semantic segmentation for Cell Nuclei Detection using Deep Learning U-Net

## 1. Project Summary

This project is carried out to implement Deep Learning Model Training for Semantic Segmentation via U-Net. The objective of this project is to train a model that be able to detect cell nuclei in bidomedical images and since that the cells are usually varies in shape and sizes, semantic segmentation is the best method for implementation. U-net has been a generic solution for quantification tasks such as cell detection and shape measurements in biomedical image data according to Falk, T., Mai, D., Bensch, R. et al. U-Net: deep learning for cell counting, detection, and morphometry. Nat Methods 16, 67–70 (2019) [Link](https://pubmed.ncbi.nlm.nih.gov/30559429/).


## 2. IDE and Framework 

The project is built with Jupyter Notebook as the main IDE and the model is trained via Google Colab Notebook. The main frameworks used in this project are TensorFlow, Numpy, Matplotlib, OpenCV and Scikit-learn.

 
## 3. Methodology

The methodolgy of this project is inpired by Tensorflow Image Segmentation Tutorial. The documentation can be found via [this link](https://www.tensorflow.org/tutorials/images/segmentation).

 
### 3.1 Input Pipeline

The dataset files contains a train folder for training data and test folder for testing data, in the format of images for inputs and image masks for the labels. The input images are preprocessed with feature scaling. The labels are preprocessed such that the values are in binary of 0 and 1. No data augmentation is applied for the dataset. The train data is split into train-validation sets, with a ratio of 80:20


### 3.2 Model Pipeline 

The model architecture can be illustrate as figure below.
 
![image](/images/model_architecture.png)
 
The model architecture used for this project is U-Net. You can refer to the TensorFlow documentation for further details. In summary, the model consist of two components, the downward stack, which serves as the feature extractor, and upward stack, which helps to produce pixel-wise output. The model structure is shown in the figure below.

![image](https://user-images.githubusercontent.com/100177902/163769994-ff4fc536-5da8-47bd-a014-bf5f020e8421.png)

The model is trained with a batch size of 10 and 100 epochs. Early stopping is also applied in the model training. The training stops at epoch 31, with a training accuracy of 97% and validation accuracy of 96% as seen in figure below.

![image](https://user-images.githubusercontent.com/100177902/164142173-19edd2c5-d689-4709-9840-cdf3b444bc08.png)

## 4. Result 

The model is evaluated with performance curve and prediction is made with test data and the results are shown in figure.

As we can see in the figure training and validation curve as well as training and validation curve is perfectly fit with no sign of overfitting or underfitting. 

![training_val_accuracy](https://user-images.githubusercontent.com/100177902/164142594-778a699d-e554-4504-a227-5598e191420a.png)

![training_val_loss](https://user-images.githubusercontent.com/100177902/164142688-b12a01e6-5e87-4fea-9200-789a3be73bca.png)

The model is then tested to make prediction using test data and the result obtained can be observed as in figures below.

![image](https://user-images.githubusercontent.com/100177902/164142286-1432dec0-e429-45ef-ace7-67ab321da0e0.png)
![image](https://user-images.githubusercontent.com/100177902/164142349-133cc97e-a9dd-4626-b300-8e3120f838c2.png)
![image](https://user-images.githubusercontent.com/100177902/164142386-9cf0db56-4d6a-4635-8b6a-e7510b2dba35.png)

The comparison can be observed with *input image, "rue mask and predicted mask*. It can be seen that cell nuclei in *predicted mask* not prefectly visible as the *true mask* but the model able to detect the cell nuclei in excellent way. The model can be improved with more data is feed to train the model to increase its performance.

## 5. Conclusion

Semantic segmentation with Deep Learning is widely used in solving Biomedical Image classification. This model succeded to achieve 97% accuracy with modified pre-trained model and converted into U-NET for image segmentation approach. 
