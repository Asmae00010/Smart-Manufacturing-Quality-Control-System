Computer Vision Module
==================

Model Architecture
----------------
Our computer vision system utilizes ResNet-50 architecture for steel surface defect detection.

Model Selection
~~~~~~~~~~~~~
ResNet-50 was chosen after comprehensive benchmarking against other architectures, demonstrating superior performance in:

- Accuracy
- Inference speed
- Model size efficiency

Training Details
--------------
Dataset
~~~~~~~
- NEU surface defect database
- Six distinct defect classes
- Augmented with standard transformations

Performance
~~~~~~~~~~
The model demonstrated exceptional performance:

+ Achieved high accuracy on both training *(99.86%)* and validation *(100%)* sets.
+ Maintained low loss values, indicating strong optimization.
+ Generalized effectively to external datasets and unseen images.
+ Provided real-time inference with consistent efficiency.

Implementation
------------
The model is implemented using PyTorch and integrated into our Streamlit application for real-time defect detection.

