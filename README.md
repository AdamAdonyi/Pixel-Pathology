# Pixel Pathology: Machine Learning Meets Medical Imaging - Challenge of AI MSC PROGRAM - 2024WS
## Project Overview
This project explores the application of machine learning in medical imaging, specifically focusing on the classification of chest X-rays into four categories: Normal, COVID-19, Pneumonia, and Tuberculosis. While our ConvNeXt model achieved remarkable accuracy (>98%), we applied various explainability techniques (LIME, SHAP, and GradCAM) to determine whether the model is identifying genuine medical features or potential biases in the dataset.
## Dataset
The dataset was sourced from Kaggle (Chest X-ray Dataset - 4 Categories) and contains 7,132 chest X-ray images distributed across four categories:

1,583 Normal
4,273 Pneumonia
700 Tuberculosis
576 COVID-19

## Model
We trained a ConvNeXt Tiny model using PyTorch, achieving over 98% accuracy on the validation set. This high accuracy prompted us to investigate the basis of the classification decisions.
Explainability Techniques
This repository focuses on three key explainability methods:
## LIME (Local Interpretable Model-agnostic Explanations)
The LIME implementation:

Uses 'quickshift' segmentation algorithm to divide images into interpretable segments
Generates 500 perturbed samples per image to understand local behavior
Identifies the top features contributing to classification decisions
Visualizes segment-level importance with color-coded heatmaps

## SHAP (SHapley Additive exPlanations) - code is not shown

## GradCAM (Gradient-weighted Class Activation Mapping) - code is not shown

## Key Findings
Our explainability analysis revealed concerning patterns:

Most influential segments identified by LIME were often outside the body or focused on edges/external objects
SHAP highlighted shoulders and bone structures rather than lung tissue
GradCAM showed focus on upper torso, areas above shoulders/neck, and image edges
Limited focus on clinically relevant lung features across all methods

These findings suggest that our model may be learning from dataset biases (such as annotations, positioning, or image artifacts) rather than actual medical features relevant to the diseases.
Repository Structure

notebooks/: Contains Jupyter notebooks for LIME

presentation/: Project presentation slides

## How to Use

Run the notebooks to reproduce our results or apply the techniques to your own models


Contributors

Nina Kirchmayr
Georgi Georgiev
Adam Adonyi



Dataset provided by Kaggle user pritpal2873
ConvNeXt architecture by Facebook AI Research
