
Training on MS COCO

# Mask_RCNN-for-Multiple-classess
# Train a new model starting from pre-trained COCO weights
python3 samples/coco/coco.py train --dataset=/path/to/coco/ --model=coco

# Train a new model starting from ImageNet weights
python3 samples/coco/coco.py train --dataset=/path/to/coco/ --model=imagenet

# Continue training a model that you had trained earlier
python3 samples/coco/coco.py train --dataset=/path/to/coco/ --model=/path/to/weights.h5

# Continue training the last model you trained. This will find
# the last trained weights in the model directory.
python3 samples/coco/coco.py train --dataset=/path/to/coco/ --model=last



Training on Your Own Dataset
In summary, to train the model on your own dataset you'll need to extend two classes or multiple classes:

Config This class contains the default configuration. Subclass it and modify the attributes you need to change.

Dataset This class provides a consistent way to work with any dataset. It allows you to use new datasets for training without having to change the code of the model. It also supports loading multiple datasets at the same time, which is useful if the objects you want to detect are not all available in one dataset.

See examples in samples/shapes/train_shapes.ipynb, samples/coco/coco.py, samples/balloon/balloon.py, and samples/nucleus/nucleus.py.

Requirements
Python 3.4, TensorFlow 1.3, Keras 2.0.8 and other common packages listed in requirements.txt.
MS COCO Requirements:
To train or test on MS COCO, you'll also need:
    • pycocotools (installation instructions below)
    • MS COCO Dataset
    • Download the 5K minivaland the 35K validation-minus-minival subsets. More details in the original Faster R-CNN implementation.

Installation
Clone this repository
    1. Install dependencies
       pip3 install -r requirements.txt
    2. Run setup from the repository root directory
       python3 setup.py install
    3. Download pre-trained COCO weights (mask_rcnn_coco.h5) from the releases page.
    4. (Optional) To train or test on MS COCO install pycocotools from one of these repos. They are forks of the original pycocotools with fixes for Python3 and Windows (the official repo doesn't seem to be active anymore).
        ◦ Linux:https://github.com/waleedka/coco
        ◦ Windows:https://github.com/philferriere/cocoapi. You must have the Visual C++ 2015 build tools on your path (see the repo for additional details)



Final results


