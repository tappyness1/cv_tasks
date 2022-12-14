1. [Images](#images)
2. [EDA](#eda)
3. [Annotations](#annotations)

## Images

1. Check on the format of the images

- Image Size
- Image file format

2. Reading in images

There are currently two main packages for reading in images to your scripts- Pillow and OpenCV  

Pillow is the more straightforward of the two. This is because we normally associate images with RGB colours and the colour intensity is [0 - 255].  

OpenCV (or cv2) reads in images to BGR and the colour intensity range is [0-1]. Additionally, OpenCV tends to be harder to be packaged in environment files and docker. 

The main reason why inference goes wrong is because people tend to mix the two. From surveying the current tensor libraries, they tend to use OpenCV to open the image files. Thus, do use this guide for which image library to use:

1. EDA - OpenCV or Pillow
2. Inference pipeline - OpenCV
3. Training Pipeline - OpenCV

## EDA  

EDA for computer vision tasks is slightly different from tabular data. 

A good resource for EDA: [Fashion](https://www.kaggle.com/code/shivamb/imaterialist-fashion-eda-object-detection-colors/notebook)

These are some of the EDA tasks to follow:

### Images
1. What is the number of images? Is this the number of images promised to be delivered to us?
1. What is the format of images eg JPG/PNG/JPEG? 

### Colour
1. Colour Distribution per channel - What is the distribution of the colour in each channel? Is it normally distributed or multimodal? The goal is to see if there is a need to equalise the colour contrast.
1. You can try performing PCA or ISOMAP per channel to see how the images are related to each other.

### Annotations
1. How many instances of each classes have we got?
1. Bounding Box - what is Width and Height Distribution overall and per class?
1. Bounding Box - what is the overall size (W*H) overall and per class?
1. Bounding Box - Run a KMeans clustering on the Width and Height clusters?
1. Segmentation - what is distribution of the mask pixel counts overall and per class?

## Annotations

### Bounding Boxes Formats

1. COCO - [x_min, y_min, width, height]
1. YOLO - [x_center, y_center, width, height]
1. Pascal VOC - [x_min, y_min, x_max, y_max]

Just be aware that these formats exist, and you'll need to manipulate them where necessary. 

For example, if the sponsor gives the format in Pascal VOC, and we are running YOLOv3, we will need to convert to YOLO format for training and then convert for COCO format for the pycocotools for evaluating models. 

An example for during inference: Read images using CV2, run YOLOv3 model, convert then return in the desired format according to what the sponsor wants

### Bounding Box Random Sample Checks

1. Are the boxes drawn tight enough? 
1. Are the objects being occluded?
1. Are the objects truncated?

### Masks

Masks are less confusing than bounding boxes because the annotations would give you the pixel-wise position of the mask.

Masks are provided in an array of x-y pairs. It will typically be:

```
masks_per_instance = [x_1, y_1, x_2, y_2, ... x_n, y_n]
```

Thus, when reading this, you can choose to distangle it by doing two list comprehensions

```
x_per_instance = [masks_per_instance[i] for i in range(0,n*2,2)]
y_per_insance = [masks_per_instance[i] for i in range(1,n*2,2)]
```

### Classes

Some models have 0-indexed, while some start from 1. 