Tags: #vision 

The Moravec corner detector, named after its creator Harry Moravec, is a simple and early corner detection algorithm. It identifies corners by computing the sum of squared differences (SSD) for small image patches shifted in different directions. The corners are located at positions where the SSD is maximized in all directions. The Moravec detector is fast and easy to implement but sensitive to noise.

![[Pasted image 20230929103155.png]]

$I$ -> Image
$\omega$ -> corner detection pattern
![[Pasted image 20230929112547.png]]

$(x, y)$ -> Coordinates in image
$(u, v)$ -> Coordinates in pattern
$(a, b)$ -> 
### Example

