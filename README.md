# motscroises

Les générateurs automatiques de mots croisés ne sont pas très bons.
L'idée de ce projet est d'exploiter les dernières avancées du TAL concernant les
plongements sémantiques contextuels des mots pour proposer des "définitions"
intéressantes des mots à trouver. Ainsi, pour chaque mot cible, on extrait une phrase
contenant ce mot et on calcule l'embedding du mot avec CamemBERT. On cherche alors
dans le voisinnage de cet embedding un autre mot proche mais dont le lemme est différent.
Ce mot-voisin sert alors de définition.
Tous les mots dont je parle sont issus de corpus textuels, filtrés par des fréquences minimales,
plutôt que de dictionnaires (ou des deux, selon certaines proportions).

La construction de la grille de mots croisés est sinon classique, en cherchant par des méthodes
de type Monte Carlo une disposition des mots qui respecte certaines contraintes:
nombre maximum de cases noires, nombre maximum de mots de fréquences très faibles,
nmobre maximum de cases noires contigues, etc.

La grille pourrait être rendue plus intéressante également en utilisant un topic model.
