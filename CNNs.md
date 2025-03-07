"Convolution" is a type of linear operation

instead of the linear combination that happens between x and w (before the activation function), we use convolution

if f is convoluted with g, you flip g and slide it over f

whenever trying to find peaks in a signal, you don't want the tiny peaks to count, so you smooth it out using something like a gaussian kernel / filter

![[Pasted image 20241112200428.png]]


3x4 matrix, 2x2 kernel -> 2x3 output
the size of the output gets reduced

IF you want to preserve the size, you do "padding":
![[Pasted image 20241112201633.png]]
There is an extra input (with value 0) that is "padded" around the size to make sure the feature map (output) after convolving is the same size.

The amount of padding is determined by stride.

Stride is the length (left to right) of the jumps between applications of the kernel


the output is a "feature map"
the input, convoluted with a kernel / filter outputs a feature map

So instead of solving for the weights when optimizing, you solve for the feature map.

The feature map is then put through the activation function. all of that is encompassed in a convolutional layer.

each kernel has a bias, so a 3x3 kernel actually has 10 params. 
Bias gets added after the multiplication

![[Pasted image 20241112201026.png]]

# Advantages
1. In fully connected layers (bottom example), all the nodes are connected to each other.
	In CNN, there are less connections. 
	In CNNs, there are ==sparse connections==
2. "Because you are estimating the weights of the kernel, you have a lot of parameter sharing"
3. You want hidden units to encode localized information, not information about the entire image
	1. In a fully connected network, all hidden units would connect to all inputs (the whole image)
4. Feature detectors can be shared across different locations (translation invariance)



Intuition is that the relevant information of each feature is relatively local

# Pooling
After the conv. layer, 


# 3D
If we have a 32x32x3, we need a 3D kernel.
Like before, after each application of the kernel (after each slide), it produces a single number. If you slide this kernel over the image and use the right padding, you get an output (feature map) with size, 32x32x1

# Equavariance
Quality of the CNN layers: IF we shift the input, the output (activation map) changes in a proportional way

# Invariance
Quality of the model outputs: IF we shift the input, the output does not change

Pooling layers are slightly invariant

Each point in an activation map has a **receptive field**, which is the places in the input that contribute to that point

# Tied weights / weight sharing
In CNNs, the weights that get applied when a kernel moves over the beginning of an image are the same weights that get applied when a kernel moves over the later part of the image

We want to learn the weights for the kernels that work when applied to any location

## Advantages of tied weights
1. Translation invariance - learned filters are not specific to certain parts of image
2. Fewer params - instead of learning separate weights for each position, we only need to learn one set of weights for each kernel that work everywhere
3. Better generalization - With fewer params, avoid memorizing specific, localized details

## Weights vs Connections
- **Weights** are learned parameters that make up the kernel.
	- Below, there are 3 weights in the kernel (BGR)
- **Connections** are all combinations of these weights connected with their corresponding feature map location
	- Below, there are 9 connections. 'valid' padding means # of output units = input - kernel_size +1 = 3 (when stride = 1)
	- There are even connections in Pooling! no weights
	- In FC layers, weights = connections
![[Pasted image 20250220152141.png]]



# Size of units
Why is it important?
 - During training: number of units makes the number of add-multiplies grow quadratically (only during training!
	 - During forward pass, activations get calculated and stored for later use during backprop
 - During test time, you don't need to remember activations! pass to next layer and delete

# Size of weights
Why is it important?
- Every weight needs to be stored in memory during trained AND testing
	- If only a small amount of weights are needed to run the model, it can run on a cell phone!
- Generally speaking, more weights allow for more overfitting
- For every weight in backward pass, we will need to find the partial der of the cost wrt it

# Size of connections
Why is it important?
- For every connection in forward pass, it contributes 1 add-multiply (NOTE: THIS ISN'T TRUE FOR WEIGHTS)
- For every connection in backwards pass, it contributes 2 add-multiply 

In general, most weights will come from the FC layers, where weights = connections
most connections and units will come from Convolutional layers



## Backprop
First, find dL/d_feature_map
since same filter was applied everywhere, each filter position contributes to the gradient of the filter

Therefore, we have to see how the filter's weights contributed to each position in the feature map, and sum these values.

we have to compute the gradients for each location in the image and avg those gradients


![[Pasted image 20250218170542.png]]
![[Pasted image 20250218170554.png]]
![[Pasted image 20250218170630.png]]
![[Pasted image 20250218170702.png]]
![[Pasted image 20250218170733.png]]
![[Pasted image 20250218170833.png]]