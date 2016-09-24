#TD Hiérarchie et Tableau CRUD

On va faire un petit exercice, on va designer une structure d'API REST.

## Énoncé :

On va avoir pour cela prendre la hiérachie suivante (exemple du blog):  
> 
- Chaque article à un auteur  
- Chaque article peut être commenté  
- Chaque article à une ou plusieures images  
- Chaque image peut être commentée   
  
![Hiérarchie](/Image/hierar.png)

## Les différents tableaux :

Dans la partie suivante, on va avoir les tableaux répondant à cette structure
pour chaque objet.

##L'objet Auteur

Voici le tableau décrivant les auteurs. On note *ida* l'id de l'auteur

| Operation | Verb   | URI            | Description |
| --------- | ------ | -------------- | ----------- |
| Read(all) | GET    | /auteurs       | On récupère tout les auteurs.
| Create    | POST   | /auteurs       | On créer un nouvel auteur.
| Read      | GET    | /auteurs/*ida* | On récupère l'auteur d'identifiant *ida*.
| Update    | PUT    | /auteurs/*ida* | On met à jour l'auteur d'identifiant *ida*.
| Destroy   | DELETE | /auteurs/*ida* | On supprime l'auteur d'identifiant *ida*.

### L'objet article

Voici le tableau relatif aux articles. On note *ida* l'auteur et *id* l'article.

| Operation | Verb   | URI                          | Description |
| --------- | ------ | ---------------------------- | ----------- |
| Read(all) | GET    | /auteurs/*ida*/articles      | On récupère tout les articles.
| Create    | POST   | /auteurs/*ida*/articles      | On créer un nouvel article.
| Read      | GET    | /auteurs/*ida*/articles/*id* | On récupère l'article d'identifiant *id*.
| Update    | PUT    | /auteurs/*ida*/articles/*id* | On met à jour l'article d'identifiant *id*.
| Destroy   | DELETE | /auteurs/*ida*/articles/*id* | On supprime l'article d'identifiant *id*.

### L'objet commentaire d'article

Ce tableau décrit le comportement de l'API pour les commentaires d'articles.
On note *ida* l'auteur, *id* l'article et *idc* l'identifiant du commentaire.

| Operation | Verb   | URI                                         | Description |
| --------- | ------ | ------------------------------------------- | ----------- |
| Read(all) | GET    | /auteurs/*ida*/articles/*id*/comments       | On récupère tout les commentaire de l'article *id* de l'auteur *ida*.
| Create    | POST   | /auteurs/*ida*/articles/*id*/comments       | On créer un nouveau commentaire pour l'article *id* de l'auteur *ida*.
| Read      | GET    | /auteurs/*ida*/articles/*id*/comments/*idc* | On récupère le commentaire *idc* de l'article d'identifiant *id* de l'auteur *ida*.
| Update    | PUT    | /auteurs/*ida*/articles/*id*/comments/*idc* | On met à jour le commentaire *idc* de l'article d'identifiant *id* de l'auteur *ida*.
| Destroy   | DELETE | /auteurs/*ida*/articles/*id*/comments/*idc* | On supprime le commentaire *idc* de l'article d'identifiant *id* de l'auteur *ida*.


### L'objet image

Ce tableau décrit le comportement de l'API pour notre objet image. On note *ida* l'auteur, *id* le
commentaire et *idi* l'image.

| Operation | Verb   | URI                                       | Description |
| --------- | ------ | ----------------------------------------- | ----------- |
| Read(all) | GET    | /auteurs/*ida*/articles/*id*/images       | On récupère tout les images de l'article *id* de l'auteur *ida*.
| Create    | POST   | /auteurs/*ida*/articles/*id*/images       | On attache une nouvelle image à l'article *id* de l'auteur *ida*.
| Read      | GET    | /auteurs/*ida*/articles/*id*/images/*idi* | On récupère l'image *idi* de l'article d'identifiant *id* de l'auteur *ida*.
| Update    | PUT    | /auteurs/*ida*/articles/*id*/images/*idi* | On met à jour l'image *idi* de l'article d'identifiant *id* de l'auteur *ida*.
| Destroy   | DELETE | /auteurs/*ida*/articles/*id*/images/*idi* | On supprime l'image *idi* de l'article d'identifiant *id* de l'auteur *ida*.


### L'objet commentaire d'image

Ce tableau décrit le comportement de l'API pour les commentaires des images. On note
toujours *ida* l'auteur, *id* l'article, *idi* l'image du commentaire et *idci* le commentaire de l'image.

| Operation | Verb   | URI                                                       | Description |
| --------- | ------ | --------------------------------------------------------- | ----------- |
| Read(all) | GET    | /auteurs/*ida*/articles/*id*/images/*idi*/comments        | On récupère tout les commentaire de l'image *idi* de l'article *id* de l'auteur *ida*.
| Create    | POST   | /auteurs/*ida*/articles/*id*/images/*idi*/comments        | On créer un nouveau commentaire pour l'image *idi* pour l'article *id* de l'auteur *ida*.
| Read      | GET    | /auteurs/*ida*/articles/*id*/images/*idi*/comments/*idci* | On récupère le commentaire *idci* pour l'image *idi* de l'article d'identifiant *id* de l'auteur *ida*. 
| Update    | PUT    | /auteurs/*ida*/articles/*id*/images/*idi*/comments/*idci* | On met à jour le commentaire *idci* de l'image *idi* de l'article d'identifiant *id* de l'auteur *ida*.
| Destroy   | DELETE | /auteurs/*ida*/articles/*id*/images/*idi*/comments/*idci* | On supprime le commentaire *idci* de l'image *idi* de l'article d'identifiant *id* de l'auteur *ida*.
