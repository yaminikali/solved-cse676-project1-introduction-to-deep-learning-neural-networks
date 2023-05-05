Download Link: https://assignmentchef.com/product/solved-cse676-project1-introduction-to-deep-learning-neural-networks
<br>



Many deep learning models have been proposed and implemented towards the task of extracting features from a given image for classification. There is a lot of literature discussing new architectures from the point of view of the layers composition and recognition performance. Hence, it is very informative as an introductory project to analyze the aspects of a few architectures in terms of memory usage and inference time and how computational cost impacts the recognition accuracy.

<h1>2             Networks</h1>

<h2>2.1           VGGNet [1]</h2>

The VGG network architecture was introduced by Simonyan and Zisserman in their 2014 paper, Very Deep Convolutional Networks for Large Scale Image Recognition.

This network is characterized by its simplicity, using only 3×3 convolutional layers stacked on top of each other in increasing depth. Reducing volume size is handled by max pooling. Two fully-connected layers, each with 4,096 nodes are then followed by a softmax classifier.

<h2>2.2           ResNet [1]</h2>

Unlike traditional sequential network architectures such as AlexNet, OverFeat, and VGG, ResNet is instead a form of “exotic architecture” that relies on micro-architecture modules (also called “network-in-network architectures”).

The term micro-architecture refers to the set of “building blocks” used to construct the network. A collection of micro-architecture building blocks (along with your standard CONV, POOL, etc. layers) leads to the macro-architecture (i.e,. the end network itself).

First introduced by He et al. in their 2015 paper, Deep Residual Learning for Image Recognition, the ResNet architecture has become a seminal work

<h2>2.3           InceptionNet [1]</h2>

The “Inception” micro-architecture was first introduced by Szegedy et al. in their 2014 paper, Going Deeper with Convolutions

The goal of the inception module is to act as a “multi-level feature extractor” by computing 1×1, 3×3, and 5×5 convolutions within the same module of the network — the output of these filters are then stacked along the channel dimension and before being fed into the next layer in the network.

The original incarnation of this architecture was called GoogLeNet, but subsequent manifestations have simply been called Inception vN where N refers to the version number put out by Google.

The Inception V3 architecture included in the Keras core comes from the later publication by Szegedy et al., Rethinking the Inception Architecture for Computer Vision (2015) which proposes updates to the inception module to further boost ImageNet classification accuracy.

The weights for Inception V3 are smaller than both VGG and ResNet, coming in at 96MB.

<h1>3             Project Requirements</h1>

<h2>3.1           Implemention and Coding</h2>

<h3>3.1.1          Task Definition</h3>

<ol>

 <li>Implement VGGNet 16, ResNet 18, InceptionV2 architectures using <strong>SGD</strong>[2] and <strong>ADAM</strong>[3] optimization with the following variations in network regularization schemes:

  <ul>

   <li>No Regularization</li>

   <li>Batch Normalization [4]</li>

   <li>Dropouts [5]</li>

  </ul></li>

 <li>Use CIFAR-100 dataset for training and testing.</li>

 <li>Calculate Precision, Recall and Accuracy to evaluate each of the 18 experiments.</li>

 <li>Implement <strong>Early Stopping </strong>regularization scheme in all the experiments.</li>

</ol>

<ol start="2">

 <li style="list-style-type: none;"></li>

</ol>

<h2>3.2           Report</h2>

The report must contain the following points:

<ol>

 <li>Introduction section describing the project in general and why is it useful to do the comparison.</li>

 <li>Describe implementation of the architectures, the training as well as the specifics of the training procedure used.</li>

 <li>Explain the networks as best as possible in your words.</li>

 <li>Plots must be included in the report which shows the performance of the given model in terms of Accuracy and Loss over the trained epochs.</li>

 <li>Display a chart like the one shown in Figure 1 in the report to compare the above networks with various combinations and explain the results section.</li>

