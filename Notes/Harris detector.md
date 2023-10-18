Tags: #vision 

The Harris corner detector, developed by Chris Harris and Mike Stephens, addresses some of the limitations of the [[Moravec detector]], particularly its sensitivity to noise. The Harris detector uses a similar approach by evaluating the variation in intensity for small image patches shifted in different directions. Instead of using SSD, it employs the Harris corner response function, which considers the eigenvalues of the structure tensor to calculate the corner score. This response function is more robust to noise and provides a better indication of corners in an image.

![[Pasted image 20230929110958.png]]

### Example

