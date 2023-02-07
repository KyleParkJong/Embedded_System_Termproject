# Embedded_System_Termproject
> Konkuk Univ. 3rd grade, Embedded System Term-project

> 건국대학교 3학년 2학기 임베디드시스템 텀프로젝트 (3인 1조, 박종혁, 고려욱, 정건희)

# 0. Key objectives of this Term-project
> _Raspberry Pi project using device driver and AI_

## > Evaluation Criteria
* number of device driver and electronic components used
* Trained AI model

## > References provided in class
* Device driver : <https://github.com/Johannes4Linux/Linux_Driver_Tutorial>
* Image labeling method : <https://github.com/heartexlabs/labelImg>
* Object detection API : <https://github.com/EdjeElectronics/TensorFlow-Lite-Object-Detection-on-Android-and-Raspberry-Pi>

# 1. Programming language & HW
* C, Python 
* Raspberry Pi, PiCam, dot matrix(8x8 LED matrix), push button(touch sensor)

# 2. Our idea
### A music recommendation system according to the user's exercise state.

### _NOTICE_
 + The implemented function in this project was __"only"__ Face recognition AI model and device driver controlling dot matrix, push button
 + Socket communication, collecting user's exercise data and music recommendating AI model was implemented by __Jung Kun-hee(정건희)__ on his own project.

# 3. Result

## Block diagram

<img src="/images/block_diagram.png" width="100%" height="100%" title="lqrd_result" alt="qrd_result"></img>

## Flow diagram

<img src="/images/flow_diagram.jpg" width="60%" height="60%" title="lqrd_result" alt="qrd_result"></img>

## Face recognition

### Reference API

<img src="/images/api.png" width="80%" height="80%" title="lqrd_result" alt="qrd_result"></img>

<https://github.com/EdjeElectronics/TensorFlow-Lite-Object-Detection-on-Android-and-Raspberry-Pi>

### Labeled 3000 images total (1000 images per class)

<img src="/images/labelimg.png" width="80%" height="80%" title="lqrd_result" alt="qrd_result"></img>

* pjh, krw, jgh  -> 3 classes (Our teammates)
* Augmented 40 images into 1000 images using Python (Randomly controlled brightness, saturation, contrast, flip and rotate)

### Used model : ssd-mobilenet-v2

<img src="/images/model.png" width="80%" height="80%" title="lqrd_result" alt="qrd_result"></img>

### Training parameters

<img src="/images/training_parameters.png" width="80%" height="80%" title="lqrd_result" alt="qrd_result"></img>

* step number : 8000
* batch size : 16

### Total loss

<img src="/images/total_loss.png" width="80%" height="80%" title="lqrd_result" alt="qrd_result"></img>

## Device driver
* Push button(touch sensor) : dot.c , dot_driver.c
* Dot matrix : touch.c , touch_driver.c
    + Reference 7-segment device driver code was applied to make dot matrix device driver

### Push button & Dot matrix
* When the button is pressed, face recognition starts.

<img src="/images/dot_matrix2.png" width="50%" height="50%" title="lqrd_result" alt="qrd_result"></img>

* When face is recognized, dot matrix shows the initial of the recognized person's name
* In this case, Park Jonghyuk was recognized and letter P was showed on dot matrix.

<img src="/images/face_recognize.png" width="40%" height="40%" title="lqrd_result" alt="qrd_result"></img>

<img src="/images/dot_matrix.png" width="40%" height="40%" title="lqrd_result" alt="qrd_result"></img>

# 4. Things to be repaired
* Recognize all the team members as Park Jonghyuk(pjh)
    + Have to use other API, not an object detection
    + There must be a class that represents a state of nothing.
    + Image labeling should be more accurate

# 5. What I learned
* Improved C programming, python skills 
* Understanding of device driver
* Usage of Raspberry Pi and Linux OS
* Methods of labeling images and training AI model