</ol>

<table width="562">

 <tbody>

  <tr>

   <td width="54"> </td>

   <td width="85"><strong>Arch</strong></td>

   <td colspan="3" width="137"><strong>VGG 16</strong></td>

   <td colspan="3" width="140"><strong>ResNet 18</strong></td>

   <td colspan="3" width="146"><strong>Inception v2</strong></td>

  </tr>

  <tr>

   <td rowspan="2" width="54"><strong>Optimizer</strong></td>

   <td width="85"><strong><em>Score</em></strong></td>

   <td width="50"> </td>

   <td width="36"> </td>

   <td width="51"> </td>

   <td width="53"> </td>

   <td width="36"> </td>

   <td width="51"> </td>

   <td width="59"> </td>

   <td width="36"> </td>

   <td width="51"> </td>

  </tr>

  <tr>

   <td width="85"><strong>Setting</strong></td>

   <td width="50"><strong><em>Precision</em></strong></td>

   <td width="36"><strong><em>Recall</em></strong></td>

   <td width="51"><strong><em>Accuracy</em></strong></td>

   <td width="53"><strong><em>Precision</em></strong></td>

   <td width="36"><strong><em>Recall</em></strong></td>

   <td width="51"><strong><em>Accuracy</em></strong></td>

   <td width="59"><strong><em>Precision</em></strong></td>

   <td width="36"><strong><em>Recall</em></strong></td>

   <td width="51"><strong><em>Accuracy</em></strong></td>

  </tr>

  <tr>

   <td rowspan="3" width="54"><strong>SGD</strong></td>

   <td width="85">With BatchNorm</td>

   <td width="50">1</td>

   <td width="36">1</td>

   <td width="51">1</td>

   <td width="53">2</td>

   <td width="36">2</td>

   <td width="51">2</td>

   <td width="59">3</td>

   <td width="36">3</td>

   <td width="51">3</td>

  </tr>

  <tr>

   <td width="85">With DropOut</td>

   <td width="50">4</td>

   <td width="36">4</td>

   <td width="51">4</td>

   <td width="53">5</td>

   <td width="36">5</td>

   <td width="51">5</td>

   <td width="59">6</td>

   <td width="36">6</td>

   <td width="51">6</td>

  </tr>

  <tr>

   <td width="85">No Regularization</td>

   <td width="50">7</td>

   <td width="36">7</td>

   <td width="51">7</td>

   <td width="53">8</td>

   <td width="36">8</td>

   <td width="51">8</td>

   <td width="59">9</td>

   <td width="36">9</td>

   <td width="51">9</td>

  </tr>

  <tr>

   <td rowspan="3" width="54"><strong>ADAM</strong></td>

   <td width="85">With BatchNorm</td>

   <td width="50">10</td>

   <td width="36">10</td>

   <td width="51">10</td>

   <td width="53">11</td>

   <td width="36">11</td>

   <td width="51">11</td>

   <td width="59">12</td>

   <td width="36">12</td>

   <td width="51">12</td>

  </tr>

  <tr>

   <td width="85">With DropOut</td>

   <td width="50">13</td>

   <td width="36">13</td>

   <td width="51">13</td>

   <td width="53">14</td>

   <td width="36">14</td>

   <td width="51">14</td>

   <td width="59">15</td>

   <td width="36">15</td>

   <td width="51">15</td>

  </tr>

  <tr>

   <td width="85">No Regularization</td>

   <td width="50">16</td>

   <td width="36">16</td>

   <td width="51">16</td>

   <td width="53">17</td>

   <td width="36">17</td>

   <td width="51">17</td>

   <td width="59">18</td>

   <td width="36">18</td>

   <td width="51">18</td>

  </tr>

 </tbody>

</table>

Figure 1:     Sample output table, where 1, 2, 3, … represent the experiment number.

<ol start="6">

 <li>A conclusion section.</li>

</ol>


