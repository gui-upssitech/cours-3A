Tags : #motion-planning 

Lorsqu'on parle de jacobienne augmentée, on se réfère généralement à une extension de la [[Matrice Jacobienne]].

L'idée derrière la jacobienne augmentée est de prendre en compte des contraintes supplémentaires dans un problème d'optimisation. Elle est couramment utilisée dans les méthodes de programmation linéaire, de programmation linéaire en nombres entiers et d'optimisation non linéaire. Elle fait cela en combinant la jacobienne des équations de contrainte avec la jacobienne des équations objectives du problème d'optimisation. 

## Calcul

Le calcul de la matrice jacobienne augmentée dépend du contexte et du problème spécifique que vous essayez de résoudre. Cependant, voici une méthode générale pour calculer la jacobienne augmentée :

1. Identifiez vos équations d'objectif et de contrainte : Tout d'abord, vous devez avoir un ensemble d'équations d'objectif que vous souhaitez optimiser et des équations de contrainte que vous devez respecter. Ces équations doivent être exprimées en fonction de vos variables de décision.

2. Calculez les dérivées partielles : Pour chaque équation d'objectif et de contrainte, calculez les dérivées partielles par rapport à toutes les variables de décision. Cela vous donnera la jacobienne pour les équations d'objectif et la jacobienne pour les équations de contrainte.

3. Assemblez la matrice jacobienne augmentée : La matrice jacobienne augmentée est formée en combinant la jacobienne des équations d'objectif et la jacobienne des équations de contrainte. La structure de cette matrice dépendra de la nature du problème et de la méthode d'optimisation que vous utilisez.

4. Utilisez la matrice jacobienne augmentée : Une fois que vous avez calculé la matrice jacobienne augmentée, elle peut être utilisée dans le cadre de méthodes d'optimisation telles que la méthode des multiplicateurs de Lagrange, la méthode de pénalité, ou d'autres méthodes d'optimisation non linéaire. Cette matrice joue un rôle essentiel dans la détermination des points optimaux qui satisfont à la fois les contraintes et les objectifs du problème.

Il convient de noter que le calcul de la jacobienne augmentée peut devenir complexe, en particulier pour des problèmes avec de nombreuses variables et contraintes. Dans de tels cas, il peut être utile d'utiliser des logiciels de calcul symbolique ou des outils informatiques de calcul numérique pour automatiser le processus de calcul. De plus, le choix de la méthode d'optimisation dépendra de la nature du problème, et un expert en optimisation peut être utile pour vous guider dans le processus.