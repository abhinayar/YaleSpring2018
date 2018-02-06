Class 1

01/23/2018

Deep Learning

—

What is Deep Learning?

- --Deep learning is a subset of Machine learning which is a subset of AI
- --Deep learning is a hot topic lately
- --Recently there has been a lot of success in deep learning methods
  - --Object classification
  - --Segmentation
  - --Shakespeare, image caption generation, etc.

What is a Neural Network?

- Multi-layer perceptron
- Perceptron was dev in 50s and 60s by Frank Rosenblatt
  - Binary inputs
  - Single binary output
- Computing output:
  - Assign weight to each input
  - If weighted sum of input &gt; threshold, then 1
    - ■■Else 0
  - Bias \*  (weights\*inputs) = output which if its &gt; threshold will emit 1
- Single perceptron is pretty simple
  - Complex network of perceptrons can make subtle decisions

- We can create LEARNING algos that TUNE the weights and biases
  - Perceptrons can be used as NAND gates, and NAND gates are universal computation devices
  - Tuning occurs in response to external stimuli and w/o direct intervention
    - ■■Created patterned circuit
  - We can then LAYER the perceptron networks and go &quot;deep&quot; with hidden layers
- BUT WHY do we need to go deep?
  - Because representations mater
    - ■■If we can build diff. Reps of the data then it&#39;s easy to seperate out the data you want from the noise you dont want

DESIGN CHOICES FOR AN ANN

- Learning algorithms
  - Backprop
  - Stochastic grad. Descent
- Activation Functions (threshold)
- Cost functions
- Number and dimensions of layers
- Connections between layers
- Regularizations
  - Layers
  - Batches

CNN: Conv. Neural Network:

- Succ. in images
- Error rate is damn near close to 0
- Word2Vec is a word embedding neural net
  - Word org. Neural net
  - Predict next word in a phrase by seeing previous words
    - ■■Similar to what the guy was doing with HTML

RNN: Recurrent Neural Network:

- Useful when time is important in the app
- Order of words in a sentence
- Want to be able to take the ordering into account in the generation of sentences
- In feed forward networks, the output is COMPLETELY det. By the inputs from the previous layers
  - RNN allow hidden layers to be affected by earlier activations so you can have cycles, etc.
- Allows analysis of data that changes over time

AUTOENCODERS:

- Unsupervised learning
- The goal is to compress the data and reconstruc the output automatically
- Middle of autoencoder is BOTTLENECK layer that makes you lose some amount of rep.
  - Idea is let&#39;s minimize the diff. Between the input the output
  - Encode the high-dim data with low-dim rep and then try and reconstruct high-rep data
- Can be used WITHIN other neural networks to initialize them
- Useful for dimensionality reduction
  - Data compression
  - Information retrieval
  - Denoising
  - Generative modeling (generating new models, etc.)

ULTRA DEEP LEARNING (RESNET)

- Very deep nets are hard to train
- ResNet developed model to address degradation in accuracy that occurs with more network layers
  - 152 layer network

GENERATIVE MODELS (GNNs):

- Important aspect of deep learning
- Create a map from random noise intro distribution of data you want to recreate

GENERATIVE ADVERSARIAL NETWORK:

- Pit generated models against network that tries to decide if the generated model is real or not
- Improves BOTH models

DEEP REINFORCEMENT LEARNING

- What is reinforcement learning?
  - Agent trying to make some decision
  - After action agent will have some obs. + some reward/consequence/cost
  - Minimize the cost over steps or Max. reward

RESTRICTED BOLTZMANN MACHINES:

- Type of stochastic recurrent neural network
- Models prob. Dist of input variables using input and hidden layers
- Trained using UNLABELED data
- Uses:
  - Feature learning
  - Initializing other deep networks
  - Components in other network


--


Class 2 

Missed Notes - Makeup

Notes should be here: http://cpsc663.guywolf.org/

**NOTES ARE NOT UP, FOLLOW UP IN CLASS**s
