# Tool-Detection
This repository contain the codes for the paper titled **"Learning Latent Temporal Connectionism of Deep Residual Visual Abstractions for Identifying Surgical Tools in Laparoscopy Procedures"** accepted at Deep-Vision workshop, CVPR 2017.

**Abstract of the paper:** Surgical workflow in minimally invasive interventions like laparoscopy can be modeled with the aid of tool usage information. The video stream available during the surgery primarily for viewing the surgical site using endoscope can
be leveraged for this purpose without the need for additional sensors or instruments. We propose a method which learns to detect the tool presence in laparoscopy videos by leveraging the temporal connectionist information in a systematically executed surgical procedures by learning the long and short order relationships between higher abstractions of the spatial visual features extracted from the surgical video. We propose a framework consisting of using Convolutional Neural Networks for extracting the visual features and Long Short Term Memory network to encode the temporal information. The proposed framework has been experimentally verified using a publicly available dataset consisting of 10 training and 5 testing annotated videos with an average accuracy of 88.75% in detecting the tools present.
The code for surgical **phase identification** is also included. The mode must be set as 2 for phase identification in the script finetune.lua

**Description of codes**
  1. Training data for CNN: 4-D tensor (nSamples x nChannels x width x height), Training label: 2-D tensor (nSamples x nClasses)
  2. finetune.lua : Finetunes the CNN for tool detection or phase identification
  3. test.lua : Evaluates the performance of CNN
  4. trainLSTM : Trains a deep LSTM network for tool detection or phase identification
  5. testLSTM : Evaluates peformance of LSTM
  6. lstmTrainGen : Dataprepration for training LSTM. The training data is a 3D tensor (SequenceLength x Batchsize x featureSize)
  
**Pretrained models**
  Pretrained models are downloaded from the link(https://github.com/BVLC/caffe/wiki/Model-Zoo). The loadcaffe library is used to convert the caffe models into torch models.
  
**Dataset used**
The networks were trained on the m2ccai16-tool and workflow dataset(http://camma.u-strasbg.fr/datasets).
