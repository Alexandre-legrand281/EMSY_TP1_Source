# TP1 - Installation Linux sur une VM - V0.2
 
## Groupe
 
-Pouly Steeve/Dias Alexandre
 
## But
 
Cette manipulation a pour but d'installer une distribution linux [Sparky Linux](https://sparkylinux.org/) dans une machine virtuelle VMware Workstation Player, à l’aide d’une image disque (ISO).
 
## Materiels à disposition
 
- VMware Workstation Player - V17
- Image disque (ISO) : sparkylinux-6.4-x86_64-minimalcli.iso
 
## Utilisation de VMware et de l'image ISO linux
 
A. Lancez VMware Workstation Player (logiciel)  
 
B. Sélectionnez **Create a New Virtual Machine**
 
C. Placez le fichier `.iso` dans une repertoire connu :

`C:AOD`

D. Indiquez le chemin d’accès de l’image iso comme indiqué sous l’image ci-dessous :
 
![install image disk](/Images/Install_ISO.jpg)
 
E. Choisir un nom d'OS : `Linux - Debian 11.x`
 
![OS name choice](/Images/OS_Choice.jpg)
 
F. Nommez la machine virtuelle : `SparkyLinux-SPY-AOD`
 
G. Creez un disque virtuel -> capcité : **20GB**
 
> remarque$$^1$$ : cocher **store virtual disk a single file**
 
![Virtual disk](/Images/VirtualDisk.jpg)
 
> remarque$$^2$$ : ci-dessous, la configuration de la VM
 
![Virtual disk](/Images/VM_Config.jpg)
 
H. Lancez la machine virtuelle : **Play virtual machine**
 
## Lancement de l'image ISO (Linux - Live CD)
 
G. Lancement du live CD :
 
![Lancement_du_Live_CD](/Images/Lancement_du_live_CD.png)
 
Shell Linux :
 
![Shell_Linux](/Images/Shell_Linux.png)
 
> **ATTENTION** : par défaut, le clavier est configuré est **Clavier Americain**
 
Q1. disposition du clavier américain ?
 
> QWERTY
 
Q2. disposition du clavier suisse-romand ?
 
> QWERTZ
 
Q3. disposition du le clavier français ?
 
> AZERTY
 
 
H. Déplacez-vous à la **racine du système** en utilisant la commande suivante : `cd`
 
> cd /
 
I. Affichez le contenu de la racine avec la commande : `ls –l`	
 
![Racine_ls-l](/Images/Contenu_racine.png)
 
Q5. Que signifie l'option `-l` avec la commande `ls`

> c'est le format long de la commande ls, elle affiche les informations pour chaque fichier ou répertoire.
 
Q6. Décrypter la ligne où se trouve le répertoire **home**    
 
![Repertoire_home](/Images/Ligne_home.png)
 
> d = indicateur de type de fichier la on se trouve dans le répertoire

> rwx = privilège que peux avoir l'utilisateur sur ce répertoire, ici on peut lire(r) écrire(w) executer(x)

> r-x = privilège que le groupe peut avoir sur ce répertoire, ici on peut lire(r) impossible d'écrire(-) executer(x)

> r-x = privilège qu'un utilisateur partagé peut avoir su ce répertoire, ici on peut lire(r) impossible d'écrire(-) executer(x)

> 1 = Le nbr d'accès

> root = racine utilisateur

> root = racine groupe

> 60 = espace mémoire utilisée 60 Mo

> Sep 18 = date du dernier acces ou modif de ce répertoire, ici c'est le 18 Septembre

> 14:04 = heure selon la date du dernier acces ou modif de ce répertoire, ici c'est à 14H04

> home = nom du répertoire
 
J. Créez un répertoire de travail nommé « EMSY_VosInitiales» dans quel dossier racine allez-vous le placer (justifiez votre réponse) et quelle commande allez-vous utiliser.
 
> Dans le dossier home/live car on peut facilement y accéder et on arrive dessus lors du lancement de la machine virtuel.

> On utilise la commande "mkdir EMSY_SPY-AOD"
 
Q7. Si vous créez un répertoire de travail (pour éditer/sauvegarder des fichiers), dans quelle **répertoire racine** vous vous placez ?
 
> On le mettrait dans un répertoire qui n'est pas sensible à des erreurs de commande ou des suppressions telle le répertoire "home"
 
K. Dans ce répertoire, créez un fichier texte que vous nommerez `TESTSLO_XXX_XXX` et éditez celui en écrivant un texte, exemple : "TP linux by XXX et XXX".
	Utiliser la commande `vi`
 
> vi TESTSLO_SPY_AOD.txt
 
Q9. dans le répertoire `/home`, pouvez-vous éditez un fichier uniquement avec la commande `vi`
 
> il faut ajouter le format du fichier ".txt" à la suite du nom.
 
Q10. Si vous éteignez la machine virtuelle et que vous la rallumez, est-ce que le répertoire créé ci-dessus existe toujours (justifiez votre réponse) ?
 
> Non, car la machine virtuel est réinitialisé à son arret.
 
L. Tapez la commande `ls -l /dev/sda`
 
![Commande_ls_-l](/Images/Commande_ls-l_dev_sda.png)
 
Q11. Que signifie **sda** ?
 
> C'est la désignation actuelle pour désigner les disque dur, lors de l'installation linux donne le nom de sda au 1er disque dur.
 
Q12. Décrypter la réponse après avoir taper la commande `ls -l /dev/sda` -> voir résultat point 13.
 
