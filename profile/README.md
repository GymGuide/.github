# SkinCheck.AI

SkinCheck.AI is an All-in-One Platform For Your Skincare Needs. This project was inspired by the fact that many teenagers in Indonesia have acne problems and limited access to information on how to solve their skin problems. We took the initiative to create a mobile app that can help any individual find out the condition of their facial skin and how to treat it. We plan to create an innovative way to find out the condition of faces, find the appropriate skin care products and the best way to handle them. We are using machine learning, cloud computing and mobile development to realise these products.

# Current Features

This was the early features that this applications have.

1. Authentication

   <img src="/profile/resource/authentication.png" height="500">

2. Browse for skincare products and tips

   <img src="/profile/resource/Home%20Skin%20Page.png" height="500">

3. Get skin condition prediction

   <img src="/profile/resource/Detail%20Skin%20Page-1.png" height="500">

4. Get skincare recommendation

   <img src="/profile/resource/Detail%20Skin%20Page.png" height="500">

# Technical Details

## SkinCheck.AI Android Applications

The mobile application is made starting with UI/UX designs and a little UX research, then implementing the design results using native Kotlin Android by utilizing supporting libraries such as Retrofit to interact with APIs, ViewModel to maintain stable live data, and Firebase Google Authentication to process user authentication.

**Flow Android**
![Flow Android](/profile/resource/flow_aplikasi_android.png)

## SkinCheck.AI Cloud Computing Platform

We have made a RestAPI server for our Skincheck.AI app using NestJS for our main server and FastAPI for machine learning model deployment. We deploy our backend services using Cloud Run, with the CI/CD pipeline using Cloud Build. We also utilize Google Cloud Storage for file storage, Google Cloud Pub/Sub for integrating our backend service, and Cloud SQL for our database server. We also successfully use cloud logging to debug our application.

The backend of for cloud computing is implemented using Google Cloud Platform. We use Cloud Run, Cloud Build, Google Cloud Storage, Google Cloud SQL, Google Cloud Pub/Sub, and Firebase Authentication.

**API Documentation :** https://documenter.getpostman.com/view/27702577/2s93sgXB56

**Cloud Architecture**

![Cloud Architecture](/profile/resource/cloud_architecture.png)

**Database Structure**

![Database Structure](/profile/resource/database_structure.png)

**List Repostory for Cloud Computing**

#### 1. [Api-Design-Specification](www.google.com) (Filled with API design using OAS 3.0)

We implemented this the initial API design for our projects using OAS 3.0

#### 2. [skincheckai-api](https://github.com/Capstone-Project-C23-PR485/skincheckai-api) (main backend API)

Implemented using NestJS Framework and Prisma ORM.

#### 3. Machine learning backend

There is three machine learning backend used in this project. Each of them is for their own models. The backend is implemented using FastAPI.

