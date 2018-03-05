# FaceDetector
<p align="center">
<a href = "https://github.com/yilmazvolkan/FaceDetector"><img 
<img src="https://github.com/yilmazvolkan/FaceDetector/blob/master/Res/faceDetector_logo.png" width="440" height="150"></a>
</p>

<p align="center">
    <a href="https://github.com/yilmazvolkan/FaceDetector/blob/master/README.md">
        <img src="https://img.shields.io/badge/DESCRIPTION-ONLINE-c2bc8c.svg"
             alt="Description">
    </a>
    <a href="https://github.com/yilmazvolkan/FaceDetector/blob/master/Res/face_recognition.py">
        <img src="https://img.shields.io/badge/Python-ONLINE-b1a86a.svg"
             alt="Python">
    </a>
    <a href="https://github.com/opencv/opencv/tree/master/data/haarcascades">
        <img src="https://img.shields.io/badge/HaarCascade-Link-988f50.svg"
             alt="HaarCascade">
    </a>
    <a href="https://github.com/yilmazvolkan/FaceDetector/issues?q=is%3Aissue+is%3Aclosed">
        <img src="https://img.shields.io/badge/ISSUES 3-CLOSED-827a44.svg"
             alt="Issues">
    </a>
</p>

## :flashlight: Before You Go

You need to install openCV library on Python. You can reach this library clicking on this [link](https://github.com/opencv/opencv).

## :tophat: Introduction

  Face detection substantially gains importance since their usage areas are getting wider. These days face detection is used in banks and smartphones to provide more secure systems, in social media and dating apps to match people and tag people easily, and even at schools to take attendance. It is also used in person emolojis with reflecting your shape and mood when you record.
  
To start with, face detection can be implemented through Viola-Jones Algorithm. It is the algorithm that lies at the foundation of openCV library and it is very powerful. It consists of training and detection stages. With this algorithm, there is a box that searches certain shapes for a face through pixels. It detects eyebrows, then eyes, then nose and keeps going like that. If it cannot find enough fetures, it understands it is not a face.

Moreover, Haar like features like scaleble edge,line and four-rectangle features are very important in detecting process. For example, in the face, lip is a line feature since there is a darkness where the two lips are joining and outside this there are bright regions. We can take difference between brightness and darkness to detect Haar like features with certain threshold of this difference. Once the algorithm identifies these features in the face through training, program understands what elements roughly a face is constructed from, then it will be used to detect faces.

<p align="center">
<a href = "https://github.com/yilmazvolkan/FaceDetector/blob/master/Res/integral_image_calc.png"><img 
<img src="https://github.com/yilmazvolkan/FaceDetector/blob/master/Res/integral_image_calc.png" width="350" height="210"></a>
</p>

However, processing Haar like features takes quite some time especially if you have lots of these features. Since they are scaleble, algorithm can find features over 100,000+. Integeral image shortens this process. The summed-area table is the sum of all the pixels above and to the left. In Integral Image algorithm, it calculates how many pixels it has until certain corner pixels and memories them to evaluate difference of brightness. While algorithm is comparing difference between brightness and darkness, throgh integral image feature, it just looks at certain pixels easily. Additionally, while the image size is getting bigger, it again just looks at those pixels without concerning about execution time.

<p align="center">
<a href = "https://github.com/yilmazvolkan/FaceDetector/blob/master/Res/haar_like_features.png"><img 
<img src="https://github.com/yilmazvolkan/FaceDetector/blob/master/Res/haar_like_features.png" width="650" height="210"></a>
</p>

Furthermore, since these features are scaleble, to prevent variations of features, we shrink input images to detect features for faces. However, even this small pixel images the number of features is still huge. Thus, we need to focus on more important features. There comes Adaptive Boosting. It selects best complements of existing features. When existing features is weaker for some areas, this new feature is strong. Cascading method is also very important. It looks for top certain number of features and if one of them not present, it does not evaluate the rest. It helps speed up the process.

To goal is find all features to classify all faces and non-faces correctly. Using these steps, we can implement in Python with openCV library. The results are below. We can see in figure 1 the program detects faces with blue rectangle and eyes with green rectangle. Then, in figure 2, if person is smiling it detects and show it with red square whether he/she is happy or not.

<p align="center">
<a href = "https://github.com/yilmazvolkan/FaceDetector/blob/master/Res/results%20.png"><img 
<img src="https://github.com/yilmazvolkan/FaceDetector/blob/master/Res/results%20.png" width="640" height="210"></a>
</p>

## :beers: Contributers


<p align="left">
<a href = "https://github.com/yilmazvolkan"><img 
<img src="https://avatars2.githubusercontent.com/u/28186366?s=400&v=4" width="120" height="120"></a>
</p>
