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

Exemple pour une recherche : site:fr.linkedin.com/in -pub.dir "growth hacker" Paris

| Titre des résultats de recherche        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| Guillaume Enriquez - Growth Hacker - USTS \| LinkedIn      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

```
=IF(REGEXMATCH(E3;" ...");REGEXREPLACE(E3;" ..."; "");REGEXEXTRACT(E3;"(.*) | LinkedIn"))
```
