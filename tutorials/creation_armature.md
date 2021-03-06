## Tutoriel: Création d'une armature sous Blender

Ce tutoriel décrit la démarche à suivre afin de créer un squelette sous format bvh à partir de d’un fichier c3d (c’est le format d’exportation que nous avons choisi sur le logiciel Nexus disponible dans la salle Amigo, d’autres formats peuvent être utilisés mais ne seront pas décrits dans ce tutoriel), de l’importation à l’exportation.
Les phases d’acquisition et d’habillage de l’armature sont décrits dans d’autres tutoriels.

Remarque : cette méthode est manuelle et s’applique donc à des objets qui ne sont pas trop complexes. Il est possible pour ces autres objets d’utiliser des scriptes afin d’automatiser le processus et de gagner du temps.

**Table des matières**

* TOC
{:toc}



### Importation du fichier .c3d
Le module qui permet l’importation de fichier .c3d sous blender est déjà présent nativement sur le logiciel mais n’est peut-être pas activé. Pour cela, il faut aller dans *File >> user preferences >> add-ons* puis dans le menu catégorie à gauche, aller dans *Import-Export*. Il suffit alors de cocher *Import-Export : C3D Graphics Lab Motion Capture file (.c3d)* puis de cliquer sur *Save User Settings*.

![Import-Export C3D](http://img4.hostingpics.net/pics/850825tuto26.png)

### Préparation du fichier
**Ajustement du nombre de frames**
Par défaut, le nombre de frames s’étend de 1 à 250. Il faut donc étendre ou réduire ce nombre dans le panneau d’animation en bas de l’écran si vous n’avez pas changé la disposition afin de le faire correspondre à la durée de votre acquisition.

**Nettoyage des points**
Tous les points qui apparaissent sur votre écran ne sont peut-être pas utile, cela dépend de la manière dont vous avez effectué votre acquisition : certains points servent par exemple uniquement à effectuer la reconstruction sur le logiciel nexus lorsque des points disparaissent. Ils n’ont dès lors plus de rôle à jouer dans l’armature. Vous pouvez donc enlever ces points afin de diminuer la complexité du traitement.

**Utilisation du *Pose Mode***
Dans Blender, il existe un mode spécialement pour développer les armatures à partir de bones qui s’appelle le *Pose Mode*. Il est dans le même menu déroulant que le mode objet et le mode édition. C’est dans ce mode que va être effectué la mise en place des contraintes.

### Placement des « bones »
Pour mettre en place un bones entre deux points, procédez de la manière suivante :

 * Sélectionnez un marqueur (ou point) avec le clic droit puis positionner le curseur 3D dessus avec *shift S >> Cursor to selected*.
 
 ![Sélection marqueur](http://img4.hostingpics.net/pics/868314tuto28.png)
 
 *  	Insérer un bone avec *shift A >> Armature >> Single bone*.

 ![Insertion bone](http://img4.hostingpics.net/pics/445571tuto29.png)

 * Sélectionnez le 2ème marqueur et placer le curseur 3D dessus comme précédemment.
 * Sélectionnez le bone, allez dans le mode édition et sélectionnez la tête du bone.
 ![Selection tête bone](http://img4.hostingpics.net/pics/383445tuto30.png)

 * Positionnez la tête du bone sur le 2ème marqueur en utilisant *shift S >> Selection to cursor*.
 ![Selection to cursor](http://img4.hostingpics.net/pics/189035tuto31.png)

 * Il peut être utile de recalculer le roulis des bones auquel cas utilisez *ctrl N >> Cursor* dans le mode édition.
 * Pour créer un bone supplémentaire, procédez dans le mode édition comme pour une extrusion avec la touche E.

>Remarque : pour positionner un bone entre plusieurs marqueurs, il suffit de les sélectionner en maintenant la touche shift enfoncée puis *shift S >> Cursor to selected* place le curseur 3D à équidistance des points.

![Equidistance](http://img4.hostingpics.net/pics/865029tuto32.png)

A la fin de cette étape, vous devez avoir obtenu l’armature complète de votre personnage ou objet. Il ne reste plus qu’à fixer les contraintes sur chaque os afin qu’ils suivent les points lors de l’animation.

![armature complète](http://img4.hostingpics.net/pics/627073tuto33.png)

###Mise en place des contraintes sur les « bones »
Pour cette étape, il faut se placer dans le *Pose Mode*.

 * Sélectionner un bone puis allez dans le panneau de droite dans *bone constraints*.
![bone constraints](http://img4.hostingpics.net/pics/937945tuto34.png)

 * Ajouter une contrainte de localisation appelée *copy location*. Sélectionnez (soit à l’aide de la pipette, soit dans le menu déroulant) le marqueur de référence de votre os, celui qui correspond à la base de votre bone.
 
 ![Selection marqueur de référence](http://img4.hostingpics.net/pics/508374tuto35.png)

>Remarque : si votre point de référence est positionné entre plusieurs marqueurs, il faut ajouter une contrainte pour chaque marqueur et leur donner des poids équivalents (paramètre *Influence*, dont la somme doit être égale à 1).

Exemple:

![Exemple](http://img4.hostingpics.net/pics/125530tuto36.png)

 * Ajoutez une contrainte de direction, appelée *Damped track*. Associez à cette contrainte le marqueur qui correspond à la tête de votre bone, comme vu précédemment. La remarque sur le nombre de marqueurs est valable ici également.
 
![](http://img4.hostingpics.net/pics/386165tuto37.png)

A la fin de cette étape, votre armature contient toutes les contraintes nécessaires pour qu’elle suive les points. A noter qu’il peut y avoir un léger décalage qui n’a pas forcément d’incidence si le mouvement effectué est le bon, qui peut être dû au fait que la distance entre les marqueurs varie légèrement lors de l’acquisition.
Vous pouvez dès à présent observer votre armature bouger en appuyant sur *alt + A* dans le *Pose mode* ou le *mode objet*.

### Exportation
Pour exporter votre armature, allez dans *file >> export >> Motion Capture (.bvh)*.

>Remarque : il peut être nécessaire de lier tous les bones entre eux, en les sélectionnant et en appuyant sur *ctrl + J*.



