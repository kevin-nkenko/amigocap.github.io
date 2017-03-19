


## Tutoriel : Lier une armature a un modèle 3D sous Blender

 Le but de ce tutoriel est de vous montrer comment lier une armature au format .bvh, obtenue par Motion Capture par exemple, à un modèle 3D préexistant sous Blender, afin d’animer celui-ci.
 
>Note : Pour procéder de manière la plus simple possible (Celle qui sera montrée ici), il est important que lors des premières secondes de son animation, l’armature ait une pose proche de la pose par défaut du modèle. Généralement il s’agit d’une pose neutre, le dos droit, les bras plus ou moins écartés. Ces premières secondes pourront facilement être coupées lors du rendu afin de ne conserver que l’animation souhaitée.

Si les poses de départ de l’armature et du modèle sont trop différentes, le processus sera plus long et difficile à réaliser, et il y a un risque que le modèle soit déformé dans l’animation.
Enfin, n’oubliez pas d’enregistrer votre travail aussi souvent que nécessaire en cas d’imprévus, voir sur plusieurs fichiers si vous avez peur d’enregistrer une mauvaise manipulation.

* TOC
{:toc}


### Etape 1 : Ouvrir les fichiers
Avant de commencer le travail, il faut bien sur ouvrir Blender et charger les fichiers qui seront utilisés.
Commencez par choisir *File > Open* dans le menu en haut à gauche de Blender, puis cherchez le modèle que vous souhaitez utiliser dans votre ordinateur. Cliquez dessus pour l’ouvrir.
Pour importer l’armature, cliquez sur *File > Import > Motion Capture(.bvh)* puis cherchez le fichier *.bvh* que vous voulez appliquer à l’armature.
Votre écran devrait alors ressembler à ça :
![](http://img4.hostingpics.net/pics/513724tuto38.png)

Il est possible que, comme dans l’exemple, votre armature ne soit pas orientée dans le bon sens. Si c’est le cas, supprimez l’armature en faisant un clic droit dessus, puis en appuyant sur le bouton *suppr* de votre clavier. Rouvrez le menu d’importation comme précédemment, mais avant de cliquer sur le fichier à ouvrir, modifiez les champs *Forward* et *Top* dans le menu *Import bvh* à gauche de l’écran pour qu’ils coïncident avec l’orientation de votre modèle. Si celui-ci est orienté de manière standard, les options *« -X Forward »* et *« Z Top »* devraient fonctionner.

### Etape 2 : Mettre l’armature à l’échelle
Sauf si vous êtes chanceux, l’armature sera probablement beaucoup plus petite ou beaucoup plus grande que le modèle auquel vous voulez l’appliquer. Dans cette partie, nous mettrons l’armature à la bonne taille et à la bonne place pour être utilisée.
Commencez par sélectionner l’armature avec un clic droit, puis appuyez sur *S*. Vous pouvez alors ajuster la taille de l’armature en déplaçant votre souris. Lorsque votre armature est à une taille adaptée, faites un clic gauche pour appliquer les modifications.
Il est probable que l’armature n’ait pas tout à fait les mêmes proportions que le modèle : Nous résoudrons ce problème dans une étape suivante.
Ensuite, en ayant toujours l’armature sélectionnée, appuyez sur la touche *G* pour déplacer l’armature. Faites en sorte que celle-ci suive à peu près le modèle. Enfin, faites un clic gauche pour valider. N’hésitez pas à ajuster encore un peu la taille et l’emplacement de l’armature pour obtenir la meilleure correspondance possible.

### Etape 3 : Ajuster les proportions de l’armature
Nous allons maintenant faire en sorte que les proportions ainsi que les positions de départ de l’armature et du modèle soient identiques.
Pour cela, assurez-vous que l’armature est toujours sélectionnée. Ensuite, dans le menu en bas de Blender, cliquez sur *« Object Mode »* et choisissez *« Edit Mode »*.
Vous pouvez maintenant modifier la position de base de l’armature.
Pour cela, faites un clic droit sur un des « nœuds » de l’armature, puis utilisez la touche *G* pour le déplacer comme fait précédemment pour l’armature. Ajustez de cette manière l’armature afin que les articulations soient placées là où elles devraient l’être par rapport au modèle. N’oubliez pas d’ajuster sous tous les angles. Vous pouvez changer l’ange de vue en appuyant sur la molette et en déplaçant la souris.
Une fois ce travail effectué, repassez en *mode objet*. Sélectionnez le modèle avec un clic droit, puis maintenez enfoncée la touche *Maj* et faites un clic droit sur l’armature. Appuyez maintenant sur *Ctrl+P* et choisissez *« …With automatic weights »* dans le menu qui s’affiche. Blender reliera automatiquement les mouvements de l’armature et du modèle.
![](http://img4.hostingpics.net/pics/472299tuto39.png)

Votre modèle devrait maintenant s’animer ! Testez en cliquant sur le bouton marche en bas de l’écran. Il est probable que l’animation présente quelques problèmes que nous allons résoudre.

![](http://img4.hostingpics.net/pics/175576tuto40.png)

Dans l’exemple ci-dessus la jambe du modèle effectue un mouvement qui n’est pas souhaité.

### Etape 4 : Ajuster les poids
Il est possible que l’attribution automatique des poids ne se soit pas faite comme vous le désiriez : Certaines parties du modèle suivent le mauvais os ou sont déformées par exemple.
Nous allons maintenant corriger cela.
Sélectionnez l’armature, et passez en *mode Pose*. Faites ensuite un clic droit sur l’un des os.
![](http://img4.hostingpics.net/pics/985758tuto41.png)

Faites ensuite un clic droit sur le modèle et passez en mode *« Weight Paint »*. Le modèle changera de couleur pour indiquer quelles parties sont influencées par l’os sélectionné. 
![](http://img4.hostingpics.net/pics/186915tuto42.png)

En faisant un clic gauche, vous pouvez « peindre » le modèle pour sélectionner les parties influencées par l’os. Si vous voulez qu’une partie du modèle ne soit plus dirigée par l’os, passez de *« Add »* à *« Substract »* dans le champ *« Blend »* du menu à gauche de l’écran et peignez. Vous pouvez changer l’os sélectionné avec un clic droit.
![](http://img4.hostingpics.net/pics/897664tuto43.png)

Expérimentez avec cet outil jusqu’à obtenir un résultat satisfaisant.
![](http://img4.hostingpics.net/pics/993045tuto44.png)

Dans l’exemple ci-dessus on a retiré la dépendance de la jambe au mouvement de l’armature, elle ne bouge donc plus. Le problème est résolu !

### Etape 5 : Rendu
Maintenant que votre animation est prête, il faut effectuer un rendu et l’enregistrer.
Il faut tout d’abord commencer par régler la caméra. Appuyez sur *0* sur le pavé numérique pour passer en vue camera, puis appuyez sur *N*. Dans le menu qui s’affiche, cochez l’option *« Lock camera to view »*. Vous pouvez maintenant changer le point de vue de la caméra avec la molette.
Une fois que vous avez un point de vue satisfaisant, cliquez sur l’appareil photo dans le menu à droite pour ouvrir le menu de rendu. Dans ce menu vous pouvez choisir entre autres le format de la vidéo, son nom et son emplacement. Une fois les réglages effectués, appuyez sur  *« Animation »* pour lancer le rendu.
Selon la longueur de la vidéo, le nombre et la complexité des éléments, etc… le temps de rendu peut facilement être très long. Une fois celui-ci terminé, vous pouvez retrouver votre vidéo à l’emplacement que vous avez spécifié.

