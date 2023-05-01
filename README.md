Download Link: https://assignmentchef.com/product/solved-ele888-lab3-multilayer-neural-networks
<br>
To implement multi-layer neural network using the back propagation algorithm to classify linearly non-separable data.

Background

Multi-layer neural network (MNN) implements the linear discriminant functions however in a feature space where the input patterns are mapped non-linearly. Neural networks are quite powerful and easily realizable using simple algorithms where the form of non-linearity can be learned from the training data. One of the most popular methods for training the MNN is based on the gradient descent in error commonly known as backpropagation algorithm. Figure 1 shows an example of a 3 layer neural network.

The task is to estimate the weight vectors (<em>w<sub>ji </sub></em>and <em>w<sub>kj</sub></em>) between the input-hidden layer and the hidden-output layer for a given activation function. The pseudo code (11 steps) of the batch backpropogation algorithm is outlined on the following page.

Where: The sensitivity of unit <em>k </em>is given by

<table width="624">

 <tbody>

  <tr>

   <td width="604"><em>δ<sub>k </sub></em>= (<em>t<sub>k </sub></em>− <em>z<sub>k</sub></em>) · <em>f</em><sup>0</sup>(<em>net<sub>k</sub></em>)and the sensitivity for a hidden unit is given by</td>

   <td width="20">(1)</td>

  </tr>

 </tbody>

</table>

(2)

The (<em>net<sub>j</sub></em>) and (<em>net<sub>k</sub></em>) are the net activation and <em>f</em>(<em>net<sub>j</sub></em>) and <em>f</em>(<em>net<sub>k</sub></em>) are the non-linear activation functions. The derivative of the function <em>f</em>(·) is shown as <em>f</em>(·).

Figure 1: An <em>d </em>− <em>n<sub>H </sub></em>− <em>c </em>fully connected 3 layer NN (Bias not shown)

<strong>Back Propagation Algorithm:</strong>

<ol>

 <li>begin initialize network topology(# hidden units), <strong>w</strong>, criterion <em>θ</em>, <em>η</em>, <em>r </em>← 0</li>

 <li>do <em>r </em>← <em>r </em>+ 1 (increment epoch)</li>

 <li><em>m </em>← 0; ∆<em>w<sub>ij </sub></em>← 0; ∆<em>w<sub>jk </sub></em>← 0</li>

 <li>do <em>m </em>← <em>m </em>+ 1</li>

 <li><em>x<sub>m </sub></em>← select pattern</li>

 <li>∆<em>w</em><em>ij </em>← ∆<em>w</em><em>ij </em>+ <em>ηδ</em><em>jx</em><em>i</em>; ∆<em>w</em><em>jk </em>← ∆<em>w</em><em>jk </em>+ <em>ηδ</em><em>k y</em><em>i</em></li>

 <li>until <em>m </em>= <em>n</em></li>

 <li><em>w</em><em>ij </em>← <em>w</em><em>ij </em>+ ∆<em>w</em><em>ij</em>; <em>w</em><em>jk </em>← <em>w</em><em>jk </em>+ ∆<em>w</em><em>jk</em></li>

 <li>until k∇<em>J</em>(<strong>w</strong>)k <em>&lt; θ</em></li>

 <li>return <strong>w</strong></li>

 <li>end</li>

</ol>

<h2>Laboratory Exercises</h2>

<ul>

 <li>Construct a 2-2-1 neural network using the batch backpropogation algorithm for solving the classical XOR problem. The two inputs are given as <em>x</em><sub>1 </sub>= [ −1 −1 1 1 ] and <em>x</em><sub>2 </sub>= [ −1 1 −1 1 ]. The targets (correct output) are <em>t </em>= [ −1 1 1 −1 ]. Use a <em>η </em>= 0<em>.</em>1 and threshold <em>θ </em>= 0<em>.</em> Assume the following sigmoid activation function (for both hidden and output units)</li>

</ul>

<em>f</em>(<em>x</em>) = <em>a</em><strong>tanh</strong>(<em>bx</em>)                                                      (3)

where <em>a </em>= <em>b </em>= 1.

<ul>

 <li>Verify that the computed final weight vectors satisfy the XOR operation. Plot the learning curve and note the number of epochs needed for convergence.</li>

 <li>Repeat the above for the <strong>’Wine’ </strong>data set from the UCI repository:</li>

</ul>

<a href="https://archive.ics.uci.edu/ml/datasets/Wine">http://archive.ics.uci.edu/ml/datasets/Wine</a><a href="https://archive.ics.uci.edu/ml/datasets/Wine">,</a> using test samples from Class 1 (<em>ω</em><sub>1</sub>) and Class 3 (<em>ω</em><sub>2</sub>) – using only features <em>x</em><sub>1 </sub>= <em>Alcohol </em>and <em>x</em><sub>2 </sub>= <em>MalicAcid</em>. Use class target labels (<em>ω</em><sub>1 </sub>= 1, <em>ω</em><sub>2 </sub>= −1).

<ul>

 <li>Compute the classification accuracy for the given data. Plot the learning curve and note the number of epochs needed for convergence</li>

</ul>