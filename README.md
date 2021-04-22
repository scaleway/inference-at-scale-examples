# AI Inference Examples

## Status : Early Access

The Scaleway AI Inference project is still under active development and should not be use for production. **In particular there is no SLA commitment at this stage, and the features/API could evolve without further notice**. Also keep in mind that AI Inference is built on top of Scaleway Serverless which is currently available in `Public Beta` (at the time of writing).

The goal of the Early Access is to provide a test access to the product, so you can contribute with your feedback as the product is being built! 

During the Access period, selected testers can create up to 10 inference endpoints (models).

The serverless resources provided during the early access stage are roughly equivalent to 1 vCPU and 2GB RAM per "worker". **These ressources are provided free of charge during the Early Access period**.

Currently AI Inference supports ONNX models and Tensorflow SavedModel (packaged in a ".tar.gz" archive)


## About AI Inference

Scaleway AI Inference provides clients with a flexible Machine Learning (ML) inference function which runs a trained model for clients on managed infrastructure and with built-in scalability.

Relying on a serverless architecture, we provide:
- an adapted runtime for your model to perform fast predictions
- on-demand billing that you pay only when predictions are made
- auto-scalability to handle as many requests as you send


## Scaleway Developer API documentation

See Scaleway AI [Inference API](https://developers.scaleway.com/en/products/inference/api/v1alpha1/)


## Content of this Repository

This repository provides 3 Jupyter Notebooks to learn how to use AI Inference:

- `1-AI-Inference-QuickStart.ipynb`: Discover AI Inference API with HTTP requests (curl)
- `2-AI-Inference-python-demo.ipynb`: A more comprehensive demo in Python (you may borrow some code snippets)
- `3-AI-Inference-convert-models-for-Inference.ipynb` : This notebook illustrates various ways to export your Pytorch or Tensorflow models into ONNX format

## Need Help ?

Should you have questions, difficulties, feature requests, feedback, please feel free to reach us in the [AI channel of the Scaleway Community slack](https://scaleway-community.slack.com/archives/C01SGLGRLEA)

Want to participate to the Early Access ? Claim your invitation to AI Inference via [this form](https://www.scaleway.com/en/betas/#inference)


## How to install ?

1- Create  a Python 3 environment and install Python requirements

Example for Ubuntu with Anaconda virtual environment:

```
apt-get update
apt-get install -y jq curl wget vim htop
conda create -n inference python=3.8.5
conda activate inference
pip install -q scikit-learn==0.24.1 numpy==1.18.5 pandas==1.2.3 boto3==1.17.33 ipython==7.18.1  jupyterlab==2.2.9 matplotlib==3.3.2
pip install -q torch==1.8.1+cpu torchvision==0.9.1+cpu torchaudio==0.8.1 -f https://download.pytorch.org/whl/torch_stable.html
pip install -q tensorflow==2.3.1 "h5py<2.11.0,>=2.10.0" "chardet<4.0,>=2.0"
pip install -q -U onnx==1.8.1 onnxconverter-common==1.7.0 onnxmltools==1.7.0 skl2onnx==1.7.0 tf2onnx==1.8.4 keras2onnx==1.7.0 onnxruntime==1.6.0

```

2- Git clone this repository into your Python environment


3- Define some environment variables with your credentials.

More information about [environment variables for Scaleway](https://github.com/scaleway/scaleway-sdk-go/tree/master/scw#environment-variables)
For a new secret key, click on the button "Generate new API Key" in the [console](https://console.scaleway.com/project/credentials)

```
export SCW_ACCESS_KEY="xxx"
export SCW_SECRET_KEY="xxx"
export SCW_DEFAULT_ORGANIZATION_ID="xxx"
export SCW_DEFAULT_PROJECT_ID="xxx"
export SCW_DEFAULT_REGION="fr-par"
export SCW_DEFAULT_ZONE="fr-par-1"
export SCW_API_URL="https://api.scaleway.com"

export SCW_ACCESS_KEY_S3=$SCW_ACCESS_KEY
export SCW_SECRET_KEY_S3=$SCW_SECRET_KEY

export S3_BUCKET_NAME="xxx"

```

 5- Launch `jupyter lab` and execute the notebooks

 6- Enjoy and give us some feedback in the [AI channel of the Scaleway Community slack](https://scaleway-community.slack.com/archives/C01SGLGRLEA)
