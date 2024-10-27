
Object Detection with HOG, YOLO, and SSD


Three different object detection methods are demonstrated in this project: TensorFlow-implemented Histogram of Oriented Gradients (HOG), You Only Look Once (YOLO), and Single Shot MultiBox Detector (SSD).


HOG Object Detection


Initially, a grayscale image is loaded and then its features are visualized using the HOG descriptor. 


YOLO Object Detection


Configuration files, class labels, and YOLOv3 weights are downloaded. After preprocessing the image and loading the YOLO model, detection is done. The objects that are detected are surrounded by bounding boxes.


SSD Object Detection


The label map and SSD MobileNet V2 model are downloaded. Once the model has been loaded and the image has been transformed into a tensor, the detection process begins. Bounding box highlights are used to show objects that have been detected.


Results


The outcomes of each detection technique are shown using Matplotlib. This allows the methods to be compared side by side. Each image shows the original with bounding boxes around objects that were detected.


HOG Results: Indicates which features were removed in order to identify objects.


Results for YOLO: Provides real-time detection with a decent speed-accuracy ratio.


SSD Results: One-pass object analysis and quick detection are provided.


Conclusion


A graphic comparison of the traditional HOG method with the deep learning-based YOLO and SSD approaches concludes the project. The comparisons show the unique benefits of each method, and the project's image folder contains reference photos.
