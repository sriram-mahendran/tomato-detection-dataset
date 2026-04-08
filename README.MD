# Tomato Ripeness Detection Dataset

## Overview

This dataset is designed for training and evaluating computer vision models to detect and classify tomatoes based on their ripeness stages in real-world agricultural environments. It consists of annotated images of tomato plants captured directly from field conditions, ensuring natural variations in lighting, occlusion, and background complexity.

The primary goal of this dataset is to support object detection tasks where tomatoes are identified and categorized into distinct ripeness levels.

---

## Dataset Description

The dataset contains images collected from two different farm locations:

* **Farm 1**: 25 images
* **Farm 2**: 15 images

Each image includes one or more tomatoes growing on plants in natural field conditions. The dataset reflects real agricultural scenarios, including:

* Varying illumination (sunlight, shadows)
* Partial occlusion by leaves and stems
* Different camera angles and distances
* Natural background noise (soil, sky, other plants)

---

## Annotation Format

All annotations are provided in **YOLO format**, which is widely used for object detection tasks.

Each image has a corresponding `.txt` file containing annotations in the following format:

```
<class_id> <x_center> <y_center> <width> <height>
```

Where:

* `class_id` → Integer representing the class label
* `x_center`, `y_center` → Normalized center coordinates of the bounding box
* `width`, `height` → Normalized width and height of the bounding box

All values are normalized between `0` and `1` relative to the image dimensions.

---

## Classes

The dataset includes **3 classes**, representing different stages of tomato ripeness:

```
nc: 3
names:
- b_green
- b_half_ripened
- b_fully_ripened
```

### Class Descriptions

* **b_green**
  Represents unripe tomatoes that are fully green in color. These tomatoes are not yet ready for harvest.

* **b_half_ripened**
  Represents tomatoes that are partially ripened, showing a mix of green and red/orange coloration. These are in the transition phase.

* **b_fully_ripened**
  Represents fully ripened tomatoes that are predominantly red and ready for harvest.

---

## Use Cases

This dataset can be used for:

* Training object detection models (e.g., YOLO, Faster R-CNN)
* Precision agriculture applications
* Automated harvesting systems
* Crop monitoring and yield estimation
* Ripeness classification research

---

## Dataset Structure

A typical dataset structure may look like:

```
Annotated/
│
├── farm1/
│   ├── images/
│   ├── labels/
│   ├── data.yaml
│
├── farm2/
│   ├── images/
│   ├── labels/
│   ├── data.yaml
```

Example `data.yaml` file:

```
train: path/to/train/images
val: path/to/val/images

nc: 3
names: ['b_green', 'b_half_ripened', 'b_fully_ripened']
```

---

## Notes

* The dataset is relatively small (40 images total), so data augmentation is recommended for training robust models.
* Suitable augmentation techniques include:

  * Horizontal/vertical flipping
  * Rotation
  * Brightness and contrast adjustments
  * Scaling and cropping

---

## Future Improvements

* Increasing dataset size with more diverse farm conditions
* Adding more ripeness stages or defect detection
* Including segmentation masks for instance segmentation tasks
* Capturing images under extreme weather conditions


---


This dataset was created to support research and development in smart agriculture and computer vision applications for crop monitoring.

---

