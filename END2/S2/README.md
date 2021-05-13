### How Neural network is getting traineed using Backpropagation algorithm


1. An example 3 layer neural network  is studied in the experiment as shown in the image below
2. The neural network is consisting of 4 fully connected neurons in the input and the hidden layer. 
3. Each of input layer and the hidden layer is with 2 neurons, and a final one output.
4. 2 weighted inputs  i1 & i2 are feed to the each of the neurons in the input layer.
5. Each neuron uses Sigmoid activation functions. 

<p align="bottom" width="100%">
    <img width="70%" src="https://github.com/Gitpabora/END2/blob/master/END2/S2/images/ANN1.png"> 
</p>

   #### Activation using Sigmoid 
   The general definition of is Sigmoid(x)= 1/(1+exp(-ax)) where a is the slope
   Graph of sigmoid function is S(slanted right) shaped. This is the most common activation function used .
   It is strictly increasing function, exhibiting a balance between linear and nonlinear behaviour. 
   The activation function helps to handle the nonlinearity of the data




### Mathematical basis 

The neural network is considered as a system where neurons are fully connected with weighted edges,the aim is to find the optimum values of weights in the edges , such that the deviation from the real ouput is minimum. Training the neural network is that the network is establised with the optimum numeric weights,such that it works as optimum approximator or predictor for the desired functionality.

The mathematical equations are shown below.

![forward prop](images/fwprop.png) 

As we can see from equation 5 and 6 , output is influenced by the weights.So to reduce the model loss as shown by equation 9 and 10 , we have to find a way to adjust the weights.This can be achieved by adjusting the weight w.r.t to the total error i.e by taking partial derivative of the error w.r.t w_i by keeping all other weights constant.The formula for adjusting the weight is given below.

![adjust weight](images/w_adjust.png)

The above formula is the foundation for carrying out back propagation in neural network.We will use the chain rule to find the partial derivative of error w.r.t each weight.

##### What is chain rule?


#### Back propagation

In this case we will start the partial derivation of Error from right side to left most side of the network.
  
![adjust weight 5](images/w_5.png) 

In equation 12 we find the partial derivative of E_total w.r.t weight 5.Looking at the network diagram , we see 


- 'E_total' is dependent on 'a_o1' and 
- 'a_o1' is dependent on 'o1'.
- 'o1' is dependent on 'w5'.

So based on chain rule we get equation 13.We can breakup equation 13 into three parts and find the partial derivative for each part as given by equation 14 , 15 , 16.

Similarly we can find the partial derivative of E_total w.r.t 

- weight 6
- weight 7
- weight 8

The result is shown below

![adjust weight 5 6 7 8](images/w_5_6_7_8.png) 
        
##### Now we need to pause and think , how to find the partial derivative of E_total w.r.t 'w1'.There are two routes in the network

![path to weight 1](images/p_w1.png)  

Partial derivatives of the two routes are given below

![partial derivative weight 1](images/partial_drv_w1.png)

When we embed equation 26 in equation 24 we get the partial derivative w.r.t route 21 , similarly when we embed equation 27 in equation 25 we get route 22.To get the resultant partial derivative of E_total w.r.t 'w1' we have to add the reult of equation 24 and 25.

Solving the above parts we get the following equations

![partcalculation](images/solving.png)

Putting the equations 28 , 29 , 30 , 31 together we get the solution for eqution 23

![putting together](images/four_tog.png)

Similarly we can find the partial derivative of *E_total* w.r.t

- weight 2
- weight 3
- weight 4
 
##### After the gradient of E_total is found with respect to each weight, we can use equation 11 to update each weight.

### A working example

The network shown in the beginning is used to test the above solution and generate a plot of L2 loss across different epoch for different learning rate.A range of learning rate was used to check the behavior of the model , the result is summarized below.

### Visualizing the computations and weight adjustments in an Excel sheet

Weights were initialized heuristically, in random values. 


#### use of learning rate 

### observations of changing learning rate in the experiment

#### When learning rate is 0.1


![putting together](images/llr_point1.png)

	The model loss is 0.15 after 76 epoch , the model will take longer to converge.

#### When learning rate is 0.2


![putting together](images/lr_point2.png)

	The model loss is 0.1 after 76 epoch , the model will take longer to converge.


#### When learning rate is 0.5


![putting together](images/lr_point5.png)

	The model is learning better and the loss is 0.05 after 76 epoch , the gradient is no longer linear.


#### When learning rate is 0.8

![putting together](images/lr_point8.png)

	The model is now learning faster and loss is around 0.025 after 76 epoch.


#### When learning rate is 1


![putting together](images/lr_1.png)

	The model behaves a little better than previous case and loss is 0.013 after 76 epoch.


#### When learning rate is 2
 

![putting together](images/lr_2.png)


	The model is converging faster and error is close to 0 after 76 epoch.



## Forward Pass
![forward prop](images/fwd.png) 



###
![Neural network](images/lr_point1.png)
 

###Activation 



## Backward Pass





