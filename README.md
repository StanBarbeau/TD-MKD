#TD Hiérarchie et Tableau CRUD

On va faire un petit exercice, on va designer une structure d'API REST.

## Énoncé :

On va avoir pour cela prendre la hiérachie suivante (exemple du blog):  
> 
- Chaque article à un auteur  
- Chaque article peut être commenté  
- Chaque article à une ou plusieures images  
- Chaque image peut être commentée  

## Les différents tableaux :

Dans la partie suivante, on va avoir les tableaux répondant à cette structure
pour chaque objet.

### L'objet article

Voici le tableau relatif aux articles. On note *id* l'identifiant
de l'article.

| Operation | Verb   | URI            | Description |
| --------- | ------ | -------------- | ----------- |
| Read(all) | GET    | /articles      |
| Create    | POST   | /articles      |
| Read      | GET    | /articles/*id* |
| Update    | PUT    | /articles/*id* |
| Destroy   | DELETE | /articles/*id* |

### L'objet commentaire d'article

| Operation | Verb | URI | Description |
| --------- | ---- | --- | ----------- |
|
|
|
|

### L'objet image

| Operation | Verb | URI | Description |
| --------- | ---- | --- | ----------- |
|
|
|
|

### L'objet commentaire d'image

| Operation | Verb | URI | Description |
| --------- | ---- | --- | ----------- |
|
|
|
|