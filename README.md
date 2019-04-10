# case-study-jingli18
`Keras`  
  
![image](https://github.com/ec500-software-engineering/case-study-jingli18/raw/master/images/keras.jpg)

[Official Documents of Keras can be found here.](https://keras.io/)  
[GitHub address of Keras](https://github.com/keras-team/keras)
# The Case study summary is in the 'Keras-case-study.docx'
# The DEMO file is 'KerasTry.py'
## DEMO requirments:
* Python 3.6
* Tensorflow-1.9
* Keras
* Opencv
* TQDM
## The DEMO testing results are in the /TestResult folder
## A tutorial of Keras can be found below:

[Click and study!](https://www.datacamp.com/community/tutorials/deep-learning-python?utm_source=adwords_ppc&utm_campaignid=1658343521&utm_adgroupid=63833880615&utm_device=c&utm_keyword=keras&utm_matchtype=p&utm_network=g&utm_adpostion=1t1&utm_creative=319519154322&utm_targetid=aud-299261629654:kwd-295071417107&utm_loc_interest_ms=&utm_loc_physical_ms=9001996&gclid=CjwKCAjwqLblBRBYEiwAV3pCJkyW1QJ0SQ2EzX-33mb-S8egkO0EvWZEMwPdIVmLUPI3Hoe7MiSMLhoCSD8QAvD_BwE)

# Technology and Platform used for development
### a.	What coding languages are used? Do you think the same languages would be used if the project was started today? What languages would you use for the project if starting it today?
Python.
I think it will be the same language if should be chosen again. 
I used python, too. 
In my opinion, the language choice is a perfect fit. First of all, the function it wants to realize is machine learning (or neural network), which is a bit complex and hard to handle. And python is such a simple and succinct language so that it will make the ML job much more easy to deal with.
*It is very easy to build a `complex nerual network`(just like the image below) by keras.
![image](https://github.com/ec500-software-engineering/case-study-jingli18/raw/master/images/NN.png)  

[*Hit me and learn more about Nural Netword*](https://en.wikipedia.org/wiki/Artificial_neural_network)

### b.	What build system is used (e.g. Bazel, CMake, Meson)? What build tools / environment are needed to build (e.g. does it require Visual Studio or just GCC or ?)
It just built in python. It can work well if you use Python 2.7-3.6. Just the same advantage with the last question----easy to use.
### c.	What frameworks / libraries are used in the project? At least one of these projects don’t use any external libraries or explicit threading, yet is noted for being the fastest in its category--in that case, what intrinsic language techniques is it using to get this speed. 
Keras used Tensorflow as the backup. It can also call help from Theano and CNTK. 
By those powerful frameworks and huge libraries, Keras can finish machine learning jobs well.

# Testing: describe unit/integration/module tests and the test framework
### a.	How are they ensuring the testing is meaningful? Do they have code coverage metrics for example?
They use the ‘coveragerc’ file to ensuring the testing quality.
### b.	What CI platform(s) are they using (e.g. Travis-CI, AppVeyor)?
Travis-CI.  
Test Contents: Dataset, Image Data Task, Tensorflow Integration, Keras Funcitonal, Backend, Engine, Layer, Legacy, Utils, Wrapper, Multiprocessing.
### c.	What computing platform combinations are tested on their CI? E.g. Windows 10, Cygwin, Linux, Mac, GCC, Clang
Windows 10, Linux, Mac.

# Software architecture
### a.	How would you add / edit functionality if you wanted to? How would one use this project from external projects, or is it only usable as a standalone program?
I need to install Tensorflow and Keras and other libraries it needed. Then I just write a python file to import those libs and build a CNN. It was built to be used at any external projects, conveniently.
### b.	What parts of the software are asynchronous (if any)?
In my opinion, Keras works as a data flow, linearly.
From the Model defining to tensor generating, to network building, to training. One by one.
### c.	Please make diagrams as appropriate for your explanation
  
![image](https://github.com/ec500-software-engineering/case-study-jingli18/raw/master/images/diagram.jpg)
  
### e.	What architectural patterns are used?
It is a combination of Pipe-filter pattern and Layered Pattern.
### f.	Does the project lean more towards object oriented or functional components
All the Keras does are Call Frameworks (TF of Theano of CNTK) and define some functions---- Activation function, loss function, callback function and so on. In my opinion it is more like functional components.
# Analyze two defects in the project
a.	Does the issue require an architecture change, or is it just adding a new function or?
b.	make a patch / pull request for the project to fix problem / add feature

# Demonstration application of the system
---------
## DEMO
1)	An object detection CNN based on Keras.
2)	Target objects---- Car and Truck.
3)	Target EX:
![image](https://github.com/ec500-software-engineering/case-study-jingli18/raw/master/images/truck.jpg)
![image](https://github.com/ec500-software-engineering/case-study-jingli18/raw/master/images/car.jpg)
  
4)	Importing to use Keras:  
```python
from keras.models import Sequential
from keras.layers import *
from keras.optimizers import *
from keras.callbacks import TensorBoard
```

5)	CNN building :  
* Convolutional layer building
```python
model = Sequential()

model.add(InputLayer(input_shape = [64, 64, 1]))
model.add(Conv2D(filters=32, kernel_size = 5, strides = 1, padding = 'same', activation = 'relu'))
model.add(MaxPool2D(pool_size = 5, padding = 'same'))
```
* Output layer building
```python
model.add(Dense(2, activation = 'softmax'))
optimizer = Adam(lr = 1e-3)
model.compile(optimizer = optimizer, loss = 'categorical_crossentropy', metrics = ['accuracy'])
```
6)	Model Graph: (Full image is in the /TestResult folder)  
![image](https://github.com/ec500-software-engineering/case-study-jingli18/raw/master/images/model.jpg)


7)	Testing result:  
![image](https://github.com/ec500-software-engineering/case-study-jingli18/raw/master/TestResult/Accuracy.png)

![image](https://github.com/ec500-software-engineering/case-study-jingli18/raw/master/TestResult/Loss.png)





