# React-Native-Install
Bienvenue sur le guide d'installation de React Native sur Windows 10/11.
À l'aide de ce tutoriel vous allez pouvoir utiliser le FrameWork React Native sans avoir à installer Android Studio.
Vous allez pouvoir utiliser VSCode pour l'intégralité du développement de votre solution.

## Prérequis :
 - Windows 10 / 11
 - Java JDK (Recommended version) :https://download.oracle.com/java/21/latest/jdk-21_windows-x64_bin.exe
 - SDK Tools Android : https://developer.android.com/studio#:~:text=commandlinetools%2Dwin%2D-,11076708_latest,-.zip
 - NodeJS : https://nodejs.org/en
 - VSCode
 - Des connaissances sur le système d'exploitation Windows

## Étape 1 :

 Vous allez devoir commencer par installer les JDK de Java. Pour cela vous avez juste à lancer l'exécutable "jdk-(version)_windows-x64_bin.exe" sur votre poste.
 Assurez-vous qu'une fois l'installation terminée que les variables d'environnements se sont bien ajoutées. Pour cela : Touche Windows, "Modifier les variables d'environnement système", vous aurez accès à une fenêtre avec plusieurs options vous cliquez sur le bouton "Variables d'environnement" et vous regardez si une ligne JAVA_PATH s'est bien ajoutée dans la partie du bas de la fenêtre "variable système".

## Étape 2 :

 Par la suite, il vous faudra installer les SDK Tools Android.
 Rien de plus simple, vous cliquez sur le lien que je vous ai mis à disposition en haut, vous allez tout en bas de la page et vous allez dans la section "SDK tools only", vous téléchargez l'archive. Une fois l'archive téléchargée, positionnez vous dans votre disque C depuis l'explorateur de fichiers windows,
 Créez un dossier "Android", mettez vous dedans. Créez un Dossier "sdk", mettez vous dedans, créez à nouveau un dossier "latest" et mettez les 4 éléments présent dans l'archive dans le dossier "latest".

 voici à quoi ça devrait ressembler :

 C:\Android\sdk\
└── cmdline-tools\
    └── latest\
        ├── bin\
        ├── lib\
        ├── NOTICE.txt
        └── source.properties

 Il faut par la suite ajouter la variable d'environnement permettant l'utilisation de SDKManager.
 Rendez vous dans le gestionnaire de variable d'environnement, et ajouter dans la variable "Path" les lignes suivantes "C:\Android\sdk\cmdline-tools\latest\bin", "C:\Android\sdk\emulator", "C:\Android\sdk\platform-tools" ⚠️ J'anticipe ici l'ajout de 2 variables d'environnement qui sont normalement à ajouter après le procéssus d'installation.


Fermez tous les terminal ouverts. Réouvrez en un et lancez la commande suivante "sdkmanager" normalement toute la liste des commandes accessibles depuis sdkmanager devraient être visibles.

Par la suite faire "sdkmanager --licenses" et accepter la totalité avec "y".
Faire : 
- sdkmanager "platform-tools"
- sdkmanager "build-tools;(version de l'appareil souhaité)"
- sdkmanager "platforms;android-(version de l'appareil souhaité)"

Félicitation vous avez désormais tout entre vos mains pour virtualiser des appareils Android et tester vos futures applications !

## Étape 3 :

Il faut installer avant toute chose le gestionnaire de package Node, allez sur le site de Node directement et installez la dernière version (Latest).


Désormais, il faut nstaller React Native, depuis un terminal faites les commandes suivantes :

- npm uninstall -g react-native-cli @react-native-community/cli (Désinstallation des précédentes versions pour ne pas avoir de conflits)
- npx react-native@latest init AwesomeProject

Vous avez maintenant un projet prêt à être utilisé !

Il vous faut désormais installer un émulateur !

## Étape 4 :

Installer un émulateur :
- sdkmanager "system-images;android-(Version de l'appareil souhaité);default;x86_64"
- avdmanager create avd -n nom_de_l_avd -k "system-images;android-(Version de l'appareil souhaité);default;x86_64"

Pour lancer l'émulateur il suffit de faire : emulator -avd nom_de_l_avd

## Étape 5 (Test) :

Pour tester le bon fonctionnement du projet :

- Ouvrir VSCode
- Se positionner dans le dossier du projet
- Lancer l'émulateur avec la commande "emulator -avd nom_de_l_avd" dans un autre terminal
- Lancer le projet et l'injecter sur l'émulateur avec la commande suivante "npx react-native run-android"


Félicitation ! Normalement tout devrait être bon pour faire usage de React Native sur un émulateur Android sans avoir à installer Android Studio !











