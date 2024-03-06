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

 Vous allez devoir commencer par installer les JDK de Java. Pour cela vous avez juste à lancer l'exécutable "jdk-21_windows-x64_bin.exe" sur votre poste.
 Assurez-vous qu'une fois l'installation terminée que les variables d'environnements se sont bien ajoutées. Pour cela : Touche Windows, "Environnement" et vous regardez si une ligne JAVA_PATH s'est bien ajoutée.

## Étape 2 :

 Par la suite, il vous faudra installer les SDK Tools Android.
 Rien de plus simple, vous récupérez l'archive "cmd_tools_SDK", positionnez vous dans votre disque C depuis l'explorateur de fichiers windows,
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
 Rendez vous dans le gestionnaire de variable d'environnement, et ajouter dans la variable "Path" les lignes suivantes "C:\Android\sdk\cmdline-tools\latest\bin", "C:\Android\sdk\emulator"


Fermez tous les terminal ouverts. Réouvrez en un et lancez la commande suivante "sdkmanager" normalement toute la liste des commandes accessibles depuis sdkmanager devraient être visibles.

Par la suite faire "sdkmanager --licenses" et accepter la totalité avec "y".
Faire : 
- sdkmanager "platform-tools"
- sdkmanager "build-tools;30.0.3"
- sdkmanager "platforms;android-30"

Félicitation vous avez désormais tout entre vos mains pour virtualiser des appareils Android et tester vos futures applications !

## Étape 3 :

Il faut installer avant toute chose le gestionnaire de package Node, allez sur le site de Node directement et installez la dernière version (Latest).


Désormais, il faut nstaller React Native, depuis un terminal faites les commandes suivantes :

- npm install -g react-native-cli
- npx react-native init MonProjet

Choisissez parmi les 3 options celle qui vous convient le mieux (je recommande celle avec l'application de test pour tester le bon fonctionnement (Option 3))

## Étape 4 :

Installer un émulateur :
- sdkmanager "system-images;android-30;default;x86_64"
- avdmanager create avd -n nom_de_l_avd -k "system-images;android-30;default;x86_64"

Pour lancer l'émulateur il suffit de faire : emulator -avd nom_de_l_avd












