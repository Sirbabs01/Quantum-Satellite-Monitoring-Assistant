# Quantum vs Classical Satellite Monitoring Assistant
## Project Overview

Modern satellites continuously generate large volumes of data in two primary forms: imagery capturing the Earth’s surface and atmosphere, and telemetry describing the spacecraft’s internal operational state. These datasets differ significantly in structure and require different analytical techniques. Imagery analysis typically relies on pattern recognition methods, while telemetry analysis focuses on identifying trends and anomalies within time-series data.

Traditional machine learning approaches such as Convolutional Neural Networks (CNNs) and Support Vector Machines (SVMs) have been widely used to analyze these data types. However, the emergence of quantum machine learning has introduced new possibilities for designing models that may offer advantages in representation, computational efficiency, or anomaly detection.

This project explores the feasibility of quantum-inspired satellite monitoring systems by developing and benchmarking two parallel assistants:

### Quantum-Inspired Monitoring Assistant

#### Quantum Neural Network (QNN) for satellite imagery classification

#### Quantum Support Vector Machine (QSVM) for telemetry anomaly detection

### Classical Monitoring Assistant

#### Convolutional Neural Network (CNN) for satellite imagery classification

#### Classical Support Vector Machine (SVM) for telemetry anomaly detection

Both assistants will analyze satellite data streams and detect anomalies in spacecraft behavior. Their performance will be evaluated using real-world datasets as well as data generated from a simulated satellite environment.

The project ultimately investigates whether quantum machine learning algorithms can provide measurable advantages over classical approaches in satellite monitoring tasks.

## Project Aim

The aim of this project is to design, develop, and evaluate a quantum-inspired and classical satellite monitoring assistant capable of analyzing satellite imagery and telemetry data, and to investigate whether quantum machine learning models can provide advantages in pattern recognition, anomaly detection, and operational monitoring.

## Project Objectives

The objectives of this project are:

### Data Preparation

Collect and preprocess satellite imagery and telemetry datasets suitable for machine learning applications.

### Quantum Model Development

Develop a Quantum Neural Network (QNN) for satellite imagery classification.

Develop a Quantum Support Vector Machine (QSVM) for telemetry anomaly detection.

### Classical Model Development

Develop classical benchmark models:

CNN for imagery classification

Classical SVM for telemetry anomaly detection.

### Satellite Simulation

Create a simulated satellite environment capable of generating realistic streams of imagery and telemetry data, including controlled anomalies.

### Deployment

Integrate trained models into Streamlit-based monitoring interfaces capable of processing and visualizing incoming satellite data.

### Performance Evaluation

Compare quantum-inspired and classical assistants in terms of:

classification accuracy

anomaly detection capability

robustness to noise

operational responsiveness.

### Operational Demonstration

Demonstrate a functional satellite monitoring framework and assess the feasibility of applying quantum machine learning techniques to real-world satellite operations.

## Current Project Status

This repository currently contains the initial implementation of the quantum imagery classification pipeline.

The present work includes:

A Quantum Neural Network (QNN) architecture for satellite imagery classification.

Feature extraction using ResNet-based embeddings.

Principal Component Analysis (PCA) for dimensionality reduction.

Angular encoding of classical features into quantum states.

A quantum circuit implemented using 8 qubits.

Initial experiments using the EuroSAT RGB dataset achieved approximately 15% classification accuracy on a 10-class problem, highlighting current limitations of near-term quantum models.

These results suggest that model expressivity is strongly constrained by available qubit counts, raising important research questions regarding the feasibility of achieving quantum advantage with current hardware and algorithms.

Work is currently underway to extend the architecture to 16-qubit and 20-qubit QNN models in order to investigate whether increased representational capacity improves performance.

## Methodology Overview

The project follows a modular pipeline consisting of data acquisition, preprocessing, model development, deployment, and evaluation.

### 1. Data Acquisition

Satellite datasets are obtained from open-access sources including:

Landsat

Sentinel

EuroSAT

SpaceNet

UC Merced Land Use

BigEarthNet

Telemetry datasets are sourced from publicly available spacecraft datasets including ESA, NASA, and CubeSat missions.

### 2. Data Preprocessing
#### Imagery

Satellite images undergo the following steps:

resizing and normalization

feature extraction using deep CNN embeddings (ResNet)

dimensionality reduction using PCA

standardization

angular encoding into quantum circuits.

#### Telemetry

Telemetry streams are:

filtered

interpolated where necessary

normalized into structured numerical feature vectors.

### 3. Model Development

Two parallel machine learning pipelines are implemented.

#### Quantum Models

Quantum Neural Network (QNN) for imagery classification.

