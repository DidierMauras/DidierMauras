# Redondance Active Directory et test de panne

**Contexte :** homelab personnel, dans le cadre de ma formation TSSR.

## Besoin
Maintenir l'authentification et la résolution DNS du domaine pendant l'arrêt d'un contrôleur de domaine.

## Mise en œuvre
- Ajout d'un deuxième contrôleur à un domaine Windows Server existant.
- Vérification des catalogues globaux, de la réplication et des partages SYSVOL/NETLOGON.
- Distribution des deux serveurs DNS aux clients.
- Vérification des communications entre le réseau des clients et celui des serveurs.

## Incident rencontré
Un client connaissait les deux DNS mais une règle de filtrage n'autorisait que le premier contrôleur. Le diagnostic a rapproché les délais de résolution DNS, l'échec de découverte du domaine et les règles réseau. L'autorisation du deuxième contrôleur a rétabli les communications.

## Résultats vérifiés
- Ouverture d'une première session avec un compte de test pendant l'arrêt du premier contrôleur, pour éviter de confondre authentification réelle et identifiants en cache.
- Contrôleur utilisé confirmé par LOGONSERVER.
- Accès RDP validé et GPO consultable depuis le second contrôleur.
- Réplication sans erreur dans les deux sens après remise en service.

## Limites
Les deux VM résident sur le même hôte Proxmox : ce test couvre l'arrêt d'un contrôleur, pas la panne de l'hôte. Il ne constitue pas un plan de reprise complet. La consultation de la GPO ne prouve pas à elle seule sa réapplication sur le client ; la réplication ne remplace pas une sauvegarde.

**Technologies :** Windows Server · Active Directory · DNS · Proxmox · UniFi.

[Retour au profil](../README.md)
