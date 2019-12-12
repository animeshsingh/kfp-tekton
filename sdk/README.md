# Compiler for Tekton

As we know, there is an SDK of `Kubeflow Pipeline` for end users to define pipelines for Machine Learning(ML). The output of the compiler from SDK is the yaml for [Argo](https://github.com/argoproj/argo).

In its place, we have created an intial prototype to have the `Compiler` of SDK to generate `Tekton` yaml for a sequential pipeline scenario. 

## Development Prerequisites
1. [`Python`](https://www.python.org/downloads/): Python 3.5 or later  
2. [`Conda`](https://docs.conda.io/en/latest/): Package, dependency and environment management for Python


## Steps

1. Setup Python env with Conda.

2. Clone the [Kubeflow Pipelines](https://github.com/kubeflow/pipelines)  

    `git clone https://github.com/kubeflow/pipelines`  
    `git checkout 0548e63f96d91c03bc213e0affaac7dfcd088c83`  

3. Copy `sdk/...` to overwrite related path in `Kubeflow Pipelines`

4. Build the SDK

    - `cd $GOPATH`/src/github.com/kubeflow/pipelines/sdk/python  
    - `./build.sh`  
    - `pip install kfp.tar.gz`  

5. Complier a sample

    - `cd sdk/samples`  
    - `dsl-compile --py ./sequential.py --output sequential.tar.gz`


## Description

For now, it's a prototype change to the original Compiler only  to support `Sequential` case. We will be evolving this as we move along






