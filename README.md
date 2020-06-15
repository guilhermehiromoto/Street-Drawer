# Street-Drawer

Final project for SCC0251 - Image Processing


## Authors
11218959 - Guilherme Amaral Hiromoto<br/>
11218855 - Victor Rodrigues Russo<br/>
10892676 - Paulo Matana da Rocha<br/>


## Abstract

This project aims to detect road shapes in urban areas through the segmentation of roads in satellite images using the [Road and Building Detection Dataset](https://www.cs.toronto.edu/~vmnih/data/) and CNN's to train a model that generates maps with the road shapes.

## Example
![](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/example_pdi.png?raw=true)

## Partial Report

**Main Objective:** As specified in abstract, this project aims to detect road shapes in urban areas through the segmentation of roads in satellite images using the [Road and Building Detection Dataset](https://www.cs.toronto.edu/~vmnih/data/) and CNN's to train a model that generates maps with the road shapes.

**Input images:** Our input images (preprocessed) are specified in [this notebook](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/preprocessing.ipynb)

**Description of steps:** For this project we are using a model-based methodology for Image Segmentation. We used the Intersection-Over-Union metric to train our model, that metric consists of calculating an area of overlap between a predicted segmentation and the mask divided by the union area between a predicted segmentation and a mask.<br/>
https://towardsdatascience.com/metrics-to-evaluate-your-semantic-segmentation-model-6bcb99639aa2<br/>

U-net architeture used for the [model](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/training_model.ipynb) (early stages of development, just to generate an output):<br/>
https://towardsdatascience.com/understanding-semantic-segmentation-with-unet-6be4f42d4b47<br/>

**Initial code with first results:** [Preprocessing Data](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/preprocessing.ipynb) and [Model Definition](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/training_model.ipynb)

Preprocessed data:

![](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/preprocessed_images.png)

Initial Prediction:

![](https://github.com/guilhermehiromoto/Street-Drawer/blob/master/initial_predictions.png)
Observacoes: Devido ao dataset extremamente reduzido (somente 36 imagens para elaborar um esboco do projeto) e a arquitetura nada otimizada da CNN, os outputs gerados pelo modelo tem um resultado muito abaixo do esperado.

## References

[1] [Machine Learning for Aerial Image Labeling](https://www.cs.toronto.edu/~vmnih/docs/Mnih_Volodymyr_PhD_Thesis.pdf)
