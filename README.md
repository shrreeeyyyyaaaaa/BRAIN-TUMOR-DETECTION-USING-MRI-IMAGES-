##**PROJECT:BRAIN TUMOR DETECTION USING MRI IMAGES**
**Abstract**
Brain tumors pose significant challenges in the medical field due to their complex nature and the critical impact they have on the central nervous system. Early detection of brain tumors is crucial for effective treatment and improved patient outcomes.it presents an overview of current methodologies used for brain tumor detection, including advanced imaging techniques, machine learning algorithms, and biomarker analysis. By integrating these approaches, we aim to enhance diagnostic accuracy and facilitate timely intervention. The use of artificial intelligence and deep learning models in analyzing MRI scans shows promise in distinguishing between tumor types and assessing tumor progression. Our findings highlight the importance of a multidisciplinary approach to brain tumor diagnosis and suggest directions for future research to improve detection methods further.

**Introduction**
Brain tumors are abnormal growths of cells within the brain and surrounding tissues, which can be either benign or malignant. Their incidence has been rising, making early detection and accurate diagnosis critical for improving patient prognosis and tailored therapeutic strategies. The symptoms exhibited by brain tumor patients are often nonspecific and can vary widely, leading to delays in diagnosis.

Traditionally, brain tumors have been diagnosed through a combination of physical examinations, neurological assessments, and imaging techniques such as magnetic resonance imaging (MRI) and computed tomography (CT) scans. Advances in imaging technologies have provided a wealth of detailed insights into brain anatomy, facilitating the identification of abnormal growths. However, despite these advancements, challenges remain in effectively distinguishing between tumor types, grades, and their response to treatment.

In recent years, there has been a growing interest in utilizing artificial intelligence and machine learning to enhance brain tumor detection. These technologies hold the potential to analyze large volumes of imaging data more efficiently than traditional methods, potentially leading to faster and more accurate diagnoses. Additionally, the exploration of molecular biomarkers has opened new avenues for understanding tumor biology and improving diagnostic precision.

**FLOWCHART OF PROJECT :**
![BRAIN TUMOR DETECTION USING MRI IMAGES _flowchart](https://github.com/user-attachments/assets/2367478b-2c80-4af0-abba-bfadfea5e42c)
**DATASET:** 
The dataset consists of MRI images categorized into tumor and non-tumor classes. The data is split into:
https://github.com/SartajBhuvaji/Brain-Tumor-Classification-DataSet/

Training Set (80%):Found 2500 images belonging to 4 classes

Testing Set (20%):Found 354 images belonging to 4 classes
This dataset appears to be a medical image dataset for brain tumor classification. The folder names indicate four categories:

**pituitary_tumor** – Images of brain scans showing pituitary tumors.
**no_tumor** – Images of normal brain scans without any tumor.
**meningioma_tumor** – Images of brain scans with meningioma tumors.
**glioma_tumor** – Images of brain scans with glioma tumors.
This dataset is likely used for training and testing machine learning models in medical image analysis, particularly for classifying different types of brain tumors using techniques

**DATA AUGMENTATION:**
To improve model robustness and prevent overfitting, data augmentation techniques were applied:

**Rotation**: Random rotations between -20 to 20 degrees.

**Flipping:** Horizontal flipping of images.

**Brightness Adjustments:** Varying image brightness using OpenCV.

**Noise Addition:** Applied Gaussian noise to simulate real-world conditions.
![image](https://github.com/user-attachments/assets/b69bb8aa-1904-4fb9-ab62-48a1b25bcf71)

**FEATURE EXTRACTION :**
using OpenCV 
**1. Edge Detection using Canny**
Edge detection is an important technique in image processing that helps identify and outline the boundaries of objects within an image. The Canny edge detection algorithm is widely used for its effectiveness and accuracy.

**The Canny detector works through several steps:**

**Noise Reduction:** It applies a Gaussian filter to smooth the image and reduce noise that may interfere with edge detection.
**Gradient Calculation:** The algorithm computes the intensity gradient of the image to find areas of rapid intensity change.
**Non-Maximum Suppression:** It refines the edge map by suppressing all points that are not considered to be edge points, ensuring that the output is a thin edge line.
**Double Thresholding:** It classifies the pixels into strong, weak, or non-relevant edges based on their gradient values.
**Edge Tracking by Hysteresis:** Finally, it connects edges based on the weak edges that are connected to strong edges.
In the context of brain tumor detection, Canny edge detection helps outline tumor boundaries, making it easier to segment the tumor from surrounding brain tissues, which is essential for accurate diagnosis.

**2. Histogram of Oriented Gradients (HOG)**
The Histogram of Oriented Gradients (HOG) is another powerful feature extraction technique used in image analysis, particularly for object detection. HOG descriptors capture the structure and shape of objects by counting occurrences of gradient orientation in localized portions of an image (i.e., in cells).

The main steps involved in computing HOG features are:

**Gradient Computation:** The image gradients are computed in both the x and y directions using derivative filters, like the Sobel operator.
**Cell Division:**The image is divided into small connected regions, called cells.
**Orientation Histograms**: For each cell, a histogram of gradient orientations is computed from the gradient magnitudes over the cell.
**Block Normalization:** To account for changes in illumination and contrast, the histograms of neighboring cells are combined into larger blocks and normalized.
HOG features are particularly useful for distinguishing between benign and malignant tumors due to their ability to capture gradient changes around the tumor contours, leading to improved classification performance.

**3. Gray Level Co-occurrence Matrix (GLCM) Texture Features**
The GLCM method is a statistical approach used to analyze the texture of an image. It considers the spatial relationship of pixels with specific gray levels. By constructing a co-occurrence matrix, the GLCM captures how often different combinations of pixel brightness values occur in a specified spatial relationship.

Key steps in GLCM feature extraction include:

**Matrix Construction:** For a given image, the GLCM is generated based on the relative positions of pixel pairs within specified distances and angles (e.g., horizontal, vertical, diagonal).
**Feature Calculation:** Several statistical measures can then be derived from the GLCM, including:
**Contrast:** Measures the local variations in the gray level intensities.
**Correlation:** Indicates how correlated the pixel values are to each other.
**Energy:** Represents the uniformity of the GLCM.
**Homogeneity:** Measures the closeness of the distribution of elements in the GLCM.
GLCM features are particularly effective in capturing the texture patterns of tumors, which can be critical in differentiating 

**MODEL**
**RESNET50**
![image](https://github.com/user-attachments/assets/815eef17-be9b-49d6-b33e-93e2c7cb16c5) 



