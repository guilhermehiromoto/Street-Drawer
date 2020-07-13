# Street-Drawer


Final project for SCC0251 - Image Processing

![](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/images/final_result.png?raw=true)

## Authors
11218959 - Guilherme Amaral Hiromoto<br/>
11218855 - Victor Rodrigues Russo<br/>
10892676 - Paulo Matana da Rocha<br/>


## Abstract

This project aims to detect road shapes in urban areas through the segmentation of roads in satellite images using the [Road and Building Detection Dataset](https://www.cs.toronto.edu/~vmnih/data/) and CNN's to train a model that generates maps with the road shapes.

## Example
![](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/images/example_pdi.png?raw=true)

## Final Report

<ins>**Main Objective:**</ins> As specified in abstract, this project aims to detect road shapes in urban areas through the segmentation of roads in satellite images using the [Road and Building Detection Dataset](https://www.cs.toronto.edu/~vmnih/data/) and CNN's to train a model that generates maps with the road shapes.

<ins>**Input images:**</ins> Our input images were obtained from the [Road and Building Detection Dataset](https://www.cs.toronto.edu/~vmnih/data/) using the [Scraping Maps](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/maps/getting_data.ipynb) notebook for the sattelite images and [Scraping Masks](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/masks/getting_data.ipynb) notebook for the masks. As our images had 1500x1500 dimensions we preprocessed then with [Preprocessing](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/notebooks/preprocessing.ipynb) notebook to fit in our U-net architecture (256x256).

#### Preprocessed data:

![](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/images/preprocessed_images.png)

<ins>**Description of steps:**</ins> For this project we are using a model-based methodology for Image Segmentation. We used the Intersection-Over-Union [[1]](https://towardsdatascience.com/metrics-to-evaluate-your-semantic-segmentation-model-6bcb99639aa2) method as metric to train our model, that method consists of calculating an area of overlap between a predicted segmentation and the mask divided by the union area between a predicted segmentation and a mask.<br/>

As loss function we used the binary cross entropy as we are dealing with a binary "classifier":
![](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/images/binary_cross_entropy.png?raw=true) [[2]](https://towardsdatascience.com/understanding-binary-cross-entropy-log-loss-a-visual-explanation-a3ac6025181a)

<br/>

For our CNN, we used the U-net architecture to train our [model](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/notebooks/training_model.ipynb):<br/>
This architecture is divided in two steps, first a **contraction path** that "downsample" the image with convolutions and maxpooling operations to **capture context in the image**, then a **expansion path** that upsample the image with transposed convolution used to **enable precise location**.
![](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/images/architeture.png?raw=true)
[[3]](https://towardsdatascience.com/understanding-semantic-segmentation-with-unet-6be4f42d4b47)<br/>

<ins>**Final Code with Results:**</ins><br/>
-[Getting Data: Maps](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/maps/getting_data.ipynb)<br/>
-[Getting Data: Masks](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/masks/getting_data.ipynb)<br/>
-[Preprocessing Data](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/notebooks/preprocessing.ipynb)<br/>
-[Model Training and Results](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/notebooks/training_model.ipynb)<br/>



<ins> **Demonstration Results**:</ins>
#### Prediction Comparation:
![](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/images/partial_prediction.png)<br/>

#### Cropped Inputs:
![](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/images/cropped_input.png)<br/>


#### Cropped Predictions:
![](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/images/cropped_result.png)<br/>

#### Final Result:
![](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/images/final_result.png)<br/>

## References

[1] [Intersection-Over-Union Metric](https://towardsdatascience.com/metrics-to-evaluate-your-semantic-segmentation-model-6bcb99639aa2)<br/>
[2] [Binary Cross Entropy Loss Function](https://towardsdatascience.com/understanding-binary-cross-entropy-log-loss-a-visual-explanation-a3ac6025181a)<br/>
[3] [U-net Architeture](https://towardsdatascience.com/understanding-semantic-segmentation-with-unet-6be4f42d4b47)<br/>
