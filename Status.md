  Indication
-    ✔️ = Fait
-    ❌ = Pas réussi


---

 4 - Configuration matérielle
  4.1 - Support matériel
  - [R1] Choisir et configurer son matériel : status = ✔️ ( manuellement )
  4.2 - BIOS/UEFI
  - [R2] Configurer le BIOS/UEFI : status = ✔️ ( capture BIOS ) mettre R2 et R3 ensemble
  4.3 - Démarrage sécurisé UEFI
   4.3.1 - Clés préchargées
  - [R3] Activer le démarrage sécurisé UEFI : status = ✔️  mettre R2 et R3 ensemble
   4.3.2 - Nouvelles clés
  - [R4] Remplacer les clés préchargées : status = ✔️

---

 5 - Configuration du noyau Linux
  5.2 - Configuration dynamique
  - [R6] Protéger les paramètres de ligne de commande du noyau et l'initramfs : status = ✔️
   5.2.1 - Configuration de la mémoire
  - [R7] Activer l'IOMMU : status = ✔️
   5.2.2 - Configuration du noyau
  - [R10] Désactiver le chargement des modules noyau : status = ✔️
   5.2.3 - Configuration des processus
  - [R11] Activer et configurer le LSM Yama : status = ✔️
   5.2.4 - Configuration du réseau
  - [R13] Désactiver le plan IPv6 : status = ❌
6 - Configuration système
  6.2 - Comptes d'accès
    6.2.3 - Comptes de service
    - [R34] Désactiver les comptes de service : status = ✔️
  6.3 - Contrôle d'accès
    6.3.1 - Modèle traditionnel Unix
    - [R36] Modifier la valeur par défaut de UMASK : status = ✔️
  6.5 - Gestion des paquets
  - [R58] N'installer que les paquets strictement nécessaires : status = ✔️
  - [R59] Utiliser des dépôts de paquets de confiance : status = ✔️
   6.6 - Veille et maintenance
  - [R61] Effectuer des mises à jour régulières : status = ✔️
  7 - Configuration des services
  - [R62] Désactiver les services non nécessaires : status = ✔️
  - [R63] Désactiver les fonctionnalités des services non essentielles : status = ✔️
---

 7 - Configuration des services
  - [R62] Désactiver les services non nécessaires : status = ✔️
  - [R63] Désactiver les fonctionnalités des services non essentielles : status = ✔️
  7.1 - Cloisonnement
  - [R65] Cloisonner les services : status = ✔️ | 🔜 (Podman)
  - [R66] Durcir les composants de cloisonnement : status = ✔️ | 🔜 (Podman)
   7.2.2 - Name Service Switch ou service de gestion de noms
  - [R69] Sécuriser les accès aux bases utilisateur distantes : status = ❌ | 🔜 (Config OpenSSH)