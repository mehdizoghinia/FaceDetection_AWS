
## Face Detection Model with AWS SageMaker Endpoint
This repository contains a face detection model built with TensorFlow. The model identifies faces within images, and the detected faces are enclosed in bounding boxes. The model is served through an AWS SageMaker endpoint which processes the image input and returns the predicted bounding boxes.

# Features
Face detection in images using TensorFlow.
AWS SageMaker endpoint for real-time face detection.
AWS Lambda function to handle image processing and prediction retrieval.
Website for user to upload images, made with TypeScript.
Bounding boxes are drawn on detected faces and the resulting images are saved to Amazon S3.
Deployment automation using Docker and GitHub Actions (see related repo: cv2LambdaFunction).

# Architecture
The project is structured as follows:

User Interface: A website made with TypeScript where users can upload images for face detection.
AWS Lambda: Upon image upload, an AWS Lambda function is triggered to process the image and retrieve predictions from the SageMaker endpoint.
AWS SageMaker Endpoint: The endpoint hosts the TensorFlow face detection model which returns bounding box predictions.
Amazon S3: The processed images with drawn bounding boxes are saved to an S3 bucket.

# Deployment
Deployment is automated using Docker and GitHub Actions. The automation scripts are maintained in a separate repository: https://github.com/mehdizoghinia/cv2LambdaFunction.

The Lambda function code and dependencies are packaged into a Docker container.
The Docker container is pushed to Amazon Elastic Container Registry (ECR).
The Lambda function is then deployed to AWS Lambda using the container image from ECR.

# Usage
Visit the website and upload an image for face detection.
The Lambda function processes the image, retrieves face detection predictions from the SageMaker endpoint, and draws bounding boxes around detected faces.
The processed image is saved to S3, and a link to the image in S3 is provided to the user.