- [Cloud-Acne-Detection-Service](https://github.com/Capstone-Project-C23-PR485/Cloud-Acne-Detection-Service)
- [Cloud-Wrinkle-Detection-Service](https://github.com/Capstone-Project-C23-PR485/Cloud-Wrinkle-Detection-Service)
- [Cloud-Flek-Detection-Service](https://github.com/Capstone-Project-C23-PR485/Cloud-Flek-Detection-Service)

We also create some simple UI to get firebase-auth token for development purposes, it was a forked project. This was the url : https://firebase-auth-ui-b6zefxgbfa-as.a.run.app/

## SkinCheck.AI Machine Learning Platform

This repository contains the implementation of three machine learning models for predicting
different skin conditions, namely acne type, wrinkle detection, and flake detection. We
employed transfer learning and fine-tuning techniques using the MobileNetV2 architecture in
the TensorFlow framework. The models were trained on a custom dataset that was specifically
curated for these tasks.

### Skin Condition Prediction Models

#### Acne Type Prediction

The acne type prediction model utilizes deep learning techniques to classify images of skin
into different acne types. By training on a diverse set of images, the model can accurately
classify acne types, such as hormonal acne, comedonal acne, inflammatory acne, and cystic
acne. This model can assist dermatologists and skincare professionals in diagnosing and
treating various forms of acne.

#### Wrinkle Detection

The wrinkle detection model is designed to identify and localize wrinkles in facial images. By
leveraging the power of deep learning, this model can detect different types of wrinkles, such
as fine lines, crow's feet, and forehead wrinkles. It provides a useful tool for evaluating the
effectiveness of anti-aging treatments and skincare regimens.

#### Fleck Detection

The flake detection model aims to detect and analyze flaky skin conditions, such as dryness
and dandruff. By examining images of the skin surface, this model can identify areas with
flaking and provide insights into the severity of the condition. This information can aid skincare
professionals in recommending appropriate treatments and moisturizers for individuals with
flaky skin.

### Skincare Recommendation System

In addition to the skin condition prediction models, we have also developed a skincare
recommendation system. We created and preprocessed a comprehensive skincare product
dataset, which includes information about various skincare products. The dataset contains
details such as the brand, type of skincare, ingredients, suitability for different skin types, a
link to buy the product, and ratings.

Our skincare recommendation system leverages this dataset to generate personalized
skincare recommendations based on an individual's specific skin needs. By considering
factors such as skin type, concerns, and ingredient preferences, the system suggests suitable
skincare products that align with the user's requirements. This can simplify the process of
finding and selecting effective skincare products tailored to individual needs.

# Getting Started

### Mobile Development

To get started with the mobile development, you can start by installing Android Studio. Then cloning this [repository](https://github.com/Capstone-Project-C23-PR485/Mobile-Development.git) to your local machine.

### Cloud Computing

To get started to deploy the server, you need a way to deploy the applications. We defaulted to use Google Cloud Platform to deploy our server. We utilize Cloud Run, Cloud Build, Google Cloud Storage, Google Cloud SQL, Google Cloud Pub/Sub, and Firebase Authentication. The step to use is below:

1. Create a GCP Projects
2. Create Firebase Project and activate Firebase Authentication
3. Create a Cloud SQL Instance
4. Create a Cloud Storage Bucket
5. Clone, build, and deploy the code in this repository to cloud run
   - https://github.com/Capstone-Project-C23-PR485/skincheckai-api.git
6. Set up Pub/Sub topic
7. Clone, build, and deploy the machine-learning backend to Cloud Run
   - Acne : https://github.com/Capstone-Project-C23-PR485/Cloud-Acne-Detection-Service.git
   - Flek : https://github.com/Capstone-Project-C23-PR485/Cloud-Flek-Detection-Service.git
   - Wrinkle : https://github.com/Capstone-Project-C23-PR485/Cloud-Wrinkle-Detection-Service.git
8. Set up Pub/Sub subscription for each machine-learning backend
9. Update all environtment variable in the Cloud Run service

####

### Machine Learning

To get started with the skin condition prediction models and skincare recommendation system,
please follow the instructions below:

1. Clone this repository:
   - Acne:https://github.com/Capstone-Project-C23-PR485/Machine-Learning-Acne-TypeClassification.git
   - Wrinkle:https://github.com/Capstone-Project-C23-PR485/-Machine-Learning-WrinkleType-Classification.git
   - Flex:https://github.com/Capstone-Project-C23-PR485/Machine-Learning-Flex-TypeClassification.git
   - Product Recommendation:https://github.com/Capstone-Project-C23-PR485/ProductRecommendation-.git
2. Install the required dependencies:
   - pip install python
   - pip install keras
   - pip install tensorflow
3. Download the trained models and preprocessed datasets from the following links:
   - Acne Type Prediction Model : https://drive.google.com/file/d/19y_LSalTBaCA8pk_Y0pa9RqldsEVj_Bz/view?usp=share_link
   - Wrinkle Detection Model : https://drive.google.com/drive/folders/1Frk77G06bEWpdYkd7WNJ9tgl43ZkSeuS?us p=sharing
   - Flake Detection Model : https://drive.google.com/file/d/18U8fijJX2el8s1GtWN_ngr58swDyYOzm/view?usp=sh aring
4. Place the downloaded models in the appropriate directories.
5. Explore the Jupyter notebooks provided in the repository to understand how to use the models and generate skincare recommendations.
6. Follow the instructions within the notebooks to load the models, preprocess the data, and make predictions or generate skincare recommendations.

### Fine-tuning the Model

To fine-tune the model, the MobileNetV2 architecture pretrained on ImageNet is used as the
base model. Fine-tuning starts from the 100th layer onwards. Layers before the 100th layer
are frozen, while layers after the 100th layer are trainable.

### Custom Layers

Custom layers are added on top of the base model to adapt it for the specific task. The added layers include:

1. Global Average Pooling
2. Batch Normalization
3. Dropout
4. Dense (with ReLU activation)
5. Dense (with sigmoid activation, kernel regularizer l2)

### Training and Evaluation

The model is compiled using the Adam optimizer with a learning rate of 0.0001 and categorical
cross-entropy loss. The evaluation metric used is accuracy. The training process involves
feeding the preprocessed images to the model and updating the model's parameters based
on the computed loss.

### Pretrained Model

The base model, MobileNetV2, is pretrained on the ImageNet dataset. This pretrained model
provides a good starting point for transfer learning, as it has already learned general features
from a large-scale dataset.

### Contributing

We welcome contributions to enhance the skin condition prediction models and skincare
recommendation system. If you have any ideas, bug fixes, or improvements, feel free to open
an issue or submit a pull.
