### Extraire une adresse email d'une cellule (A1 par exemple)
```
=iferror(Regexextract(A1;"[A-z0-9._%+-]+@[A-z0-9.-]+\.[A-z]{2,4}");"")
```
