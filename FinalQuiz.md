## Intro to MLP Quiz
1. Who invented the Perceptron algorithm?
a) Alan Turing
**b) Frank Rosenblatt**
c) Ada Lovelace
d) Bjarne Stroustrop

2. What type of function cannot be estimated using a single layer perceptron? (Hint: write out their logic tables)
a) AND
b) OR
**c) XOR**
d) XAND

3. What are iteratively updated as the MLP learns?
**a) weights, biases**
b) activation functions, biases
c) inputs, biases, weights
d) inputs, activation functions

4. What does it mean for an MLP to be *fully connected*?
a) The number of inputs to a hidden layer of the MLP matches to the number of outputs of that hidden layer
b) Every neuron is connected to every other neuron
**c) Every neuron is connected to every other neuron in the immediately preceding and following layers**
d) Every neuron is connected to every other neuron in its own layer

5. Let us represent an MLP (without biases) with 4 neurons as a directed graph, where each neuron is a vertex that we denote as $v\in\{1,2,3,4\}$, and each connection is a directed edge that we can represent as a tuple of two vertices with the first item being the input and the second being the output. Which of the following sets of edges represent valid MLPs? Explain why or why not. (Hint: draw them out!)
a) {(1,2),(2,3),(3,4)}
b) {(4,3),(3,2),(3,1)}
c) {(1,3),(1,4),(2,3),(2,4)}
d) {(1,2),(2,4),(3,4)}
e) {(1,4),(4,3),(3,2),(4,2)}
f) {(1,2),(2,3),(3,4),(4,1)}
g) {(1,2),(2,4),(3,4),(1,4)}

Answer: 
a) Yes, we can regard this as a four layer network.
b) Yes, this is the same as a).
c) Yes, this is a fully connected 2 layer network.
d) No, this has 3 layers but is not fully connected.
e) No, there is no way to formulate this as a fully connected network.
f) No, there are no cycles allowed.
g) Yes, this is a fully connected 3 layer network.

6. Denoting the size (the number of neurons) of the $i^{th}$ layer as $n_i$ in an MLP with $m+1$ layers such that $i\in\{0,1,...,m\}$, how many weights do we have to learn?

Answer: $\sum_{i=1}^mn_{i-1}*n_i$



7. True or False: Given a black box MLP that we denote as the function $F:\mathbb{Z}^n \rightarrow \mathbb{Z}^m$, an input vector $x\in \mathbb{Z}^n$, and some scalar $\alpha\in\mathbb{R}$, we have $F(\alpha x) = \alpha F(x)$. Concisely explain why or why not.

Answer: False. The MLP is nonlinear due to the activation functions. 

8. Given input data representing a human with the following attributes: height (in cm), weight (in pounds), eye color (all are either brown, blue, hazel, or green), handedness (right or left) - what is the smallest number of column features in a proper input for an MLP?

Answer: 7. One for height, one for weight, four one hot encoded features for eye color, and one binary feature for handedness.

9. Given that the input of the activation function in an MLP can be written as $b + \sum_{i = 1}^{n} x_i \cdot w_i$ where there are $n$ inputs $x_i$ along with the $n$ weights $w_i$ single bias term $b$ that we need to learn,  how can we rewrite this expression as a dot product of two vectors? (Hint: You should treat the bias as a weight that we wish to learn)

Answer: We first write our input data and weights as vectors by augmenting the data with the constant 1 and regarding the bias as a weight, we can write 
$\textbf{x} = \begin{bmatrix}
           1 \\
           x_{1} \\
           \vdots \\
           x_{m}
         \end{bmatrix}$and $\textbf{w} = \begin{bmatrix}
           b \\
           w_{1} \\
           \vdots \\
           w_{m}
         \end{bmatrix}$

We can then write $b + \sum_{i = 1}^{n} x_i \cdot w_i = <\textbf{x},\textbf{w}>$.

10. Give a real life scenario in which we can apply MLPs and describe their inputs and outputs.

Answer: This is an open ended question, so the student gets credit as long as they mention a classification or regression task with practical implications. For example, we can automate the sorting of different colors of apples given a video of them taken in an apple sorting machine where the input is still frames of each apple taken from the video feed and the output is a color.
