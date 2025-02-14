# future-context-ST
This repository contains the works conducted for my bachelor thesis "The Role of Future Context Prediction in Low-Latency Speech Translation".

## Low-Latency Speech Translation
Low-latency speech translation, also known as simultaneous speech translation is a speech translation which occurs in real-time. The input is an audio in the source language and the output is a written text in the target language. To realise the low-latency ability, a method called "Incremental Decoding" is used. This method suggest segmentation of the input data into small fixed-size chunks. In each step, chunk-level inputs are given to the model incrementally and decoded by the model to generate a partial output. A certain part of this output is selected and committed not to be modified again. The next step's decoding is conditioned on the committed outputs so far. By using this method, the system does not wait for the whole sentence which reduces latency drastically. More deatiled information about the incremental decoding and different strategies to select committed outputs can be found in this [article](https://arxiv.org/abs/2005.11185).

## The Role of Future Context Prediction in Low-Latency Speech Translation
Even tough the method of incremental decoding improves the latency of the speech translation, it has several shortcomings. The system needs to wait for a specific number of chunks before starting the inference.
The reason for that is the lack of context in the early chunks of the input. Therefore starting the inference from very early chunk steps may result in unstable and incorrect predictions. However waiting for a specific number of chunk steps comed with a latency penalty. If the system does not wait for several steps to prevent increased latency, the inference quality may drop significantly.

In order to overcome this problem, one can make use of large language models which can predict the future context of a given incomplete sentence. If the future context of the input is predicted in earlier chunk steps, the system will obtain more context. This will not only enable the system to start the inference in earlier chunk steps thus improving latency, but also to increase the inference quality of system in early steps' partial outputs.

## References
[1] Yupeng Chang, Xu Wang, Jindong Wang, Yuan Wu, Linyi Yang, Kaijie Zhu, Hao Chen,
Xiaoyuan Yi, Cunxiang Wang, Yidong Wang, Wei Ye, Yue Zhang, Yi Chang, Philip S. Yu,
Qiang Yang and Xing Xie. ?A Survey on Evaluation of Large Language Models? in(2023):
url: https://arxiv.org/abs/2307.03109.

[2] Colin Cherry and George Foster. ?Thinking Slow About Latency Evaluation for Simultaneous
Translation Evaluation? in(2019): url: https://arxiv.org/abs/1906.00048.

[3] Kyunghyun Cho and Masha Esipova. ?Can Neural Machine Translation Do Simultaneous
Translation ?? in(2016): url: https://arxiv.org/abs/1606.02012.

[4] European Parlament Interpretation Directorate. ?Report on Remote Interpretation Test 22-25
Janaury 2001 Brussels? in(2001): url: https://www.europarl.europa.eu/interp/remote_
interpreting/ep_report1.pdf.

[5] Danni Liu, Gerasimos Spanakis and Jan Niehues. ?Low-Latency Sequence-to-Sequence Speech
Recognition and Translation by Partial Hypothesis Selection? in(2020): url: https://arxiv.
org/abs/2005.11185.

[6] Renze Lou, Kai Zhang and Wenpeng Yin. ?Large Language Model Instruction Following:
A Survey of Progresses and Challenges? in(2024): url: https : / / arxiv . org / html / 2303 .
10475v8.

[7] Mingbo Ma, Liang Huang, Hao Xiong, Renjie Zheng, Kaibo Liu, Baigong Zheng, Chuanqiang
Zhang, Zhongjun He, Hairong Liu, Xing Li, Hua Wu and Haifeng Wang. ?STACL: Simultaneous
Translation with Implicit Anticipation and Controllable Latency using Prefix-to-Prefix Framework?
in(2019): url: https://aclanthology.org/P19-1289/.

[8] Xutai Ma, Mohammad Javad Dousti, Changhan Wang, Jiatao Gu and Juan Pino. ?SimulEval:
An Evaluation Toolkit for Simultaneous Translation? in(2020): url: https://arxiv.org/
abs/2007.16193.

[9] Jan Niehues, Thai Son Nguyen, Thanh Le Ha and Eunah Cho. ?Dynamic Transcription
for Low-Latency Speech Translation? in(2016): doi: http : / / dx . doi . org / 10 . 21437 /
Interspeech.2016- 154. url: https://www.researchgate.net/publication/307889273_
Dynamic_Transcription_for_Low-Latency_Speech_Translation.

[10] Jan Niehues, Ngoc-Quan Pham, Thanh-Le Ha, Matthias Sperber and Alex Waibel. ?Low-
Latency Neural Speech Translation? in(2018): url: https://arxiv.org/abs/1808.00491.

[11] Takaaki Saeki, Shinnosuke Takamichi and Hiroshi Saruwatari. ?Low-Latency Incremental
Text-to-Speech Synthesis with Distilled Context Prediction Network? in(2021): url: https:
//arxiv.org/abs/2109.10724v1.
