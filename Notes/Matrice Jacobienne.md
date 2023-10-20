Une matrice jacobienne est une matrice qui représente les dérivées partielles d'un système d'équations par rapport à ses variables. Plus précisément, elle est utilisée pour exprimer la variation des composantes d'un vecteur de fonctions en fonction de la variation de ses variables indépendantes. La matrice jacobienne est largement utilisée en mathématiques, en particulier en analyse, en calcul vectoriel et en optimisation.

Formellement, si vous avez un vecteur de fonctions $f(x) = [f_1(x), f_2(x), \cdots, f_n(x)]$ qui dépend d'un vecteur de variables $x = [x_1, x_2, \cdots, x_n]$, la matrice jacobienne $J$ de $f(x)$ est une matrice composée des dérivées partielles de chaque fonction $f$ par rapport à chaque variable $x$. Elle a la forme suivante :

$$
J = \begin{bmatrix}
\frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} & \ldots & \frac{\partial f_1}{\partial x_n} \\ \frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2} & \ldots & \frac{\partial f_2}{\partial x_n} \\ \vdots & \vdots & \ddots & \vdots \\ \frac{\partial f_n}{\partial x_1} & \frac{\partial f_n}{\partial x_2} & \ldots & \frac{\partial f_n}{\partial x_n} \end{bmatrix}
$$

Chaque élément de la matrice jacobienne est une dérivée partielle, où $\frac{\partial f_i}{\partial x_j}$ représente la dérivée partielle de la i-ème fonction par rapport à la j-ème variable.

La matrice jacobienne est utilisée dans de nombreux domaines des mathématiques et des sciences, y compris en calcul différentiel, en analyse numérique, en optimisation, en mécanique, en physique, en statistiques, et dans de nombreux autres domaines. Elle est un outil puissant pour comprendre comment les petites variations dans les variables indépendantes affectent les valeurs des fonctions d'un système, ce qui est essentiel pour de nombreuses applications pratiques.