# darkflow_applied

## Applications of Darkflow

This repo documents how my project team used [darkflow] (https://github.com/thtrieu/darkflow) to develop a real-time object detector / classifier for marine species and for dog breeds.

### Image Collection

Marine species images were provided by the Cal Poly Center for Coastal Marine Sciences.

Dog breed images were obtained from [Kaggle] (https://www.kaggle.com/c/dog-breed-identification) and further supplemented with Google Images using this [script] (https://github.com/markjay4k/YOLO-series/blob/master/part5%20-%20get_images.py).

### Bounding Boxes

Bounding boxes were drawn using this [script] (https://github.com/markjay4k/YOLO-series/blob/master/part6%20-%20draw_box_py36.py).
This creates an XML file for each image containing the coordinates of the bounding box.
Both the XML file and the corresponding image are needed as training inputs for the darkflow model.

### Model Training