Quantum Support Vector Machine (QSVM) for telemetry anomaly detection.

##### Quantum models are implemented using:

PennyLane

Qiskit Machine Learning

#### Classical Models

Convolutional Neural Network (CNN) for imagery classification

Support Vector Machine (SVM) for telemetry anomaly detection

These models provide the baseline for evaluating the performance of quantum approaches.

### 4. Satellite Simulation

To evaluate the monitoring assistants under conditions similar to real satellite operations, a simulated satellite data stream will be developed. The goal of this simulation is not to fully reproduce a physical satellite system, but to emulate how satellite imagery and telemetry data might be received and processed by a monitoring interface.

The simulation will consist of two components: imagery streaming and telemetry streaming.

#### Imagery Simulation

Satellite imagery will be simulated by sequentially sampling images from labeled satellite imagery datasets such as EuroSAT RGB. These images will be passed to the monitoring system as if they were being received from a satellite sensor.

Basic image perturbations such as noise, blur, or brightness variations may be applied to represent sensor imperfections or environmental effects. This allows the monitoring assistant to process incoming imagery in a way that mimics real satellite observations.

#### Telemetry Simulation

Telemetry data streams will be simulated using generated time-series signals representing common spacecraft health parameters such as:

temperature

battery voltage

power levels

orientation or sensor readings

These signals will follow realistic trends during normal satellite operation. Controlled anomalies, such as sudden temperature spikes or power fluctuations, may be introduced to evaluate the ability of the monitoring models to detect abnormal spacecraft behavior.

### 5. Monitoring Interfaces

Two monitoring assistants will be deployed as interactive dashboards using the Streamlit framework—one implementing the quantum-inspired models and the other implementing the classical models.

Each interface will allow users to:

upload satellite imagery for classification

input or stream telemetry data for anomaly detection

visualize model predictions and confidence scores

monitor telemetry signals and highlight potential anomalies in real time

These dashboards will demonstrate how machine learning models can be integrated into practical tools for satellite data analysis and monitoring.

## Data Sources
### Satellite Imagery

EuroSAT RGB Dataset
https://zenodo.org/record/7711810

NASA Landsat
https://earthexplorer.usgs.gov/

ESA Sentinel-2
https://scihub.copernicus.eu/

SpaceNet Dataset
https://spacenet.ai/datasets/

UC Merced Land Use Dataset
http://weegee.vision.ucmerced.edu/datasets/landuse.html

BigEarthNet
https://bigearth.net/

Radiant MLHub
https://mlhub.earth/

### Telemetry Datasets

ESA Satellite Telemetry Anomaly Dataset
https://kelvins.esa.int/satellite-telemetry-anomaly-detection/

NASA Dashlink Telemetry Repository
https://c3.ndc.nasa.gov/dashlink/

SatNOGS Telemetry Archive
https://db.satnogs.org/

Delfi-C3 CubeSat Telemetry
https://delfispace.nl/delfi-c3/

NASA / Numenta Anomaly Benchmark
https://github.com/numenta/NAB

## Technology Stack
### Data Processing

NumPy

Pandas

SciPy

### Image Processing

OpenCV

Pillow

### Classical Machine Learning

scikit-learn

TensorFlow / PyTorch

### Quantum Machine Learning

PennyLane

Qiskit Machine Learning

Cirq (optional)

### Satellite Simulation

poliastro

skyfield

SimPy

asyncio

FastAPI

### Visualization

Matplotlib

Seaborn

Plotly

### Deployment

Streamlit

WebSockets

joblib

## Future Work

The project is currently under active development. Planned extensions include:

### Quantum Model Scaling

Implementation of 16-qubit and 20-qubit QNN architectures

Investigation of how model expressivity scales with qubit count.

### Hybrid Quantum Models

Development of Quantum Neural Network + Quantum SVM hybrid pipelines.

### Classical Benchmark Completion

Training of CNN models for imagery classification.

Training of classical SVM models for telemetry anomaly detection.

### Satellite Simulation

Implementation of a fully operational satellite simulation environment

Injection of realistic operational anomalies.

### Monitoring Dashboard Deployment

Deployment of quantum-inspired and classical monitoring assistants using Streamlit.

### Performance Benchmarking

Comprehensive evaluation comparing:

classification accuracy

anomaly detection precision

robustness to noisy telemetry

computational efficiency.

## Research Motivation

This project explores a fundamental question in quantum machine learning:

Can near-term quantum algorithms provide practical advantages for real-world data analysis tasks?

Satellite monitoring offers a challenging domain where large datasets, complex patterns, and anomaly detection requirements make it an ideal testbed for investigating the potential of quantum-inspired machine learning systems.
