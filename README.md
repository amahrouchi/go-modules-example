# How to use go modules

- Udemy: https://ankorstore.udemy.com/course/le-langage-go-formation-complete/learn/lecture/21134208#questions

Explication du la gestion de dépendances en Go

## Creation du ficher `go.mod` 
```
go mod init <organization/project>
```

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