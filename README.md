# Interactive Image Segmentation with Latent Diversity
This is a Tensorflow implementation of Interactive Image Segmentation with Latent Diversity. It receives positive and negative clicks and produces segmentation masks.

## Examples



Raw Segmentation Mask            |  Segmentation Results (Overlay)
:-------------------------:|:-------------------------:
![Raw Segmentation Mask](res/83567032/Ours/00000/segs/009.png?  "Raw Segmentation Mask")  |   ![Segmentation Results (Overlay)](res/83567032/Ours/00000/tmps/ol_009.png? "Segmentation Results (Overlay)")

Distance Map for Positive Clicks            |  Distance Map for Negative Clicks
:-------------------------:|:-------------------------:
![Distance Map for Positive Clicks](res/83567032/Ours/00000/ints/pos_dt_001.png? "Distance Map for Positive Clicks")  |  ![Distance Map for Negative Clicks](res/83567032/Ours/00000/ints/pos_dt_004.png? "Distance Map for Negative Clicks")




## Setup

### Requirement
Required python libraries: Tensorflow (>=1.3) + OpenCV + Scipy + Numpy.

Tested in Ubuntu 16.04 LTS + Intel i7 CPU + Nvidia Titan X (Pascal) with Cuda (>=8.0) and CuDNN (>=6.0). 

### Quick Start
1. Clone this repository.
2. Download the pre-trained model from this [link](https://drive.google.com/open?id=1u96zu0VyNpy-1VL90EbriN74hGaBBK08). Unzip it and put them into the "Models" folder.
3. Run "UI_interactive_segmentation.py", and a window will show up.
4. Open an image (one sample image is provided in "imgs"); the image will show on the up-left.
5. Use the mouse to input positive (left) and/or negative (right) clicks.

The segmentation mask will show on the bottom-left, and the overlying image will show on the up-right. The bottom-right window can be ignored at this moment. The click inputs and segmentation results will be saved in the "res" folder under a random user id specified folder.

Note that the GUI is designed for demonstration only, and thus it is not optimized for images with arbitrary resolution.

### Training

The MATLAB script "genIntSegPairs.m" is provided for automatically generating positive/negative clicks. Note that the synthesizing strategies follow "Deep interactive object selection" ([arxiv link](https://arxiv.org/abs/1603.04042)).

With the generated positive/negative clicks, run "train_interactive_segmentation.py" to start training after the "im_path" and "seg_path" are properly set. 

The current implementation processes the SBD dataset ([link](http://home.bharathh.info/pubs/codes/SBD/download.html)), and it can be modified to process any dataset with image and intance mask pairs.

## License
MIT License
