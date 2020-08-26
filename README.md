# Physics-Informed-Neural-Network-PINNs---TF-2.0

Physics Informed Neural Network for 1-D Burgers' equation implemented using the **Sequential API** in Tensorflow 2.0. Originally, the code was implemented by *Raissi et. al.* using Tensorflow 1.0 (https://github.com/maziarraissi/PINNs) which is slightly difficult to interpret for people without a coding background. In contrast, Tensorflow 2.0 comes inbuilt with Keras, a High Level API that makes Machine Learning user friendly. 

Primarily, there are three ways of implementation using Tensorflow 2.0

1. Sequential API- High level API for hidden layers connected in series.
2. Functional API- High level API for multiple inputs/outputs or parallel arrangment of hidden layers.
3. Sub-classed API- Low level API. Implementation from scratch. 

These are mentioned in the order to complexity. For the problem at hand, Sequential API is sufficient.

Generally speaking, MLP are universal function approximators and the authors of this paper exploit this idea solve differential equations. The idea is to find the solution at random interior points in the domain such that the boundary conditions are known at collocation points. The total loss is the sum of MSE at interior points as well collocation points. The loss is minimised to satisfy the PDE with the boundary conditions associated with it. Please refer to this video(https://www.youtube.com/watch?v=LQ33-GeD-4Y&list=PLyqSpQzTE6M-SISTunGRBRiZk7opYBf_K&index=107&t=956s) as well as the orginal paper for extensive details.

# Implementation

The code has been implemented using Google Colab as it offers GPU as a runtime option. Most variables used in the code are in alignment with those used by *Raissi et. al.*. The input data and outputs from the original paper have been provided. Upload these on your google drive before running on Colab. This would be helpful in generating some graphs for comparison. Also, the code uses LBFG-S, which is second order optimizer. Conventional first order optimizers such as Adam, Gradient descent and RMSprop are slow to converge.LBFG-S is not available by default in Tensorflow 2.0 and hence a function from Tensorflow Probability has been used. This has not been coded by me except for a minor addition to loss function(check the loss_value variable). Please refer to this link (https://gist.github.com/piyueh/712ec7d4540489aad2dcfb80f9a54993)below to get a better idea.

# Results

https://github.com/deepmorzaria/Physics-Informed-Neural-Network-PINNs---TF-2.0/issues/2#issue-686213509

<img width="896" alt="Screen Shot 2020-08-26 at 3 59 20 PM" src="https://user-images.githubusercontent.com/23555180/91294117-aa924c00-e7b6-11ea-8e7e-b1b3ba93be5c.png">



# Citation
 @article{raissi2017physicsI,\
      title={Physics Informed Deep Learning (Part I): Data-driven Solutions of Nonlinear Partial Differential Equations},\
      author={Raissi, Maziar and Perdikaris, Paris and Karniadakis, George Em},\
      journal={arXiv preprint arXiv:1711.10561},\
      year={2017}\
  
