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



Code JS décortiqué :
-----------------

  <script>
    document.addEventListener('DOMContentLoaded', function() {  // le dom doit être chargé entièrement avant d'éxécuter le reste 
      const buttons = document.querySelectorAll('#four-btn button'); // déclare la constante "buttons" et sélectionne tous les elements (par id="four-btn"
      const lists = document.querySelectorAll('.items-right'); //déclare la constante "lists" et sélectionne tous les elements (par classe items-right)
  
      buttons.forEach(button => { // depuis la constante " buttons" pour chaque élément "button"
          button.addEventListener('click', function() {  //ajoute un évènement pour écouter chaque 'button' s'il est cliqué. 
          const color = button.id.split('-')[1]; // déclare la constante 'color', cela permet de récupérer la couleur ("red", "blue", etc.). 
                                                 // la couleur est isolée de 'btn' grâce à .split('-')[1]
          const targetList = document.getElementById(`list-${color}`); //le code va cibler la bonne liste avec la couleur extraite précédemment.
          //déclare la constante 'targetList' et va récupérer la bonne liste. 
          // en cliquant sur le bouton, on déclenche donc la création de la constante 'color' qui peut-être 'red' ou 'green'....
          // le code va déterminer quelle liste avec d'abord document. (dans ce document),
          // je cherche l'élément selon son id qui sera 'list' suivi de la constante de couleur 'color' récupérée (ce sera dont 'list-red' ou 'list-blue', etc...)
  
          lists.forEach(list => { // depuis la constante 'lists' (déclarée en ligne 176) pour chaque élément 'list'
            if (list !== targetList) { // si la liste "observée" est !== strictement différente de la liste 'target' (ciblée) alors...
              list.classList.remove('show'); // on retire de la classe CSS 'items-right' l'état SHOW (ce qui permet de jouer la transition)
              list.classList.add('hide'); // et on ajoute l'état HIDE (ce qui permet de jouer la transition)
            }
          });
  
          if (targetList.classList.contains('show')) {  // pour vérifier si la liste cible est actuellement visible (contient l'état SHOW)
            targetList.classList.remove('show'); // si c'est le cas on retire l'état SHOW (transition jouée)
            targetList.classList.add('hide'); // et ensuite on ajoute l'état HIDE (transition jouée)
          } else { //SINON
            targetList.classList.remove('hide'); //on retire l'état HIDE
            targetList.classList.add('show'); //on ajoute l'état SHOW (transition jouée)
          }
        });
      });
    });
  </script>
