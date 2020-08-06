# Classification-CT-Scan-Images-Age-and-Contrast-CNN

**Abstract**

A computed tomography scan is a process which uses computers and X-ray machines which rotates to create cross-section images of body. The images provided by the CT scans are more accurate and detailed in comparison to normal X-ray images. The detail in the images can be increased by administering a chemical dye called contrast. The dye can be administered by a medical practitioner with prior permission from the patient as there is a risk of having side effects such as cancerous disease, head-aches and others. Our study aims at providing a classification model using a CNN learning algorithm to classify images based on age of a person and if contrast material is used. A practitioner hence can get prior knowledge about trends in CT scan images and if administering contrast material would affect the image in any way. Our proposed model provides an accuracy of 89.99% on any test CT image.

**Introduction**

During a Computed Tomography (CT) scan, a person is exposed for a short period of time to radiation through the process of ionization. The extent of radiation in a CT scan is greater than that exposed during X-ray since CT scans gives more detailed information about the subject in study. The small amount of doses of radiation emitted in a CT scan has not been seen to cause long-term harm, although at higher amount of doses there can be a minute increase in the risk of having chronic diseases like cancer. CT scans are often administered with or without a contrast media. The contrast material improves the ability of a radiologist to view the inside images of the body in a more detailed fashion. The contrast material is a special dye which tends to block X-rays and appear white on images; it helps in emphasizing the images under study. The contrast material can be administered by a practitioner either through mouth, injections or through enema. 

Sixteen years ago in a study it was found about the possibility of a risk of having cancer induced by pediatric controlled computed tomography scans and the potential of having harmful effects of contrast related exposures. The study predicted risks of fatal cancer ranging from 1 per 10000 to 1 per 1000 scanned patient, depending on their age and scanned body part.

Our study provides a classification model based on age of a patient and the contrast used in the CT scans and classifying the images for abnormalities and misclassifications to help doctors diagnose a patient based on classified output with respect to the features. We used a convolutional neural network to classify such images provided in the dataset. The dataset provided by The Cancer Imaging Archive (TCIA) includes a set of hundred CT images tagged with the age of a person and the contrast material usage. The model is successful in providing a classified result output and it was seen that it successfully classified the images on the basis of age and contrast with an 89.99% accuracy rate. 

**Dataset**

The results shown below are in whole or part based upon data generated by the TCGA Research Network. It contains a total number of 100 images of size 512 x 512. The training set and test set was divided in a 90:10 ratio. It also contains a list of patient’s age and contrast used for CT scan and mapped it with the images. The dataset contains eight columns – a serial number, Age, Contrast, Contrast tag, the input path, the id, image name and the DICOM image name. It is seen that half of the images have contrasts applied and others do not. The contrast tag tells us what kind of contrast dye is applied if used. An example of how the images in the dataset looks like is given in Fig.

![dataset](https://user-images.githubusercontent.com/31190025/89528301-6db2e500-d808-11ea-831c-ce8c5cc16be6.JPG)

**Results**

The convolutional neural network is able to learn from the given test images formed by splitting the hundred image into training and test images, to classify whether the images are rightly classified when it comes to age and contrast material used, if there are any misclassifications done. The model was seen initially to show over fitting which had been overcome later by using dropout layers and reducing the number of epochs for training. The output was coming in multiclass form which needed to be transformed to a single class output for analysis of the result. The accuracy achieved during the classification amounted to 89.99%.
During the training stage of the convolutional neural network structure, in each epoch the categorical cross-entropy loss function reduces due to the back-propagation during training stage. The loss values for each epoch value are shown in the following graph: 

 ![Loss](https://user-images.githubusercontent.com/31190025/89528590-f0d43b00-d808-11ea-869b-17e5f043f5a8.JPG)

From figure, it can see as the number of epochs increase the cross-entropy loss keeps on decreasing due to the gradient descent algorithm. Due to the forward propagation steps and corresponding back-propagation steps, the model learnt from the weights given and the corresponding accuracy of the model kept on increasing. The accuracy values for each epoch are shown in the following graph. 
 
![Accuracy](https://user-images.githubusercontent.com/31190025/89528631-fcbffd00-d808-11ea-8f04-02e4768115e1.JPG)

From figure, it can be seen that the accuracy of the model is increasing as the number of epochs increase. The average precision, average recall and average F1 score from the classification model are tabulated in the ipynb file.

The error matrix for the classification is given below in table 2. The classification that was applied to the ten test images from the dataset had nine such images correctly classified in terms of age and contrast used. One such image was wrongly classified in terms of contrast used.

![Confusion](https://user-images.githubusercontent.com/31190025/89528834-57f1ef80-d809-11ea-910b-486d5ba5190c.JPG)

The receiver operating characteristics curve (ROC) was drawn for the following test images and the area under the ROC curve (AUC) value was derived from it. Along with the result, from the confusion matrix, truly positive rates and false positive rates were calculated and with that the specificity and sensitivity percentages were derived and their results are shown in the ipynb file. 

During training, it was seen that over fitting was seen for number of epochs greater than six. It resulted in correct classification for all the test cases, evident from having a training accuracy of one. To rectify the errors, dropout layers were applied, it resulted in a perfectly fitted classified data. 

