
Tags: #vision 


$$
F_\omega = \sum_{t=0}^N { f_t \cdot e^{\frac{2i \pi \omega t}{N}} }
$$
![[Pasted image 20230925145856.png]]

### Algorithme

1. Conversion en niveau de gris *(simplifie les calculs)*
2. Application de la DFT 2D *(inclus dans les libs comme opencv)*
3. Décalage du zéro fréquentiel *(haut gauche -> centre grâce à ffshift)*
4. Calcul du module du spectre