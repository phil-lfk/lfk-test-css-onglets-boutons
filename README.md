# lfk-test-css-onglets-boutons
test page css (sans js) pour un display de boutons qui affichent des div cachées lorsqu'ils sont cliqués

Résumé du Code
-----------------

Description
-----------------
Ce projet implémente une interface utilisateur simple avec une disposition en deux colonnes. La colonne de gauche contient des boutons qui, lorsqu'ils sont cliqués, affichent du contenu spécifique dans la colonne de droite. Le contenu de la colonne de droite est masqué par défaut et devient visible en fonction du bouton sélectionné, grâce à l'utilisation de la pseudo-classe CSS :target.

Structure du Code
-----------------
HTML : Structure la page en deux colonnes. Les boutons de la colonne de gauche sont des liens ancrés qui ciblent différentes sections de la colonne de droite.
CSS : Gère la disposition, le style des boutons, et la visibilité du contenu basé sur la pseudo-classe :target. Le CSS assure également un style de mise en page réactif.
JavaScript : Non utilisé pour les interactions de cette page ; la visibilité du contenu est gérée uniquement via CSS.
Fonctionnalités

Disposition :
-----------------
Deux colonnes côte à côte : la colonne de gauche pour les boutons, la colonne de droite pour le contenu.
Les boutons sont alignés et centrés dans la colonne de gauche.

Affichage du Contenu :
-----------------
Par défaut, tout le contenu dans la colonne de droite est caché.
Chaque bouton de la colonne de gauche cible une section spécifique dans la colonne de droite, qui devient visible lorsque le bouton est sélectionné.
CSS Utilisé

Pseudo-classe :
-----------------
target : Permet de gérer la visibilité du contenu en fonction de l'ID ciblé dans l'URL.
Disposition Flexbox : Utilisé pour la mise en page des colonnes et le centrage des éléments.
Styles des Boutons : Personnalisés pour chaque couleur avec des bordures et sans soulignement.
