# Get your ML models into production today!

BentoML is an open-source platform that streamlines machine-learning model deployment and runs high-performance serving workload at scale.


- [🍱 BentoML](https://github.com/bentoml/BentoML): The Unified Model Serving Framework
- [🦄️ yatai](https://github.com/bentoml/yatai): Run BentoML workflow at scale on Kubernetes
- [🚀 bentoctl](https://github.com/bentoml/bentoctl): CLI tool for fast model deployment on cloud platforms


### BentoML - The Unified Model Serving Framework

[🍱 BentoML source](https://github.com/bentoml/BentoML) | [🎨 Gallery Projects](https://github.com/bentoml/gallery) | [📖 Documentation](http://docs.bentoml.org)


BentoML provides high-level APIs for packaging ML models and defining ML Services. From the ML service definition, BentoML allows building versioned archive(aka Bento) capturing all required dependencies, automatically generate HTTP Server and create Docker Image for production-grade deployment.

Key Features:
* Support **multiple ML frameworks** including PyTorch, TensorFlow, Scikit-Learn, XGBoost, and [many more](https://docs.bentoml.org/en/latest/frameworks/index.html)
* Support **Adaptive Batching** which dynamically group inference requets into small batches in real-time for better performance
* Build inference graph composed from **multiple models** and execute them in parallel
* **Automatic Docker image** can be generated for production deployment
* Automatically generate REST API spec in **Swagger/OpenAPI** format


### Yatai - MLOps on Kubernetes

[🦄️ Yatai source](https://github.com/bentoml/BentoML)

To be announced soon!


### bentoctl - CLI tool for fast model deployment on cloud platforms

[🚀 bentoctl source](https://github.com/bentoml/bentoctl)

`bentoctl` supports deploying ML Service created with BentoML into popular cloud services. Support for each cloud platform is captured in its own plugin that can be found below:

Supported platforms:
* AWS EC2: https://github.com/bentoml/aws-ec2-deploy
* AWS Lambda: https://github.com/bentoml/aws-lambda-deploy
* AWS SageMaker: https://github.com/bentoml/aws-sagemaker-deploy
* Azure Functions: https://github.com/bentoml/azure-functions-deploy
* Azure Container Instances https://github.com/bentoml/azure-container-instances-deploy
* Google Cloud Run: https://github.com/bentoml/google-cloud-run-deploy
* Google Compute Engine: https://github.com/bentoml/google-compute-engine-deploy
* Heroku: https://github.com/bentoml/heroku-deploy

Custom cloud platform is also supported by customizing deployment logic from the bentoctl operator tempalte:
* bentoctl deployment operator template: https://github.com/bentoml/bentoctl-operator-template
