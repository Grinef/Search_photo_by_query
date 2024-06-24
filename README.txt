# Image Search PoC for "With Sense" Photo Hosting

## Project Overview

You work for the professional photo hosting service "With Sense". Users upload their photos with detailed descriptions, which can also be added by other users. Your team is experimenting with a reference photo search for photographers. The goal is to allow users to input a scene description and retrieve matching photos. This project aims to develop a Proof of Concept (PoC) to demonstrate the feasibility of this idea.

## Project Steps

1. **Data Preparation**: 
   - Load and clean the dataset, ensuring compliance with legal restrictions by filtering out content involving minors.
   - The dataset consists of images and their descriptions, as well as crowd-sourced and expert annotations on the relevance of descriptions to images.

2. **Model Selection**:
   - Choose the best model that converts images and text descriptions into vector representations and outputs a similarity score between 0 and 1.

3. **Model Training and Evaluation**:
   - Train the model using the provided training data.
   - Evaluate the model using metrics such as accuracy and relevance based on crowd-sourced and expert annotations.

4. **Implementation**:
   - Develop a preliminary version of the product that can be presented to the company's management.
   - Ensure the model's output adheres to legal requirements by displaying a disclaimer for prohibited content.

## Data Description

- **train_dataset.csv**: Contains the image filename, description ID, and text description. Each image can have up to 5 descriptions. Description IDs follow the format `<image_filename>#<description_number>`.
- **train_images**: Directory containing images for model training.
- **CrowdAnnotations.tsv**: Contains crowd-sourced data on image-description relevance with columns for the image filename, description ID, the proportion of people who confirmed the relevance, the number of people who confirmed relevance, and the number of people who did not.
- **ExpertAnnotations.tsv**: Contains expert evaluations of image-description relevance with columns for the image filename, description ID, and ratings from three experts. Ratings range from 1 to 4, with 1 being completely irrelevant and 4 being fully relevant.
- **test_queries.csv**: Contains the test query ID, query text, and relevant image. Each image can have up to 5 descriptions. Description IDs follow the format `<image_filename>#<description_number>`.
- **test_images**: Directory containing images for model testing.

## Legal Restrictions

In some countries where "With Sense" operates, there are legal restrictions on processing images of minors. The service must comply by showing a disclaimer instead of the images. For the PoC, the dataset must be cleaned of such content, and any queries involving restricted content should display the disclaimer:

