# Convolutions and Activation functions 
---
## Lets Get Started 
![image](https://media.giphy.com/media/SmgdGLAzMPOUw/giphy.gif)
---

---
## 3 x 3 CONVOLUTION

the purpose of a convolution is to extract features from the input images using the convolution operation.

*Convolution can be said as process where each element is added to its local neighbours,weighted by kernels(filters).*

>Suppose you have an image as shown below.

![Imgur](https://i.imgur.com/2Ao6lUL.png)

---
>And now we use a 3 x 3 kernel or filter on the input image to extract some features of the image.

---
![Imgur](https://i.imgur.com/YB3vhdP.png)


### The Operation Is Shown Below 
---
**Step-1**
>The 3X3 matrix starts its operation on the image from the top left corner of the image. Its a basic convolutin operation where in the values of the 3 X 3 filter is mutiplied by the corresponding values in the cell and finaaly summed across.

![Imgur](https://i.imgur.com/s2CHBJt.png)


**step-2**
>This proces is now repeated, by moving to the next position, 3 x 3 matrix in the input image(*stride*=1),where again the filter is convoluved on the same shape.

![Imgur](https://i.imgur.com/fhghEQp.png)


>we  get a new matrix of convolved features with a loss of two pixels,from the original image.

This 3 by 3 matrix is also know by other names
* Masks
* Kernels
* FIlters

Depending on the values of the kernel, it can be used for image *edge detection,sharpening images,blurring* etc.




# 1 x 1 CONVOLUTION 

Now lets look at another filter,which is a 1 by 1 dimensional filter.

>why we use 1 by 1 convolution, well simply saying this filter helps in dimensionality reduction.
Suppose we have an image of 
28 x 28 x 50. Now on convolving with a 1 x 1 x 10 we get the convolved feature matrix as 28 x 28 x 10.

---
![Imgur](https://i.imgur.com/cvFmAVo.png)


---
>1 by 1 convolutions help in shrinking the number of channels. 
It also helps us to build more deeper networks with less computation.
More the number of channels means we adding on data to the training.
1 by 1 convolutions minimises this computation process.
Not only that it introduces new parameters and new non-linearity into the network which help to increase the model accuracy.


# ACTIVATION FUNCTIONS

![Imgur](https://i.imgur.com/Rnyn8xA.gif)

---

**First question: What is an activation function.**

>Well it is added to the output of every layer in a neural network, It is also attached in between two neural network layers. Activation Function determines the output of the neural network.

---
**Second question: Why to use an activation function.**

>Suppose we do not use an activation function. We know that the neurons calculate the weighted sum of the inputs.
```Y=sum(weight*input)+bias```

>Now **Y** can take any value, how can we decide on which value that particular neuron should fire or not.If this neuron fires then only the output of this can be taken as input to the next laye. So it seems kind of necessary. We can not have an infinity space.

**Third question: Which activation can be used to fire neurons.**

>Now on the basic thought of it we can take out all the negative values, and take from 0, but to where. we can consider something like a threshold, if the values of the **Y** is greater than a threshold the state is **1** else state **0**. This brings the similarity to a **Step Function**.

>But the problem comes when there are multiclass prediction and mulitpile layer neurons. So if mulitiple neurons fires we get **1** from all the neurons,this poses a challenge on which neurons to select.

*So we need a range of values which falls on the postive space and is of limited range.*

**Linear Function**

```y=mx+c```
>why not using this.This solves the problem partially from the step function, but during the step of the back propagation.The derrivate will be a constant ```m```.
Now the gradient will be a constant one,the decent will be on a constant gradient.

>Other problem is the last activation layer is the linear function of the input of first layer.
No need for layers right!!

**Sigmoid Function**

>It defeats the linearity problem we had earlier as its non linear in nature. Also the range is from  **0 to 1**. How about the Gradient,it has a smooth Gradient. Also it has a tendency to bring the **Y** values to the extreme edges (0 and 1),but at these ends **Y** values respond very less to changes in the **x** values,i.e the graidents at this region will be small(vanishing Gradients).The gradient decent will be slow once it reaches this region.

**Tanh Function**
>Similar to Sigmoid. Tanh is non-linear,ranges from **(-1,1)**.This function also suffers from the vanishing graident problem as diccused above.

**Relu Function**
Relu is non linear in nature,But the range is from **(0,inf)**.

```Y=max(0,x)```

That means for random initialization for negative values the output is 0 that means fewer neurons are firing, but in case of sigmodi,tanh function almost all the nurons fire.
So Relu is computationally less expensive,compared to other activation functions.

---
The choice of the matter of which activation function to use is based on individual problem one is handling.Mos populary Relu is used,mostely the choice is based on individual it can be random or a trial and error method ,testing each functions.

---
