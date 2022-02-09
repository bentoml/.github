# Deploy your ML models to production today!  [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=BentoML:%20The%20Unified%20Model%20Serving%20Framework%20&url=https://github.com/bentoml&via=bentomlai&hashtags=mlops,bentoml)


BentoML is an open platform that simplifies machine-learning model deployment and runs high-performance model serving at scale.

- [🍱 BentoML](https://github.com/bentoml/BentoML): The Unified Model Serving Framework
- [🦄️ Yatai](https://github.com/bentoml/Yatai): Model Deployment at scale on Kubernetes
- [🚀 bentoctl](https://github.com/bentoml/bentoctl): Fast model deployment on any cloud platform


👉 [Pop into our Slack community!](https://join.slack.bentoml.org) We're happy to help with any issue you face or even just to meet you and hear what you're working on 😄

### BentoML - The Unified Model Serving Framework

[🍱 BentoML repo](https://github.com/bentoml/BentoML) | [🎨 Gallery Projects](https://github.com/bentoml/gallery) | [📖 Documentation](http://docs.bentoml.org)

BentoML makes it easy to turn your ML models into prediction services that's easily deployable and high-performance. You can use it with any ML framework, incorporate business logic and pre/post-processing code with your model, automatically generate HTTP API Server and create Docker Image for production-grade deployment.

<details>
  <summary>Details</summary>

  #### Key Features:

  * Support **multiple ML frameworks** including PyTorch, TensorFlow, Scikit-Learn, XGBoost, and [many more](https://docs.bentoml.org/en/latest/frameworks/index.html)
  * Support **Adaptive Batching** which dynamically group inference requets into small batches in real-time for better performance
  * Build inference graph composed from **multiple models** or functions, and **execute them in parallel**
  * **Automatic Docker image** can be generated for production deployment
</details>

### Yatai - Model Dpeloyment at scale on Kubernetes

[🦄️ Yatai repo](https://github.com/bentoml/yatai) | [👩‍🚀 Administrator's Guide](https://github.com/bentoml/yatai/blob/main/docs/admin-guide.md) | [⎈ Helm Chart](https://github.com/bentoml/yatai-chart)

Yatai helps ML teams to deploy large scale model serving workloads on Kubernetes. It standarlizes BentoML deployment on Kubernetes,
provides UI for managing all your ML models and deployments in one place, and enables advanced GitOps and CI/CD workflow.

<details>
  <summary>Details</summary>
  
  * **Deployment Automation** - deploy Bentos as auto-scaling API endpoints on Kubernetes and easily rollout new versions
  * **Bento Registry** - manage all your team's Bentos and Models, backed by cloud blob storage(S3, MinIO)
  * **Observability** - monitoring dashboard helping users to identify model performance issues
  * **CI/CD** - flexible APIs for integrating with your training and CI/CD pipelines
  
  <img width="785" alt="yatai-overview-page" src="https://user-images.githubusercontent.com/489344/151455964-4fe30eb7-f000-43cc-8a5f-807ee450b8b6.png">

<details>
  <summary>See more product screenshots</summary>
  <img width="785" alt="yatai-deployment-creation" src="https://user-images.githubusercontent.com/489344/151456002-d4e9f84d-8a71-4bf9-bde7-f94a74abbf3f.png">
  <img width="785" alt="yatai-bento-repos" src="https://user-images.githubusercontent.com/489344/151456379-da255519-274d-41de-a1b9-a347be279230.png">
  <img width="785" alt="yatai-model-detail" src="https://user-images.githubusercontent.com/489344/151456021-360a6d6e-acb8-494b-9f6b-868ef9d13bce.png">
  <img width="785" alt="yatai-cluster-components" src="https://user-images.githubusercontent.com/489344/151456017-abf0c77a-ba8a-43e5-8949-901ef4a8074a.png">
  <img width="785" alt="yatai-deployment-details" src="https://user-images.githubusercontent.com/489344/151456024-151c275d-b33e-480e-be34-dadab5b01915.png">
  <img width="785" alt="yatai-activities" src="https://user-images.githubusercontent.com/489344/151456011-69c283bc-7382-4b30-bfbf-2686e2abdc0f.png">
</details>
</details>

### bentoctl - Fast model deployment on any cloud platform

[🚀 bentoctl repo](https://github.com/bentoml/bentoctl) | [📖 Documentation](https://github.com/bentoml/bentoctl/blob/main/docs/introduction.md)

`bentoctl` is a CLI tool for deploying your machine-learning models to any cloud platform and serving predictions via REST APIs. 
It is built on top of BentoML and makes it easy to bring any BentoML packaged model to production.

<details>
  <summary>Details</summary>
  
Supported platforms:
* [AWS EC2](https://github.com/bentoml/aws-ec2-deploy)
* [AWS Lambda](https://github.com/bentoml/aws-lambda-deploy)
* [AWS SageMaker](https://github.com/bentoml/aws-sagemaker-deploy)
* [Azure Functions](https://github.com/bentoml/azure-functions-deploy)
* [Azure Container Instances](https://github.com/bentoml/azure-container-instances-deploy)
* [Google Cloud Run](https://github.com/bentoml/google-cloud-run-deploy)
* [Google Compute Engine](https://github.com/bentoml/google-compute-engine-deploy)
* [Heroku](https://github.com/bentoml/heroku-deploy)

**Custom deploy target** is supported by creating your own bentoctl plugin from the [deployment operator template](https://github.com/bentoml/bentoctl-operator-template).
</details>

