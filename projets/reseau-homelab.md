# Segmentation réseau et administration du homelab

**Contexte :** infrastructure personnelle, utilisée et enrichie au quotidien.

## Besoin
Organiser les équipements selon leurs usages et contrôler les communications entre postes, objets connectés, invités, caméras, serveurs et environnement de laboratoire.

## Mise en œuvre
- Segmentation par VLAN et sous-réseaux dédiés.
- Administration de la passerelle, des commutateurs et des points d'accès avec Ubiquiti UniFi.
- Règles de filtrage entre les réseaux selon les besoins d'accès aux services.
- Accès distant par VPN WireGuard.
- Hébergement des VM et des services sur Proxmox, avec Home Assistant sur un équipement distinct.

## Démarche de dépannage
Le travail sur la redondance AD a notamment montré l'importance de vérifier les règles inter-réseaux, en complément de la configuration DNS des clients. Les tests et les corrections sont consignés pour garder une trace des choix d'architecture.

## Évolutions
La supervision et les sauvegardes restent des axes à approfondir et à documenter par des tests. La segmentation seule ne garantit pas la sécurité : le comportement dépend des règles et des flux effectivement autorisés.

Les adresses, accès et configurations détaillées ne sont pas publiés dans cette présentation.

**Technologies :** Ubiquiti UniFi · VLAN · VPN WireGuard · Proxmox · Windows Server · Debian.

[Retour au profil](../README.md)
