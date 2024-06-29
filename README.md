# Predicting Livestream Viewer Behavior from Chat Messages

## Table of Contents
- [Introduction](#introduction)
- [Project Structure](#project-structure)
- [Results](#Results)
- [Data](#data)
- 
- [Installation](#installation)
- [Usage](#usage)


- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Introduction

This project demonstrates how to implement behavioral prediction from language data through the implementation of a transformed neural network on embeddings generated from a BERT based large language model (LLM) to predict whether a livestream viewer will or will not donate. These models are implemeneted using a combination of pytorch (for the prediction network) and Huggingface's open source models for our LLM. All experiments are constructed in collab notebooks.

This project can be broken into 3 parts

**1.Data Collection**

Livestream data for a particular streamer is scrapped from youtube in two steps. First, urls of all livestreams is obtained from the channel, then these urls are used to scape chat data. This livestream chat data is stored in an SQlite3 database for future reference.

Code for this section can be found in 

**2.LLM Pre-training**

A fraction of the data is used to pre-train a BERT based LLM. A sampled set of streams is used to perform pre-training. Messages are concatenated together before training. Training effectiveness is tested by assessing perplexity over training and by looking at the decay of cosine distance between messages as a function of time.

Code for this section can be found in

**3.Behavioral Prediction**

The trained LLM is used to generate representations of each individual during a livestream. This is done by converting each message into an embedding using the encoder LLM, appending the the timestamp of the message and the total length of the stream to create a complete encoded message. Each encoding is aggregated together into a full tensor to generate a complete representation of each viewer's messages sent during a livestream. An encoder transformer with a learnable CLS is then trained to seperate donors from non-donors using a training-test data split.

Code for this section can be found in 

Below is a graphical outline illustrating each step of the process.





## Project Structure


## Results

When 

## Features
## Installation
## Usage


## Contributing
## License
## Contact
