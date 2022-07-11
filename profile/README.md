# Welcome to BentoML 👋  [![Twitter Follow](https://img.shields.io/twitter/follow/bentomlai?style=social)](https://twitter.com/bentomlai) [![Slack](https://img.shields.io/badge/Slack-Join-4A154B?style=social)](https://l.linklyhq.com/l/ktO8)

[![BentoML](https://user-images.githubusercontent.com/489344/178160978-6e13a849-d16a-43b4-9ada-ef30f35922fa.png)](http://bentoml.com)

[Website](http://bentoml.com) | [Docs](https://docs.bentoml.org) | [Blog](https://modelserving.com) | [Twitter](https://twitter.com/bentomlai) | [Community](https://l.linklyhq.com/l/ktO8)


## What we are building 👩‍🍳

BentoML is an open source platform for machine learning in production. It simplifies model packaging and model management, optimizes model serving workloads to run at production scale, and accelerates the creation, deployment, and monitoring of prediction services.

- [🍱 BentoML](https://github.com/bentoml/BentoML): The Unified Model Serving Framework
- [🦄️ Yatai](https://github.com/bentoml/Yatai): Model Deployment at scale on Kubernetes
- [🚀 bentoctl](https://github.com/bentoml/bentoctl): Fast model deployment on any cloud platform

## Get in touch 💬

BentoML has a thriving open source community where hundreds of ML practitioners are contributing to the project, helping other users and discuss all things MLOps. [👉 Join us on slack today!](https://l.linklyhq.com/l/ktO8)

## Open Source Projects 👩🏽‍💻

### 🍱 BentoML

[Tutorial](https://docs.bentoml.org/en/latest/tutorial.html) | [Documentation](http://docs.bentoml.org) | [Examples Gallery](https://github.com/bentoml/gallery)

BentoML makes it easy to turn your ML models into prediction services that's easily deployable. You can use it with any ML framework, incorporate business logic and pre/post-processing code with your model, serve real-time via REST API endpoint or offline via batch inference job, and automatically generate Docker container image for production deployment.

<details>
  <summary>Learn More</summary>
  
  #### Key Features:

  * Support **multiple ML frameworks** including PyTorch, TensorFlow, Scikit-Learn, XGBoost, and [many more](https://docs.bentoml.org/en/latest/frameworks/index.html)
  * Support **Adaptive Batching** which dynamically group inference requets into small batches in real-time for better performance
  * Build inference graph composed from **multiple models** or functions, and **execute them in parallel**
  * **Automatic Docker image** can be generated for production deployment
  
  #### How it works:
  
  1. Use BentoML to save your trained model:
  ```python
  import bentoml
  bentoml.pytorch.save('mnist', trained_model)
  ```

  2. Create a ML Service:
  ```python
  # mnist_service.py
  import bentoml
  from bentoml.io import Image, NumpyNdarray
  
  mnist_runner = bentoml.pytorch.load_runner("mnist")

  svc = bentoml.Service("pytorch_mnist_demo", runners=[mnist_runner])

  @svc.api(input=Image(), output=NumpyNdarray(dtype="int64"))
  async def predict_image(f: PILImage) -> "np.ndarray[t.Any, np.dtype[t.Any]]":
    arr = np.array(f)/255.0
    arr = np.expand_dims(arr, 0).astype("float32")
    output_tensor = await mnist_runner.async_run(arr)
    return output_tensor.numpy()
  ```
  
  3. Run a model server locally to test out the API endpoint:
  ```bash
  bentoml serve mnist_service.py:svc --reload
  ```
  
  4. Checkout the [Quickstart Guide](https://l.linklyhq.com/l/ktIk) to learn more！
  
  
</details>


### 🦄️ Yatai

[Tutorial](https://github.com/bentoml/Yatai#getting-started) | [Installation](https://github.com/bentoml/yatai/blob/main/docs/admin-guide.md) | [Helm Chart](https://github.com/bentoml/yatai-chart)

Yatai helps ML teams to deploy large scale model serving workloads on Kubernetes. It standarlizes BentoML deployment on Kubernetes,
provides UI for managing all your ML models and deployments in one place, and enables advanced GitOps and CI/CD workflow.

<details>
  <summary>Learn More</summary>
  
  #### Key Features:

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

### 🚀 bentoctl

[Quickstart](https://github.com/bentoml/bentoctl/blob/main/docs/quickstart.md) | [Documentation](https://github.com/bentoml/bentoctl/blob/main/docs/introduction.md)

`bentoctl` is a CLI tool for deploying your machine-learning models to any cloud platform and serving predictions via REST APIs. 
It is built on top of BentoML and makes it easy to bring any BentoML packaged model to production.

<details>
  <summary>Learn More</summary>
    
  #### Supported platforms:
  
  * [AWS EC2](https://github.com/bentoml/aws-ec2-deploy)
  * [AWS Lambda](https://github.com/bentoml/aws-lambda-deploy)
  * [AWS SageMaker](https://github.com/bentoml/aws-sagemaker-deploy)
  * [Azure Functions](https://github.com/bentoml/azure-functions-deploy)
  * [Azure Container Instances](https://github.com/bentoml/azure-container-instances-deploy)
  * [Google Cloud Run](https://github.com/bentoml/google-cloud-run-deploy)
  * [Google Compute Engine](https://github.com/bentoml/google-compute-engine-deploy)
  * [Heroku](https://github.com/bentoml/heroku-deploy)
  * [Knative](https://github.com/bentoml/bentoctl/issues/79) (WIP)
  * Looking for **Kubernetes**? Try out [Yatai: Model deployment at scale on Kubernetes](https://github.com/bentoml/Yatai).
  * **Customize deploy target** by creating bentoctl plugin from the [deployment operator template](https://github.com/bentoml/bentoctl-operator-template).

</details>

