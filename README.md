# How to use go modules

- Udemy: 
  - https://ankorstore.udemy.com/course/le-langage-go-formation-complete/learn/lecture/21134208#questions

Explication du la gestion de dépendances en Go

## Creation du ficher `go.mod` 
**N.B.:** Pas besoin de se mettre dans le `GOPATH`, on peut créer notre projet où on le souhaite dans notre arborescence.

On créé donc notre répertoire qui servira de racine à notre projet et on se place dedans avant de lancer la commande :
```
go mod init <organization/project>
```

## Installation d'une dépendance

On ajoute ensuite dans le code la lib qu'on veut utiliser. Ici:
```go
import (
    log "github.com/sirupsen/logrus"
)
```

Puis on fait un :
```
go get
```

Go télécharge la dépendance et inscrive dans le fichier `go.mod` son nom et la version dans laquelle 
elle a été installé. De cette manière, lors de prochaines installation, la dépendance en question sera téléchargée
dans la bonne version.

## Autres commandes utiles

### Mise à jour à la dernière version disponible :
```
go get github.com/sirupsen/logrus
```

### Lister tous les modules inclus dans le projet :
```
go list -u -m all
```

### Supprimer une dépendance :

Si une dépendance n'est plus référencée dans le code source, elle n'a plus besoin
d'apparaitre dans le fichier `go.mod`. Pour nettoyer ce fichier des dépendances inutiles,
il suffit de lancer la commande :

```
go mod tidy
```
