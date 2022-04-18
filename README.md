# P4 - Cell Nuclei Detection via Semantic Segmentation
 Semantic segmentation for Cell Nuclei Detection using U-Net
## 1. Project Summary
This project is carried out to implement Deep Learning Model Training for Semantic Segmentation via U-Net. The objective of this project is to train a model that be able to detect cell nuclei in bidomedical images and since that the cells are usually varies in shape and sizes, semantic segmentation is the best method to implement. U-net has been a generic solution for quantification tasks such as cell detection and shape measurements in biomedical image data accoriding to Falk, T., Mai, D., Bensch, R. et al. U-Net: deep learning for cell counting, detection, and morphometry. Nat Methods 16, 67–70 (2019) [Link](https://pubmed.ncbi.nlm.nih.gov/30559429/).


## 2. IDE and Framework 
The project is built with Google Colab Notebook as the main IDE. The main frameworks used in this project are TensorFlow, Numpy, Matplotlib, OpenCV and Scikit-learn.

 
## 3. Methodology

The methodolgy of this project is inpired by Tensorflow Image Segmentation Tutorial. You can find the documentation in [link text](https://www.tensorflow.org/tutorials/images/segmentation).

 
### 3.1 Input Pipeline

The dataset files contains a train folder for training data and test folder for testing data, in the format of images for inputs and image masks for the labels. The input images are preprocessed with feature scaling. The labels are preprocessed such that the values are in binary of 0 and 1. No data augmentation is applied for the dataset. The train data is split into train-validation sets, with a ratio of 80:20


### 3.2 Model Pipeline 
The model architecture can be illustrate as figure below.
 
 ![image](/images/model_architecture.png)
 
The model architecture used for this project is U-Net. You can refer to the TensorFlow documentation for further details. In summary, the model consist of two components, the downward stack, which serves as the feature extractor, and upward stack, which helps to produce pixel-wise output. The model structure is shown in the figure below.

 
The model is trained with a batch size of 10 and 100 epochs. Early stopping is also applied in the model training. The training stops at epoch 31, with a training accuracy of 97% and validation accuracy of 96%. The model training graphs are shown in figures below.
 
 ![image](https://user-images.githubusercontent.com/100177902/163766128-2d221500-198b-4123-99f1-10c179a5f12c.png)

## 4. Result 
The model is evaluated with test data, which is shown in figure below.
 
 ![image](https://user-images.githubusercontent.com/100177902/163766461-bae2e805-55cd-4e4d-9420-8dd59ba42a16.png)

## 5. Conclusion
Semantic segmentation with Deep Learning is widely used in solving Biomedical Image classification. This model succeded to achieve 97% accuracy with modified pre-trained model and converted into U-NET for image segmentation approach. 
