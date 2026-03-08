## Du MCD au Modèle Relationnel 
> Cours complet sur la méthode MERISE et l'interrogation SQL d'une base SQLite à partir d'un exemple.

## Contenu
Un **modèle conceptuel de données (MCD)** est une représentation abstraite, visuelle et simplifiée de l’ensemble des données d’un **système d’information**. Conçu pour **faciliter la compréhension des relations entre les différents types de données d’un système donné**, le MCD s’affranchit des détails techniques (liés à l’enregistrement des données et à leur stockage par exemple) **pour se concentrer sur la structure logique des informations**. C’est pour cela qu’on utilise l’adjectif « conceptuel » pour caractériser ce modèle.
- **Modèle Conceptuel des Données (MCD)** : entités, attributs, associations, cardinalités
- Transformation en **modèle relationnel** (3 règles)
- **Script SQL** de création des tables
- 10 **requêtes SQL** commentées (du SELECT simple aux jointures multiples)

## Modèle relationnel

```
Celui de notre exemple se présente ainsi :

CLIENT     (id_client, numeroClient, nom, prenom, adresseMail, dateInscription, adresse)
COMMANDE   (id_commande, dateCommande, #id_client)
CATEGORIE  (id_categorie, nom)
PRODUIT    (id_produit, nom, prix, #id_categorie)
ASSEMBLER  (#id_commande, #id_produit, qte)
```

## Règles de transformation MCD → Relationnel

| Type d'association | Cardinalités | Résultat |
|--------------------|--------------|----------|
| Un-à-plusieurs (1:N) | 1 d'un côté, N de l'autre | Clé étrangère (FK) |
| Plusieurs-à-plusieurs (N:M) | N des deux côtés | Table de jonction |
#
On distingue trois catégories d'associations selon les cardinalités maximales de leurs branches :
#
► **Associations hiérarchiques** (ou fonctionnelles) : notées [1, n]
#
► **Associations non hiérarchiques** (ou non fonctionnelles) : notées [n, n]
#
► **Associations [1, 1]** : les deux branches ont une cardinalité maximale de 1 — cas rare
#
## Requêtes SQL
#
On limitera le nombre de requêtes à 10.
#
|  | Intitulé | Notions |
|---|----------|---------|
| 1 | Liste des clients | `SELECT *` |
| 2 | Liste des produits | `SELECT *` |
| 3 | Liste des catégories | `SELECT *` |
| 4 | Commandes triées par date | `ORDER BY` |
| 5 | Produits > 500 € | `WHERE` |
| 6 | Nombre de produits par catégorie | `GROUP BY`, `COUNT` |
| 7 | Clients et leurs commandes | `JOIN` |
| 8 | Détail commandes avec produits | Double `JOIN` |
| 9 | Montant total par commande | `SUM`, `GROUP BY` |
| 10 | Dépenses par client et catégorie | 4 `JOIN`, `SUM` |

## Fichiers

- `commandes.db` — base SQLite
- cours_MCD_modele_relationnel.pdf — Le cours

## Licence
Libre - Servez-vous

## Auteur
👤 Auteur : SERRES Régis - Lycée E de Constant, La Flèche (72) - https://serres-regis-prof-estournelles.github.io/
