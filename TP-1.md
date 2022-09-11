# **Exercice 2 : Prise en main de l'interpréteur de commande**

## *Manuel*

1 - La commande **which** permet de localiser une commande, un binaire.

2 - Lorsque l'on consulte une page du manuel, pour chercher un terme il suffit de saisir la commande **man** 

3 - Afin de sortir du manuel, il faut presser la touche 'q'.

4 - La première page de la section 6 concerne les jeux, économiseurs d’écran, gadgets...

## *Navigation dans l’arborescence des fichiers*

1 - Pour aller dans un dossier : "cd [directory]"; ici : **cd /var/log**.

2 - Pareil que la question précédente : **cd /var** ou **cd..**.

3 - Le retour dans le dossier personnel se fait avec **cd**.

4 - Sans utiliser de chemin, pour revenir au dossier précédent, il faut utiliser la commande **cd -**

5 - L'accès au dossier /root est refusé.

6 - La commande **sudo cd /root** ne fonctionne pas. Cela s'explique par le fait que la commande **cd** est intégrée dans le shell tandis que **sudo** ne fonctionne qu'avec les executables.

7 - 
* D'abord la création des deux dossiers : **mkdir Dossier1** et **mkdir Dossier2**
* entrer dans le Dossier1 avec **cd Dossier1** puis créer le Fichier1 avec **touch Fichier1**
* sortir du Dossier1 avec **cd ..**
* entrer dans Dossier2 avec **cd Dossier2** puis créer les deux sous-dossiers : **mkdir Dossier2.1**, **mkdir Dossier2.2**
* entrer dans Dossier2.2 avec **cd Dossier2.2** puis créer les fichiers : **touch Fichier2.txt**, **touch Fichier3.txt**

