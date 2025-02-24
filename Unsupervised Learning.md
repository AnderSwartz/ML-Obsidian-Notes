One way to define the aim: create an internal representation of the input that is useful for subsequent supervised or reinforcement learning. E.g. clustering finds classes, then you do supervised classification

- Create compact, low-dimensional representation of the input
	- High-dimensional inputs typically live on a low-dimensional manifold. If you have a picture with a million pixels, there aren't really a million DoF, there are like a thousand. 
	- [[PCA]] is an example! It assumes there is 1 manifold which is a plane in the high-dimensional space.