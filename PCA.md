- Unsupervised technique for projecting data into lower dimensional space
- Given a dataset with 1000 samples and 50 features, PCA will return up to 50 different principle components, each a 1000 vector

Optimization problem is to min the distance between every point in the original space and transformed space is as close as possible

![[Pasted image 20241024142411.png]]

xi is original point, xi' is projected point



![[Pasted image 20241024142650.png]]
vk is a unit vector representing one of the PCs

$(x^T v)v$ is the projection of data point x onto the direction v

(x^T v) gives a scalar value measuring how much x aligns with v



![[Pasted image 20241024164055.png]]
Same as the eigenvector equation.

You end up with the eigenvectors of XtX

