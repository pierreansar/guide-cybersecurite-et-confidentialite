# Nettoyer Windows : Confidentialité et Optimisation

> ⚠️ **Avertissement** : Les modifications présentées ici touchent au registre et aux services profonds de Windows. Par sécurité, créez toujours un **[point de restauration](https://www.it-connect.fr/comment-creer-restaurer-et-supprimer-point-de-restauration-windows-11/)** avant d'appliquer ces changements.

Quand vous installez Windows 10 ou 11, il y a par défaut de nombreux services de collecte de données (télémétrie), des publicités ciblées et des applications préinstallées inutiles
L'objectif de ce guide est de reprendre le contrôle de votre système pour le rendre plus privé, plus léger et plus réactif.

> L'outil recommandé pour automatiser ces tâches est **[Chris Titus Tech's Windows Utility](https://github.com/ChrisTitusTech/winutil)**. Il a une interface graphique contrairement à d'autres outils et permet de cocher simplement les cases correspondant aux actions ci-dessous.
>
> **Commande PowerShell (Admin) pour le lancer :** `iwr -useb https://christitus.com/win | iex`

---

## 1. Compte Utilisateur (Fondamental)

L'utilisation d'un compte Microsoft lie votre identité numérique, vos fichiers (OneDrive) et votre clé BitLocker aux serveurs de Microsoft. Pour une confidentialité maximale, privilégiez toujours l'usage d'un **compte local**.

- **Installation sans Internet** : Lors de l'installation de Windows 11, utilisez la commande `OOBE\BYPASSNRO` dans le terminal (Shift + F10) pour pouvoir créer un compte local hors ligne.
- **Conversion** : Si vous êtes déjà connecté, allez dans _Paramètres > Comptes > Vos informations_ et choisissez "Se connecter plutôt avec un compte local".
  > ⚠️ **Attention BitLocker** : si le chiffrement de lecteur est activé, sauvegardez votre **clé de récupération** (clé USB ou impression papier) avant de déconnecter le compte Microsoft.

## 2. Vie Privée et Télémétrie (Priorité Absolue)

Windows utilise massivement la télémétrie (collecte de données à distance), la base de la confidentialité sur Windows consiste à désactiver cela. Les réglages suivants visent à stopper l'envoi de vos données d'usage à Microsoft et à ses partenaires publicitaires.

- **Désactiver la télémétrie et le suivi** : Coupe l'envoi des données de diagnostic et l'historique d'activité.
- **Bloquer les suggestions et publicités** : Windows affiche des publicités dans le menu Démarrer, l'écran de verrouillage, les Paramètres et l'explorateur. Il est crucial de désactiver :
  - Les "conseils et astuces" (Tips & Tricks).
  - Le flux d'actualités MSN dans Edge.
  - "Windows à la une" (Spotlight) sur le bureau.
- **Réduire les parasites** : Désactiver les widgets Météo/Actualités qui sont des vecteurs de tracking et de distraction.

## 3. Intelligence Artificielle et Recherche (Critique)

Avec Windows 11, Microsoft intègre l'IA (Copilot) au cœur du système, ce qui pose de nouveaux problèmes majeurs de confidentialité.

- **Désactiver Windows Recall (W11)** : **Crucial.** Cette fonctionnalité prend des captures d'écran de votre activité toutes les quelques secondes pour permettre une recherche à base d'IA. Elle est à désactiver impérativement d'un point de vue de la confidentialité.
  - Note : Recall est surtout présent/activé par défaut sur les **PC "Copilot+"** dotés d'un **NPU**. Mais le désactiver préventivement ailleurs est une bonne pratique.
- **Supprimer Bing & Copilot** : La recherche Windows locale ne doit pas envoyer vos requêtes sur le web.
  - Désactiver Bing dans la barre de recherche.
  - Désactiver Microsoft Copilot et l'analyse d'image/texte par IA.
  - Désactiver l'intégration IA dans les apps système (Notepad, Paint, Edge).

## 4. Nettoyage et Applications (Performance)

Beaucoup d'applications installées par défaut sont inutiles et un système sain est un système léger.

- **Navigateur Web** : Edge est intrusif. Installez **Firefox**, **LibreWolf** ou **Brave** et ajoutez l'extension **uBlock Origin** pour bloquer les traceurs publicitaires ainsi que les scripts de suivi.
- **App Removal (Debloat)** : Suppression massive des applications préinstallées inutiles (bloatware) qui tournent en arrière-plan.
- **Menu Démarrer épuré** :
  - Supprimer les applications épinglées par défaut (W11).
  - Désactiver la section "Recommandé" (fichiers récents/pubs) pour un menu propre.
  - Désactiver l'intégration des appareils mobiles (Phone Link) si non utilisée.

## 5. Interface et Ergonomie (Confort & Sécurité)

Ces réglages améliorent l'utilisabilité et la sécurité.

### Explorateur de fichiers (Sécurité)

- **Afficher les extensions de fichiers** : **Indispensable.** Permet de distinguer un vrai document (`facture.pdf`) d'un virus camouflé (`facture.pdf.exe`).
- **Afficher les fichiers cachés** : Pour voir tout ce qui se trouve réellement sur vos disques.
- **Nettoyer la navigation** : Masquer les doublons de lecteurs amovibles, la section "Galerie" ou "OneDrive" si non utilisés.

### Barre des tâches et système

- **Alignement à gauche (W11)** : Rétablit l'ergonomie classique du menu Démarrer.
- **Menu contextuel (clic droit)** : Rétablit le menu complet de Windows 10 (fini l'option "Afficher plus d'options").
- **Confort visuel** : Activer le mode sombre (Dark Mode) et désactiver les effets de transparence/animations pour plus de réactivité.

## 6. Optimisations Diverses

- **Xbox Game Bar** : Si vous ne jouez pas ou n'utilisez pas ses fonctions sociales, désactivez-la pour libérer des ressources et stopper l'overlay.
- **Désactiver "Fast Startup"** : Le démarrage rapide est en réalité une veille prolongée (hibernation). Le désactiver permet d'éteindre _réellement_ le PC, réglant souvent des bugs de pilotes.
- **Mouse Acceleration** : Désactiver "Enhance Pointer Precision" pour une souris plus précise (c'est le logiciel qui extrapole le mouvement).
- **Sticky Keys** : Désactiver le raccourci (5 fois Maj) qui interrompt souvent l'activité par accident.

- **DNS privés** : Configurez des DNS respectueux de la vie privée (par ex. **Quad9** 9.9.9.9 / **NextDNS**) pour bloquer pubs et traceurs au niveau réseau (Paramètres > Réseau et Internet > Propriétés de l'adaptateur > DNS).

> ℹ️ **Mises à jour Windows** : les mises à jour majeures (Feature Updates) réactivent parfois certains réglages. Après chaque grosse mise à jour, relancez **WinUtil** pour réappliquer vos préférences.

---

## Sources

- [GitHub - Chris Titus Tech's Windows Utility](https://github.com/ChrisTitusTech/winutil)
- [O&O ShutUp10++ (Alternative gratuite)](https://www.oo-software.com/en/shutup10)
- [Microsoft - Windows 11 Privacy](https://privacy.microsoft.com/en-us/privacystatement)
- [uBlock Origin (gorhill)](https://github.com/gorhill/uBlock)
- [Quad9 DNS](https://www.quad9.net/)
- [NextDNS](https://nextdns.io/)
- [Microsoft - BitLocker: overview](https://learn.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
