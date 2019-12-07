### Extraire une adresse email d'une cellule (A1 par exemple)
```
=Regexextract(A1;"[A-z0-9._%+-]+@[A-z0-9.-]+\.[A-z]{2,4}")
```

### Extraire du texte avant une virgule (A1 par exemple)
```
=REGEXEXTRACT(A1;"(.*),")
```

### Extraire du texte aprés une virgule (A1 par exemple)
```
=REGEXEXTRACT(A1;",(.*)")

```
### Nettoyer le titre d'un scraping des résultats de recherche de profil Linkedin via un moteur de recherche (A1 par exemple)
```
=IF(REGEXMATCH(E3;" ...");REGEXREPLACE(E3;" ..."; "");REGEXEXTRACT(E3;"(.*) | LinkedIn"))
```
