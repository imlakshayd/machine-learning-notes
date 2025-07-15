Neural networks (NN) also known as artificial neural networks (ANNs) are a machine learning model which try to mimic the human brain, specifically neurons on how to process information. NN which have more than one hidden layer are part of the subset of machine learning called [[Deep learning]], although many use NNs and deep learning interchangeably. These model are made up of node or neurons which work together to help solve the desired problem. They are adaptive which allows them to learn from their mistakes and improve from them. Neural Networks are actually an old idea which was used in the 1980's but they fell out of favor due to limitations of computational power, but they have made a resurgence around 2005 and have made great strides due to the rise of GPUs.

Due to the fact that neural net can make intelligent decisions with little human assistances and learn ambiguous patterns from data which human might overlook it allows them to have several uses in various industries. There are four main types of applications of neural networks which include the following:

- Computer vision:
	- Self driving cars
	- Facial recognition
	- Image recognition
	- Content moderation
- Speech recognition:
	- Customer service assistance
	- Transcription
- Natural language processing:
	- Chatbots
	- Summarizing content
	- Sentiment analysis
	- Classification of written data 
- Recommendation engines:
	- Google search
	- TikTok's recommendation system
	- Amazon product recommendation
	- Targeted marketing

![[Pasted image 20250611220900.png]]

Neural networks models are made of 3 layers which include the following:

- **Input Layer:** This is the initial layer of the network where all the data is received from the outside world. The nodes which make up the input layer than process the data and pass it on to the next layer.
  
- **Hidden Layer(s):** Neural nets can have one or more hidden layer and this is where transform the data from the input layer into an abstract representation of the data and learn basic patterns essentially. These layer most of the heavy lifting for the model and use a lot of computational power. With multiple hidden layers basic patterns can start to become more and more abstract.

- **Output Layer:** The output layer is the predicts and output of all our inputs and this depends on the task.

When data enters the input layer, and is transformed in the hidden layer(s) and give us an output, it passes through the neural net in a forward direction, this is known as forward propagation. Every time data goes through one layer to another it goes through an activation function, this function is conducting a linear transformation such as logistic regression (sigmoid function), and then the value denoted as $z$ is passed to the next layer. The activation function is shown below in the following:

$\vec{a}_{j}^{[l]}= g(\vec{w}_{j}^{[l]}\cdot\vec{a}^{[l-1]}+b_{j}^{[l]})$

Where:

- $\vec{a}$ is known as the activation function
- $l$ represents the layer index
- $j$ represent the unit (neuron)
- $w$ and $b$ being parameter of weight and bias

The image below shows the process of forward propagation through multiple layers

![[Pasted image 20250614011457.png]]


