# LSTM 
---

LSTM networks is the advanced form of Recurrent neural network which trains on the sequential input data.

A recurrent neuron saves the state of previous input and combines it with the current input thereby preserving relationship between the layers,previous and the current ones.

---

why can not we use a standard neural network to solve the squence problems?

first problem is that the inputs and outputs can be of different  lengths in different examples.

The normal Neural network doesnt share features learned between the position of words across the network.

In a recurrent neural network for the input x1, the activations of the 1 st network are transsfered to the next layer,which is again combined with the input x2 to predict an output y2.as shown below.

---

![img](https://i.imgur.com/gw1u89I.jpg)

---

so after each time step the RNN passes on the activation to the next time step for their use.

The typical forward function is denoted in the above image.

we can see we have three weights,Waa weights of the activation from previous layer. Wax the weights for the input at the Tth step.The output weights Wya.

general LSTM architecture is of unidirectional. One disadvantage of this is, the information is gathered from the previous time steps, not from the forward time steps for example.
*army core told " Major Tom is a great battle commander".*

so to identify whether the name Tom is a name information has to be taken not only from previous words of the sentences but also from the after name, words.

Now Loss for the entire sequence is given by the bottom formula.

---
![image2](https://i.imgur.com/qCrewef.jpg)

---

## Vanishing Gradient Problem in RNN's


The RNN architecture is designed to store short term dependencies(short contexts). But to remember the entire context of a particular story it fails. The reason being Vanishing Gradient.

---
**How vanishing Graident becomes a problem**

During the Backpropagation when the errors are passed back to the network to adjust weights for optimisation,the derrivatives are multiplied by the small value of the weights across each layer as it move towards the initial layers the value become very small, Thus the terms vanishing gradients.

THe current RNN just remembers just small context. This has introduced a modified RNN network called 
LSTM (Long Short Term Memory) networks.

LSTM have something called a cell memory. These memory blocks are responsible for stroing information and there are handled through gates.

Forget is responsile for removing the information from the memory cell 
INput gate,we add important information to the cell state.

Bringing out the output from the cell memory current state is done by output gate.
