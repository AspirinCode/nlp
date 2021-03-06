<p align="center">
    <br>
    <img src="https://raw.githubusercontent.com/huggingface/nlp/master/docs/source/imgs/nlp_logo_name.png" width="400"/>
    <br>
<p>
<p align="center">
    <a href="https://circleci.com/gh/huggingface/nlp">
        <img alt="Build" src="https://img.shields.io/circleci/build/github/huggingface/nlp/master">
    </a>
    <a href="https://github.com/huggingface/nlp/blob/master/LICENSE">
        <img alt="GitHub" src="https://img.shields.io/github/license/huggingface/nlp.svg?color=blue">
    </a>
    <!-- <a href="https://huggingface.co/nlp/index.html">
        <img alt="Documentation" src="https://img.shields.io/website/http/huggingface.co/nlp/index.html.svg?down_color=red&down_message=offline&up_message=online">
    </a> -->
    <a href="https://github.com/huggingface/nlp/releases">
        <img alt="GitHub release" src="https://img.shields.io/github/release/huggingface/nlp.svg">
    </a>
</p>

<h3 align="center">
<p> Datasets and Metrics for Natural Language Processing
<p> in PyTorch, TensorFlow 2.0, NumPy and Pandas,
</h3>

🤗 `nlp` is a lightweight and extensible library to easily share and access datasets and evaluation metrics for Natural Language Processing (NLP).

`nlp` has many interesting features (beside easy sharing and accessing datasets/metrics):

- Build-in interoperability with Numpy, Pandas, PyTorch and Tensorflow 2
- Lightweight and fast with a transparent and pythonic API
- Strive on large datasets: `nlp` naturally frees the user from RAM memory limitation, all datasets are memory-mapped on drive by default.
- Smart caching: never wait for your data to process several times

`nlp` currently provides access to ~100 NLP datasets and ~10 evaluation metrics and is designed to let the community easily add and share new datasets and evaluation metrics.

`nlp` originated from a fork of the awesome [`TensorFlow Datasets`](https://github.com/tensorflow/datasets) and the HuggingFace team want to deeply thank the TensorFlow Datasets team for building this amazing library and user API.

# Installation

## From PyPI

`nlp` can be installed from PyPi and has to be installed in a virtual environment (venv or conda for instance)

```bash
pip install nlp
```

## From source

You can also install `nlp` from source:
```bash
git clone https://github.com/huggingface/nlp
cd nlp
pip install .
```

When you update the repository, you should upgrade the nlp installation and its dependencies as follows:

```bash
git pull
pip install --upgrade .
```

## Using with PyTorch/TensorFlow/pandas

If you plan to use `nlp` with PyTorch (1.0+), TensorFlow (2.2+) or pandas, you should also install PyTorch, Tensorflow or pandas.

# Usage

Using `nlp` is made to be very simple to use, the main methods are:

- `nlp.list_datasets()` to list the available datasets
- `nlp.load_dataset(dataset_name, **kwargs)` to instantiate a dataset
- `nlp.list_metrics()` to list the available metrics
- `nlp.load_metric(metric_name, **kwargs)` to instantiate a metric

Here is a quick example:

```python
import nlp

# Print all the available datasets
print(dataset.id for dataset in nlp.list_datasets())

# Load a dataset and print the first examples in the training set
squad_dataset = nlp.load_dataset('squad')
print(squad_dataset['train'][0])

# List all the available metrics
print(metric.id for metric in nlp.list_metrics())

# Load a metric
squad_metric = nlp.load_metric('squad')
```

Now the best introduction to `nlp` is to follow the tutorial in Google Colab which is here:
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/huggingface/nlp/blob/master/notebooks/Overview.ipynb)

# Disclaimers

Similarly to Tensorflow Dataset, `nlp` is a utility library that downloads and prepares public datasets. We do not host or distribute these datasets, vouch for their quality or fairness, or claim that you have license to use the dataset. It is your responsibility to determine whether you have permission to use the dataset under the dataset's license.

If you're a dataset owner and wish to update any part of it (description, citation, etc.), or do not want your dataset to be included in this library, please get in touch through a GitHub issue. Thanks for your contribution to the ML community!

If you're interested in learning more about responsible AI practices, including fairness, please see Google AI's Responsible AI Practices.
