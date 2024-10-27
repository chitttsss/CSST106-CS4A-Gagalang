Performance Analysis


For real-time object detection, the YOLO (You Only Look Once) model stands out due to its exceptional speed and accuracy, particularly in scenarios that demand rapid, single-pass processing. YOLO's architecture, which detects and recognizes objects in a single forward pass through the network, enables it to consistently identify objects with high accuracy across various images, even when the number of objects varies. By bypassing the traditional region proposal steps seen in older models, YOLO achieves real-time processing rates.


By successfully detecting and labeling objects with confidence scores above a predetermined threshold, the model reduced false positives and maintained high object localization precision. However, occlusions, image quality, and object size are some of the variables that can affect accuracy.


In general, the design of YOLO works very well for real-time applications where speed is crucial, such as surveillance, autonomous driving, and video analysis, providing quick and accurate detections with little loss in accuracy. This is the reason YOLO was selected for my thesis, which is about the Android-Based Identification of Edible and Medicinal Wild Plants using Image Processing, since it offers a good balance between speed and accuracy, which is crucial for plant identification in real time.


