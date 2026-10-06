# LiveCam 0.11.2

Version du 6 octobre 2026.

LiveCam se rouvre bien plus vite une fois la mise à jour acceptée, il propose et garde votre micro de façon plus fiable, et pendant un appel, il décrit plus justement les problèmes de connexion et vous permet de relancer votre visage quand le service de visage est très demandé.

### Modifications

#### Appels

- Quand toutes les sessions de visage disponibles pour LiveCam restent occupées après quelques minutes d'essais, l'appel propose maintenant « Réessayer » pour relancer votre visage sans arrêter l'appel, au lieu de vous demander de relancer l'appel.

### Corrections

#### Appels

- Après une coupure du réseau pendant un appel, LiveCam n'indique plus l'absence de connexion internet une fois la connexion revenue : pendant qu'il reconnecte votre visage, il indique que la connexion est instable.
- Quand la connexion vidéo du visage reste bloquée pendant une minute au cours d'un appel, LiveCam indique maintenant qu'il reconnecte votre visage au lieu d'annoncer une absence de connexion internet, et ne signale une connexion perdue qu'après l'avoir vérifié.

#### Voix

- Une voix qui compte dans votre limite (le « Clonage complet », le passage d'une voix instantanée au clonage complet ou une nouvelle tentative pour une voix en échec) attend maintenant que LiveCam ait vérifié que cet ordinateur peut l'utiliser. Si cette vérification ne fonctionne pas, LiveCam le signale, et « Réessayer » la relance. En attendant, la fenêtre d'ajout s'ouvre sur le « Clonage instantané », gratuit, qui reste possible, téléchargement compris ; si cet ordinateur ne peut finalement pas utiliser cette voix, LiveCam le signale au démarrage de la voix.
- La configuration du son démarre maintenant sur le micro que Windows utilise par défaut, même quand son nom est long (comme le micro intégré de nombreux ordinateurs portables), au lieu d'un autre micro de la liste. Il en va de même pour le casque ou les haut-parleurs proposés pour écouter le test de la voix.
- Le câble virtuel qui transmet votre voix aux appels apparaît aussi comme un micro, qui ne fait que renvoyer la voix de LiveCam. Ce micro est maintenant reconnu sous tous les noms que lui donne Windows : la liste des micros ne le propose plus sur un ordinateur dont les micros portent des noms inhabituels. Un micro enregistré par une version précédente qui est en fait ce câble n'est plus indiqué comme absent dans Voix, dans la configuration du son et avant le direct : LiveCam l'oublie, le micro affiche « À choisir » et la configuration démarre sur l'un des micros de l'ordinateur.
- Sur un ordinateur sans micro, la configuration de la voix ne propose plus ce câble comme micro, et ne le garde plus quand une version précédente l'avait choisi ainsi. Elle indique maintenant qu'aucun micro n'a été trouvé.

#### Installation, mises à jour et licence

- Une fois que vous avez accepté la demande de Windows pour la mise à jour, LiveCam se rouvre bien plus vite : la mise à jour se décompresse maintenant en quelques secondes, et l'attente sans rien à l'écran passe d'environ une demi-minute à une dizaine de secondes. Le téléchargement de la mise à jour est un peu plus lourd.
- Quand une mise à jour ne peut pas être installée, LiveCam en donne maintenant la raison sur la ligne de la mise à jour dans Paramètres (ou sur l'écran « Mettez LiveCam à jour ») et dans le bandeau de mise à jour du tableau de bord, au lieu de l'afficher aussi dans une notification. Quand la demande de Windows pour installer la mise à jour est refusée ou reste sans réponse, cette ligne indique maintenant que la mise à jour n'a pas été installée et comment réessayer, au lieu de dire que l'installation a été annulée.
- Une réponse à la vérification de la licence qui ne vient pas du service de licence de LiveCam, comme la page d'un proxy d'entreprise, compte maintenant comme un problème de connexion : la licence continue de fonctionner hors ligne pendant le délai de grâce habituel. Avant, une telle réponse « mise à jour requise » demandait une mise à jour inutile, et une page anormalement volumineuse arrêtait l'appel et bloquait LiveCam.

---

Le programme d'installation ci-dessus est le seul fichier à télécharger. Les archives « Source code » sont ajoutées automatiquement par GitHub et ne contiennent pas LiveCam.
