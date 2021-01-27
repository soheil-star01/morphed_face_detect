## Detecting Morphed portraits using BoVW and ensemble DNN method

# BoVW
to understand the idea of Bag of Virtual Words you can take a look at this link: https://ianlondon.github.io/blog/how-to-sift-opencv/

the procedure can be explained as these steps:

1- reading all images and store them in Numpy arrays 

2- finding _keypoints_ of all images using SIFT method from OpenCV package

![Alt text](readme_img/bovw_keypoints.png?raw=true)

3- using the extracted _keypoints_ (each _keypoint_ is a 128-element vector) to define clusters (words). I used K-means for this part.

4- check images to see which Visual Words are in them

5- train a binary classification model. I used XGBoost classifier

### Resulted Confusion Matrix
![Alt text](readme_img/bovw_res.png?raw=true)

# DNN
I used three classification DNN structures to create the ensemble model which are:

1- ResNet101V2 

2- InceptionV3

3- VGG19

### Resulted Confusion Matrix
![Alt text](readme_img/dnn_res.png?raw=true)
