# Image Classification using AWS SageMaker

Use AWS Sagemaker to train a pretrained model that can perform image classification by using the Sagemaker profiling, debugger, hyperparameter tuning and other good ML engineering practices. This can be done on either the provided dog breed classication data set or one of your choice.

## Project Set Up and Installation
Enter AWS through the gateway in the course and open SageMaker Studio. 
Download the starter files.
Download/Make the dataset available. 

## Dataset
The provided dataset is the dogbreed classification dataset which can be found in the classroom.
The project is designed to be dataset independent so if there is a dataset that is more interesting or relevant to your work, you are welcome to use it to complete the project.

### Access
Upload the data to an S3 bucket through the AWS Gateway so that SageMaker has access to the data. 

## Hyperparameter Tuning
What kind of model did you choose for this experiment and why? Give an overview of the types of parameters and their ranges used for the hyperparameter search
For this experiment, I used ResNet18 model. Among other pre-trained models, ResNet(18) model is popularly used. It provides a fair balance between the model accuracy to the number of operations needed to excecute. Though ResNet18 model might tend to have a lower accuracy, It is comparably faster to train with than ResNet 50 completed training job

Remember that your README should:
- Include a screenshot of completed training jobs
- <img width="1099" alt="Training Jobs" src="https://user-images.githubusercontent.com/77801625/153280426-7e8a70f3-2c3e-45b1-8583-f2e096090f06.png">
- Logs metrics during the training process
- <img width="1431" alt="Training Logs" src="https://user-images.githubusercontent.com/77801625/153280506-0b7a9170-5dfa-40b6-af57-3f642d79f34c.png">
- Tune at least two hyperparameters
- <img width="1098" alt="Screenshot 2022-02-10 at 1 10 54 AM" src="https://user-images.githubusercontent.com/77801625/153280606-5e18e190-24d3-4616-a280-166db095c34e.png">
- Retrieve the best best hyperparameters from all your training jobs
- <img width="1078" alt="Screenshot 2022-02-10 at 1 31 03 AM" src="https://user-images.githubusercontent.com/77801625/153280803-76f6d237-8f21-4ea2-abe3-6b53647941c1.png">

## Debugging and Profiling
The training performance is checked by sagemaker debugger During your training job, the IOBottleneck rule was the most frequently triggered. It processed 476 datapoints and was triggered 0 times.

### Results
<img width="696" alt="Screenshot 2022-02-10 at 1 33 15 AM" src="https://user-images.githubusercontent.com/77801625/153281129-516b2d04-625f-411e-93ff-690bdf1f582b.png">
The CrossEntropyLoss_output tend to decrease during training which is good, no over fitting recorded


## Model Deployment
After successfully conducing a training job with the best hyperparameter available, I easily called for deployment with pytorch_model.deploy(). I also run a prediction on the endpoint. the result was seen by opening the payload image as seen in the train and deploy notebook above

<img width="1111" alt="Endpoint details" src="https://user-images.githubusercontent.com/77801625/153281298-c867ad0e-2e60-4223-8793-cb4a819906af.png">
