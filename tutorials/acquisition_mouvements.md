


## Tutoriel: Acquisition de mouvements

Le dispositif de Motion Capture installé dans la salle Amigo de l’Ecole Centrale de Lyon permet d’enregistrer les mouvements de capteurs dans l’espace. Ce tutoriel permet d’expliquer, étape par étape, comment obtenir l’enregistrement de ces mouvements sous un format exploitable par des logiciels d’animation 3D tel que Blender.

**Table des matières**

* TOC
{:toc}


### Étape 1 : Démarrage

Il faut bien évidemment commencer par allumer l’ordinateur et les caméras pour pouvoir utiliser le dispositif.
L’interrupteur des caméras est situé derrière le mur, à gauche.

### Étape 2 : Lancement

Une fois que tout est allumé, il faut lancer Vicon Nexus 2.5, le logiciel qui permet d’effectuer l’acquisition.
Le programme peut se lancer à partir de cette icône sur le bureau :

![Lancement Nexus](http://www.hostingpics.net/thumbs/25/69/70/mini_256970tuto1.png)

### Étape 3 : Changement de vue

Pour préparer les caméras, il va falloir changer la vue du logiciel.
Pour cela, cliquez sur *« Go Live »* en haut à gauche de l’écran, et dans le menu déroulant à côté, passez de *« 3D perspective »* à *« Camera »*.

![Changement de vue](http://img4.hostingpics.net/pics/572763tuto2.png)

Enfin, dans le panneau de gauche, sélectionnez toutes les caméras :

![Sélection caméras](http://img4.hostingpics.net/pics/180318tuto3.png)

La vue devrait alors ressembler à ceci :

![vue](http://img4.hostingpics.net/pics/423773tuto4.png)

### Étape 4 : Correction des réflexions parasites

Il est possible qu’il y ait des réflexions ou des scintillements parasites. Il va donc falloir faire en sorte que ceux-ci soient ignorés par les caméras.
Pour utiliser la souris, maintenez la molette enfoncée pour déplacer le cadre et le bouton de droite pour zoomer/dézoomer. 

![Correction](http://img4.hostingpics.net/pics/442396tuto5.png)

Si vous repérez un scintillement, cliquez sur l’icône pinceau en haut de la vue centrale puis cliquez sur la case présentant ce scintillement pour la masquer. Les cases masquées deviennent bleues, comme montré ci-dessous. Pour démasquer une case, utilisez la gomme, dont le bouton est situé à côté du pinceau. Pour enlever tous les masques, cliquez sur le bouton croix.

![Exemple cases masquées](http://img4.hostingpics.net/pics/891663tuto6.png)

### Étape 5 : Calibrage

Il faut maintenant calibrer les caméras pour que l’acquisition s’effectue correctement.
Pour cette étape et la suivante, vous aurez besoin de la croix de calibrage. N’oubliez pas de l’allumer avant de l’utiliser, sinon il ne se passera rien !

Commencez par aller dans la rubrique *« Calibrate Cameras »* du panneau *« Tools »*, situé à droite de l’écran. Appuyez sur *« Start »* déplacez-vous dans la salle en tenant la croix de calibrage. Pour une calibration correcte, il faut faire en sorte que plusieurs caméras puissent voir la croix en même temps : si vous calibrez les caméras une par une, vos acquisitions ne seront pas correctes.

![Panneau tools](http://img4.hostingpics.net/pics/780078tuto7.png)

La rubrique *« Camera Calibration Feedback »* donne des informations sur la progression du calibrage. Le calibrage se termine lorsque toutes les caméras sont vertes dans cette rubrique.

![Calibrage](http://img4.hostingpics.net/pics/706648tuto8.png)

### Étape 6 : Origine

Il faut maintenant régler l’origine du repère utilisé par les caméras.

Placez tout d’abord la croix allumée au centre de la salle puis, dans le panneau *« Tools »*,  cherchez la rubrique  *« Set Volume Origin »*  et appuyez sur  *« Start »*.

![start](http://img4.hostingpics.net/pics/921032tuto9.png)

Repassez ensuite en vue *« 3D perspective »* et vérifiez qu’il n’y a pas dédoublement des points de la croix.

![vue 3D perspective](http://img4.hostingpics.net/pics/584333tuto10.png)

S’il y a dédoublement, il faut recalibrer les caméras comme expliqué dans l’étape précédente.

### Étape 7 : Créer un nouveau patient

Le logiciel étant à la base conçu pour une utilisation dans le milieu médical, il utilise une structure de fichiers assez spécifique. Les étapes suivantes permettent donc de mettre en place la hiérarchie nécessaire.

Nous allons tout d’abord créer un nouveau patient. Dans le panneau *« Communication »* en bas au centre,  cliquez sur le bouton *« New Patient Classification »* :

![Panneau Communication](http://img4.hostingpics.net/pics/987684tuto11.png)

Puis sur « New Patient » :
![New Patient](http://img4.hostingpics.net/pics/879222tuto12.png)

Puis créez une nouvelle session en cliquant sur le bouton « New Session » :
![New Session](http://img4.hostingpics.net/pics/125592tuto13.png)

### Étape 8 : Créer un nouveau sujet

Dans le panneau à gauche de l’écran, cliquez sur l’onglet *« Subject »* et créer un nouveau sujet en cliquant sur le premier bouton, *« Create a blank suject »* :

![Create a blank subject](http://img4.hostingpics.net/pics/349710tuto14.png)

### Étape 9 : Réaliser une acquisition

Dans le panneau Tools,  ouvrez l’onglet  *« Subject Preparation »* et vérifiez que le bon sujet est sélectionné :

![Subject Preparation](http://img4.hostingpics.net/pics/514854tuto15.png)

Ensuite, cliquez sur le bouton *« Start »* pour lancer l’acquisition. Lorsque l’acquisition est finie, appuyez sur *« Stop »*.

Cliquez ensuite sur *« Go Offline »* à gauche, puis sur le bouton représentant des bulles grises  dans la barre en haut de l’écran pour observer le résultat de l’acquisition.

### Étape 10 : Créer des segments

Nous allons maintenant créer des segments entre les points. Cela permettra au logiciel d’étiqueter chaque point, et nous permettra d’y voir plus clair. 
Pour cela, entrez le nom du segment voulu dans le champ *« Create Segments »*,  cliquez sur *« Create »*,  puis sur les points que vous souhaitez relier. Enfin, recliquez sur *« Create »* pour que le segment apparaisse. 

![segment en cours de création](http://img4.hostingpics.net/pics/943910tuto16.png)

Répétez l’opération pour créer autant de segments que voulu. N’oubliez pas d’enregistrer le sujet en cliquant sur la disquette.

![Un exemple de résultat](http://img4.hostingpics.net/pics/404836tuto17.png)

### Étape 11: Étiqueter les marqueurs

Le travail n’est pas encore fini : en effet, si vous regardez un autre moment de l’acquisition à l’aide de la barre de temps situées sous la vue, vous verrez que votre squelette n’est pas toujours complet.

![Barre des temps](http://img4.hostingpics.net/pics/877347tuto18.png)

On peut distinguer deux types de problèmes :

* Un marqueur perd son étiquetage à un moment et le logiciel ne le reconnait donc plus comme étant le même point qu’aux autres moments.

* Un des marqueurs disparaît tout simplement car il été caché lors de l’acquisition. 

Un exemple sur l'image ci-dessous : certains marqueurs ont disparu, d’autres ne sont plus étiquetés.

![Marqueurs](http://img4.hostingpics.net/pics/681306tuto19.png)

Nous allons commencer par régler le problème de l’étiquetage.
Pour commencer, allez dans l’onglet *« Quality »* du panneau *« Communications »* situé en bas de l’écran.

![Onglet Quality](http://img4.hostingpics.net/pics/324454tuto20.png)

Les points colorés représentent les marqueurs étiquetés. Plus le point est rouge, plus il y a de moments où le point disparait. Les points gris représentent les marqueurs non étiquetés.

Cliquez sur un de ces points gris pour voir ou se situe ce marqueur, puis faites un clic droit dessus pour lui étiqueter le nom correspondant. Répétez l’opération jusque à ce qu’il n’y ait plus de marqueurs gris.

![marqueurs étiquetés](http://img4.hostingpics.net/pics/598522tuto21.png)

### Etape 12: Remplir les trous

Il faut maintenant remplir les trous où les marqueurs disparaissent.

Cliquez sur l’onglet *« Label »* du panneau *« Tools »*. Nous allons nous intéresser à la rubrique *« Gap Filling »* :

![Gap Filling](http://img4.hostingpics.net/pics/195926tuto22.png)

La liste en haut répertorie tous les trous. Cliquez sur un élément de cette liste pour voir le moment ou le marqueur concerné disparaît. Pour remplir le trou, cliquez sur *« Pick sources »* dans la partie *« Rigid Body Fill »*, puis cliquer sur trois points proches et ayant un mouvement similaire au marqueur disparu. Cliquez ensuite sur *«  Fill »* pour remplir le trou, ou *« All »* pour remplir autant de trous que possible en gardant les même points comme sources.
Répétez cette opération jusqu’à ce qu’il n’y ait plus de trous.

Maintenant que l’acquisition a été traitée, nous allons l’exporter pour pouvoir l’utiliser sous Blender.


### Etape 13: Exportation

Dans l'onglet *« Tools »*, onglet *« Pipeline »*, sélectionnez  *« Exportation »* dans le menu *« Current Pipeline »*, puis le bouton lecture.

![Exportation](http://img4.hostingpics.net/pics/485636tuto23.png)

L’acquisition sera alors enregistrée au format C3D.
Si vous ne trouvez pas Exportation, vous pouvez la recréer vous-même : Cliquez sur la flèche à côté du menu de sélection, puis sur *«New»*.

![New](http://img4.hostingpics.net/pics/623252tuto24.png)


Déroulez ensuite la rubrique *« File Export »* dans *« Available Operations »* et double-cliquez sur *« Export C3D »*. Cliquez enfin sur le bouton lecture pour enregistrer l’acquisition.

![](http://img4.hostingpics.net/pics/959658tuto25.png)




