# darkflow_applied

## Applications of Darkflow

This repo documents how my project team used [darkflow](https://github.com/thtrieu/darkflow) to develop a real-time object detector / classifier for marine species and for dog breeds.

### Image Collection

Marine species images were provided by the Cal Poly Center for Coastal Marine Sciences.
About TBD images were collected for each species.

Dog breed images were obtained from [Kaggle](https://www.kaggle.com/c/dog-breed-identification) and further supplemented with Google Images using this [script](https://github.com/markjay4k/YOLO-series/blob/master/part5%20-%20get_images.py).  About TBD images were collected for each species.

### Image Preprocessing

The marine species images were reduced to size 400 x 300.
The dog breed images were not resized, as most images were less than 400 x 300.

### Bounding Boxes

Bounding boxes were drawn using this [script](https://github.com/markjay4k/YOLO-series/blob/master/part6%20-%20draw_box_py36.py).
This creates an XML file for each image containing the coordinates of the bounding box.
Both the XML file and the corresponding image are needed as training inputs for the darkflow model.

### Model Training
Our model configuration for both applications was tiny yolo.  The weights were obtained from this [site](https://pjreddie.com/darknet/yolo/), as suggested in the darkflow repo.  

The marine species classifier included 5 classes, while two versions of the dog breed classifier were developed -- one with 5 classes, and the other with 10 classes.

All models were trained using a single GPU -- Nvidia GeForce GTX 980.

The marine species classifier was trained up to 20,000 steps over 2-3 days.
The dog breed classifier was trained up to 24,000 steps also over 2-3 days.

Note: The model "broke" after 24,000 steps as the loss would change from ~1.2 to NAN.
Models configurations should be saved at regular intervals to ensure a working model is available.
It is unclear why the model "breaks" in this manner.

### Model Usage
As described in the darkflow repo, the model may be used for live object detection / classification or with pre-recorded video.
In both instances, a threshold of 10% was used.

### Results
Here is an example of the live object detection / classification for marine species

Here is an example of pre-recorded video for marine species

Here is an example of pre-recorded video for dog breed

### Analysis
The marine species model demonstrated better performance, as the training images and video images were very similar.  In addition, the five marine species 

### Future Work
- More species
- More training images per species
- Figure out why model "breaks"
- Experiment with other yolo configurations



