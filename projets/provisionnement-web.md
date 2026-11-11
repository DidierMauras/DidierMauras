# Automatisation d'un environnement Web Debian

**Contexte :** travaux pratiques TSSR sous Debian, avec Apache, PHP, MariaDB et vsftpd.

## Besoin
Automatiser la préparation d'un environnement Web par utilisateur, puis disposer de l'opération inverse pour nettoyer le laboratoire.

## Mise en œuvre
- Script Bash de création du compte, de l'arborescence du site et des répertoires associés.
- Création d'une base MariaDB et de son utilisateur SQL.
- Génération de la configuration PHP et d'une page de vérification PDO.
- Génération d'un VirtualHost Apache à partir d'un modèle et configuration de l'accès FTP du TP.
- Script de suppression des ressources associées.

## Vérifications
Les échanges du TP ont validé la création d'un utilisateur Web, puis sa suppression. Lors de l'archivage, la syntaxe Bash des scripts a été vérifiée sans exécuter de provisionnement.

## Limites
Il s'agit d'un montage de laboratoire. Le remappage FTP et l'identité Web commune ne fournissent pas d'isolation entre les applications. La suppression inclut la base et les sauvegardes locales du site ; l'arrêt à la première erreur ne constitue pas un mécanisme de retour arrière.

Le code et les paramètres du TP sont conservés dans un dépôt privé. Cette fiche publique décrit la démarche et les résultats.

**Technologies :** Bash · Debian · Apache · PHP/PDO · MariaDB · vsftpd.

[Retour au profil](../README.md)