> brw-rw----1 root disk 8,0 Sep 24 15:56 dev/sda
> b = indicateur de type de fichier la on se trouve dans le fichier bloc
> rw- = privilège que peux avoir l'utilisateur sur ce répertoire, ici on peut lire(r) écrire(w) impossible d'executer(-)
> rw- = privilège que le groupe peut avoir sur ce répertoire, ici on peut lire(r) écrire(w) impossible d'executer(-)
> --- = privilège qu'un utilisateur partagé peut avoir su ce répertoire, ici il est impossible de lire(-) impossible d'écrire(-) impossible executer(-)
> 1 = Le nbr d'accès.
> root = racine utilisateur.
> disk = block SCSI.
> 8 = numéro majeur, il indique le pilote utilisé gérer le matériel.
> 0 = numéro mineur, il est donné par le pilote pour distingué le matériel qu'il contrôle.

M. Pour cela, il faut lancer l'"Instaeller" fourni avec le live-cd. Pour vous aider à réaliser cette installation, regardez les pages Wiki de la distribution de Sparky (aide).
(https://wiki.sparkylinux.org/doku.php/start)

Q13. Quelle est la taille de disque minimum recommandée pour installer la distribution Sparky?

> Il est recommandée d'avoir au minimum 2Go

Partition 1: env.50% du disque (~10Go) -> Système de fichiers Linux

Partition 2: env.25% du disque (~5Go) -> Partition d'échange (swap)

Partition 3: le reste sera utilisé pour un système de fichiers dans un format Linux

Q14. A quoi sert la partition swap? Est-ce que ce principe existe sur les OS Microsoft Windows?

> Quand la RAM est saturée, le noyau Linux déplace certaines données peu utilisées vers la swap pour libèrer de la RAM pour les applications actives. Ce principe existe egalement sur les OS Microsoft Windows, mais Windows ne crée pas de partition swap

Q15. Quel format pourriez-vous utiliser pour la 3eme partition afin qu'elle soit également accessible depuis un OS Microsoft?

> exFAT

Q16. Durant l'installation, on vous demande deux noms d'utilisateur. A quoi correspondent-ils?

> Le premier nom est le nom de la machine et le deuxieme est le nom de l'utilisateur

N. Après l'installation de Linux, prenez une capture d'écran du démarrage de votre systéme (GRUB)

![Login_AOD](/Images/Login_AOD.png)

O. Trouvez la ou les lignes de commande permettant de changer le clavier (clavier suisse romand trouvable sous "German (Switzerland)" et procédez à la configuration du clavier.

> sudo loadkeys fr_CH-latin1
> sudo dpkg-reconfigure keyboard-configuration

P. Testez si l'application "nano" est installée sur votre machine, tapez la commande: nano -version

Q17. À quoi sert "nano"?

> Elle permet d'editer qui permet d'ouvrir et de modifier les fichiers .txt et peut egalement éditer des texts en ligne de commande

Q. Testez si l'application "git" est installée sur votre distribution, si ce n'est pas le cas installez un client git.

Q18. Comment savoir si "git" est déjà installé?

> apt list --installed | grep git

Q19. Quelle(s) commande(s) utilisez-vous pour l'installer?

> sudo apt install git

Q20. Que veut dire "apt"?

> Advanced Package Tool, c'est le gestionnaire de paquets avec une interface utilisateur de haut niveau basé sur dpkg

Q21. Est-ce que cette commande peut être utilisée sur toutes les distributions Linux?

>Non, la distribution Debian 2.0 ne puisse l'utiliser

R. Créez un sous-répertoire "EMSY_TP1_XXX-YYY" dans le répertoire de votre utilisateur.
ATTENTION: Ici on veut que l'utilisateur (vous) ait les droits de lecture, d'écriture et d'exécution.

Q22. Quel est le répertoire utilisateur?

> /home/aod

Q23. Quelles sont les commandes que vous allez utiliser?

> sudo mkdir EMSY_TP1_AOD

S. Dans ce répertoire, tapez la commande:
git clone https://github.com/votreDepot/EMSY_TP1_Source
Il faut préalable que vous ayez mis en place à cette adresse un fork du dépôt fourni.

Q24. Qu'observez-vous dans votre répertoire?

>

T. Editez le fichier source .c avec l'éditeur de texte "nano".
Réalisez un petit programme en C (par exemple de type "Hello world")

U. Vérifiez si le compilateur "gcc" est bien installé.
Notez la version du logiciel.
Tapez les commandes suivantes:
gcc -Wall -o fichier.o -c fichier.c
gcc -o fichier fichier.o
REMARQUE: "fichier" est à remplacer par le nom de votre choix

Q25. Quels sont les fichiers qui ont été générés?

V. Entrez la commande suivante:
./fichier

Q26. Que se passe-t-il?
 
## Tips
 
> $$Tips^1$$ : sortir de la VM -> appuyer simultanément sur `Ctrl` et `Alt`
 
> $$Tips^2$$ : arrêter la VM proprement -> commande : `shutdown`
 
> $$Tips^3$$ : arrêter la VM pour cause de plantage -> commande : `halt` ou `poweroff`
 
> $$Tips^4$$ : [commande vi avec ses options](https://www.linuxtricks.fr/wiki/guide-de-sur-vi-utilisation-de-vi)
 
> $$Tips^5$$ : [éditer un fichier type markdown (.md)](https://ashki23.github.io/markdown-latex.html)