8 - Avec la commande **rm Dossier1/Fichier1.txt** on peut supprimer le fichier. Nonobstant, supprimer le Dossier1 avec **rm Dossier1** ne fonctionne pas (car c'est un dossier).

9 - Pour supprimer un dossier, il faut alors ajouter l'option -r à la commande : **rm -r Dossier1**.

10 - Elle appliquant la commande précédente pour le Dossier2, **rm -r Dossier2**, cela va supprimer le Dossier2 y compris tous ses sous-dossiers et fichiers.

11 - (même réponse que la question précédente : **rm -r Dossier2**).

## *Commandes importantes*

1 - La commande **date** permet d'afficher la date, y compris l'heure. **time** affiche des informations sur les ressources utilisées par COMMAND.

2 - Les noms des fichiers précédés par un point, peut se traduire par le fait que les fichiers sont des éléments masqués.

3 - La commande **ls** se trouve ici : /usr/bin/.

4 - Il n'existe aucune entrée de manuel pour cette commande **ll**. En effet, cette commande est un alias pour une autre commande : **ls -alF**.

5 - Pour afficher le contenu du dossier /bin : ****ls /bin**.

6 - **ls** liste les fichiers/sous-dossiers d'un dossier.

7 - Pour avoir le chemin complet du dossier courrant : **pwd**.

8 - Création d'un fichier nommé plop avec à l'intérieur écrit bip. La première exécution va créer le fichier et écrire à l'intérieur. La seconde va réécrire le fichier.

9 - A contrario de **echo "bip" > plop**, **echo "bip" >> plop** va écrire bip à la suite du même fichier sans l'écraser.

10 - Un temps d'attente de 10 secondes va se lancer et 'toto' va s'afficher dans la console.

11 - **file** determine le type d'un fichier (indépendamment de son extension). Elle affiche son contenu.

12 - lien_phy et original possèdent le même contenu. En supprimant le fichier 'original', lien_phy va prendre la place de ce dernier en gardant son contenu (car lien_phy agit comme une copie synchronisée de 'original').

13 - Une modification apportée à lien_phy est également appliquée sur lien_sym, et inversement. La suppression de lien_phy conduit à la suppression de lien_sym (car lien_sym agit comme un raccourci pour lien_phy).

14 - En affichant le fichier /var/log/syslog, un défilement trop verbeux commence. Il est néanmoins possible de l'interrompre avec la commande **CTRL + S** puis le reprendre avec  **CTRL + Q** (personnellement, uniquement **CTRL** permet de reprendre ce défilement).

15 - Pour afficher les 5 premières lignes du fichier /var/log/syslog : **head -5 /var/log/syslog**; (**head -n 5 /var/log/syslog** fonctionne également)
Pour afficher les 15 dernières lignes du fichier /var/log/syslog : **tail -15 /var/log/syslog**;
Pour afficher les lignes 10 à 20 du fichier /var/log/syslog : **???**.

16 - La commande **dmesg | less** va relier la sortie de dmesg (commande qui permet d'examiner ou contrôler le tampon circulaire du noyau) à l'entrée de less (commande qui permet d'afficher un fichier page par page). En d'autres terme, cela va permettre d'examiner le tampon circulaire du noyau mais en gérant en quelque sorte la cadance du défilement.

17 - Le fichier /etc/passwd contient différentes informations sur les comptes utilisateurs. On peut retrouver:
* le nom de connexion de l'utilisateur
* un mot de passe chiffré optionnel
* l'identifiant numérique de l'utilisateur
* l'identifiant numérique du groupe de l'utilisateur
* le nom complet de l'utilisateur ou un champ de commentaires
* le répertoire personnel de l'utilisateur
* l'interpréteur de commande de l'utilisateur
Pour afficher la page de manuel de /etc/passwd : **man 5 passwd**.

18 - **cut -d ":" -f 1 /etc/password | sort -r**. En effet, **cut -d ":" -f 1 /etc/passwd** permet de couper chaque ligne de sortie du fichier /etc/passwd jusqu'au délimiteur ":". Ensuite, la sortie de cette commande est redirigé en entrée de la seconde, **sort -r**, qui va à son tour trier dans l'ordre décroissant.

19 - En tapant la commande **wc -l /etc/passwd**, on peut obtenir le nombre de lignes et de ce fait le nombre d'utilisateur ayant un compte sur la machine.

20 - On recherche d'abord les pages contenant le mot *conversion* dans leur description puis on compte : **man -k conversion | wc -l**.

21 - On peut trouver tous les fichiers nommés 'passwd' présents sur la machine grâce à la commande : **sudo find / -type f -name passwd**.

22 - **sudo find / -type f -name passwd > list_passwd_files.txt 2>> /dev/null**

23 -

24 -

25 -

# **Exercice 3 : Découverte de l’éditeur de texte nano**

1 - On copie le fichier /var/log/syslog et on le colle dans notre dossier personnel avec la commande **cp -r /var/log/syslog log.txt**. **nano** pour lancer nano puis **CTRL + R** suivi du nom du fichier log.txt pour le lancer.

2 - Dans nano: ouverture du fichier log.txt avec **CTRL + R**; une fois ouvert on entre le mot (kernel) à remplacer avec **ALT + R**; puis on saisit le nouveau mot (noyau); enfin on presse 'A' pour remplacer toutes les occurences.

3 - D'abord, **ALT + A** pour placer un genre de marqueur au début du fichier. Ensuite on compte 10 lignes (en descendant avec la flèche du clavier) et on coupe les 10 premières lignes sélectionnées avec **CTRL + SHIFT + K**. Enfin, on se place à la fin du fichier puis on colle avec **CTRL + U**.

4 - Annuler cette action avec **ALT + U**.

5 - Avant de quitter nano, on enregistre le fichier avec **CTRL + S**.

# **Exercice 4. Personnalisation du shell**

1 - Copie du fichier .bashrc en .bashrc_bak : **cp -r .bashrc .bashrc_bak**.

2 -
* Ouverture du fichier dans nano : **CTRL + R** => .bashrc
* on se déplace dans le fichier puis on décommente la ligne force_prompt_color=yes
* Enregistrement du fichier : **CTRL + S**
* Sortie de nano : **CTRL + X**

3 - oui vert et bleu.

4 - **\[\033[35m\][\A]\[\033[00m\] - \[\033[01;32m\]\u@\h\[033[00m\]:\[\033[96m\]\w\[\033[00m\]\$** (pour afficher l'invite de commande sous la forme: heure affichée en violet et entre crochets, et le chemin du dossier courant en cyan)