# future-context-ST
This repository contains the works conducted for my bachelor thesis "The Role of Future Context Prediction in Low-Latency Speech Translation".

## Low-Latency Speech Translation
Low-latency speech translation, also known as simultaneous speech translation is a speech translation which occurs in real-time. The input is an audio in the source language and the output is a written text in the target language. To realise the low-latency ability, a method called "Incremental Decoding" is used. This method suggest segmentation of the input data into small fixed-size chunks. In each step, chunk-level inputs are given to the model incrementally and decoded by the model to generate a partial output. A certain part of this output is selected and committed not to be modified again. The next step's decoding is conditioned on the committed outputs so far. By using this method, the system does not wait for the whole sentence which reduces latency drastically. More deatiled information about the incremental decoding and different strategies to select committed outputs can be found in this [article](https://arxiv.org/abs/2005.11185).

## The Role of Future Context Prediction in Low-Latency Speech Translation
Even tough the method of incremental decoding improves the latency of the speech translation, it has several shortcomings. The system needs to wait for a specific number of chunks before starting the inference.
The reason for that is the lack of context in the early chunks of the input. Therefore starting the inference from very early chunk steps may result in unstable and incorrect predictions. However waiting for a specific number of chunk steps increases the latency of the system. 
