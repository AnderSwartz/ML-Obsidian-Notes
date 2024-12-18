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

Intuition is that the relevant information of each feature is relatively local

# Pooling
After the conv. layer, 


# 3D
If we have a 32x32x3, we need a 3D kernel.
Like before, after each application of the kernel (after each slide), it produces a single number. If you slide this kernel over the image and use the right padding, you get an output (feature map) with size, 32x32x1