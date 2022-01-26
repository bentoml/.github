# Get your ML models into production today!  [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=BentoML:%20The%20Unified%20Model%20Serving%20Framework%20&url=https://github.com/bentoml&via=bentomlai&hashtags=mlops,bentoml)


BentoML is an open-source platform that streamlines machine-learning model deployment and runs high-performance serving workload at scale.

- [🍱 BentoML](https://github.com/bentoml/BentoML): The Unified Model Serving Framework
- [🦄️ Yatai](https://github.com/bentoml/Yatai): Run BentoML workflow at scale on Kubernetes
- [🚀 bentoctl](https://github.com/bentoml/bentoctl): Fast model deployment with BentoML on cloud platforms

Join us in our [community Slack](https://join.slack.com/t/bentoml/shared_invite/enQtNjcyMTY3MjE4NTgzLTU3ZDc1MWM5MzQxMWQxMzJiNTc1MTJmMzYzMTYwMjQ0OGEwNDFmZDkzYWQxNzgxYWNhNjAxZjk4MzI4OGY1Yjg) to receive project updates and get involved with latest development.


### BentoML - The Unified Model Serving Framework

[🍱 BentoML repo](https://github.com/bentoml/BentoML) | [🎨 Gallery Projects](https://github.com/bentoml/gallery) | [📖 Documentation](http://docs.bentoml.org)


BentoML provides high-level APIs for packaging ML models and defining ML Services. From the ML service definition, BentoML allows building versioned archive(aka Bento) capturing all required dependencies, automatically generate HTTP Server and create Docker Image for production-grade deployment.

Key Features:
* Support **multiple ML frameworks** including PyTorch, TensorFlow, Scikit-Learn, XGBoost, and [many more](https://docs.bentoml.org/en/latest/frameworks/index.html)
* Support **Adaptive Batching** which dynamically group inference requets into small batches in real-time for better performance
* Build inference graph composed from **multiple models** and execute them in parallel
* **Automatic Docker image** can be generated for production deployment
* Automatically generate REST API spec in **Swagger/OpenAPI** format


### Yatai - MLOps on Kubernetes

[🦄️ Yatai repo](https://github.com/bentoml/yatai) | [👩‍🚀 Administrator's Guide](https://github.com/bentoml/yatai/blob/main/docs/sys-admin-guide.md) | [⎈ Helm Chart](https://github.com/bentoml/yatai-chart)

Yatai helps ML teams to run BentoML at scale on Kubernetes. It makes it easy for teams to manage all their ML assets in one place and operate large scale model serving workloads on Kubernetes.

* **Bento Registry** - manage all your team's Bentos and Models, backed by cloud blob storage(S3, MinIO)
* **Deployment Automation** - deploy Bentos as auto-scaling API endpoints on Kubernetes and easily rollout new versions
* **Observability** - monitoring dashboard helping users to identify model performance issues
* **CI/CD** - flexible APIs for integrating with your training and CI pipelines


### bentoctl - Fast model deployment with BentoML on cloud platforms

[🚀 bentoctl repo](https://github.com/bentoml/bentoctl)

bentoctl is a CLI tool for deploying your BentoML packaged ML models as API endpoint on popular cloud platforms. It automates Bento docker image build, interactes with cloud platform APIs, and allow users to easily manage their deployment.

Supported platforms:
* [AWS EC2](https://github.com/bentoml/aws-ec2-deploy)
* [AWS Lambda](https://github.com/bentoml/aws-lambda-deploy)
* [AWS SageMaker](https://github.com/bentoml/aws-sagemaker-deploy)
* [Azure Functions](https://github.com/bentoml/azure-functions-deploy)
* [Azure Container Instances](https://github.com/bentoml/azure-container-instances-deploy)
* [Google Cloud Run](https://github.com/bentoml/google-cloud-run-deploy)
* [Google Compute Engine](https://github.com/bentoml/google-compute-engine-deploy)
* [Heroku](https://github.com/bentoml/heroku-deploy)

**Custom deploy target** is also supported by building your own bentoctl plugin from the [deployment operator template](https://github.com/bentoml/bentoctl-operator-template).
