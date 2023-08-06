# ordinary-differential-equation-with-neural-network
Solving ODEs analytically can be challenging, and therefore, several numerical methods have been developed to estimate their solutions. In recent years, machine learning techniques and neural networks have emerged as promising tools for approximating solutions to ODEs. In this article, we explore the use of the PyTorch library to train a neural network for producing the desired values of a function that estimates solution of an ordinary differential equation. We discuss how the learning rate, momentum coefficient, and number of layers may vary due to the complexity of the unknown function. Our study demonstrates the potential of machine learning and neural networks for solving ODEs, and highlights the advantage and limitations of using these techniques in practice.
By training the network for estimating correct value of f(x), we can find the solution of the equation. Also we need to differentiate the output of the neural network and then compare it with our loss function. Then the last step is to update the weights of our network.
For computing the discrete differentiation, we can use some numerical approximations such as Simpson’s rule, trapezoidal formula or other numerical formulas for evaluating the differentiation of a function. In this article we used two points forward formula. 
Also we run the network two times, first with ordered inputs and second, with shuffled input. This helps the network to compute the approximation of weights in first time and check them for better answer in the second time. 

![image](https://github.com/erfan-golshan/ordinary-differential-equation-with-neural-network/assets/129675348/7a9f1118-3c29-4e5d-86b4-e88d3d9d79e4)

In the first example we tried to solve this equation

df/dx=2x+1.f(0)=0

Which the exact answer is

f(x)= x^2+x

The loss values for the ordered input are as followed

![image](https://github.com/erfan-golshan/ordinary-differential-equation-with-neural-network/assets/129675348/66a2daec-e53d-4545-97a2-3ce88997fa18)

And the neural network predicts the answer 

![image](https://github.com/erfan-golshan/ordinary-differential-equation-with-neural-network/assets/129675348/7864ff15-6769-4fed-812c-1ccf473a8e54)

Which is not too much accurate. But for the next time that network uses shuffled data, the loss values become better as follow

![image](https://github.com/erfan-golshan/ordinary-differential-equation-with-neural-network/assets/129675348/af2ae7a0-1937-4aee-a5b4-a7f64915cf74)

And the prediction become much better

![image](https://github.com/erfan-golshan/ordinary-differential-equation-with-neural-network/assets/129675348/31dca2a4-0fcf-4cec-bb64-e0f5b8e62266)

for the next example we tried to solve this problem

df/dx=  (-1)/〖(x-5)〗^2 +2x.f(0)=0.4

Which the exact solution is

f(x)=  1/(x-5)+ x^2+0.6

The results are as followed;
Plot of loss for ordered inputs:

![image](https://github.com/erfan-golshan/ordinary-differential-equation-with-neural-network/assets/129675348/a890738c-ee86-4b93-8253-33ed5d897f18)

Plot of the prediction:

![image](https://github.com/erfan-golshan/ordinary-differential-equation-with-neural-network/assets/129675348/90b43796-9652-498e-80d3-c1c00580b33a)

Plot of the loss for shuffled inputs:

![image](https://github.com/erfan-golshan/ordinary-differential-equation-with-neural-network/assets/129675348/3775a205-4158-4699-84ae-6ff81531f671)

Plot of prediction after seeing shuffled inputs:

![image](https://github.com/erfan-golshan/ordinary-differential-equation-with-neural-network/assets/129675348/f004f8b4-c01e-4aa3-b114-8f4fd35e6f27)

