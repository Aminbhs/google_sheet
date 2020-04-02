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

Exemple pour une recherche : site:fr.linkedin.com/in -pub.dir "Tech marketer" Paris

| Sans la formule        | Avec la formule           |
| ------------- |:-------------:|
| Amin Bouhassoune - Tech marketer - Freelance \| LinkedIn      | Amin Bouhassoune - Tech marketer - Freelance      |
| Amin Bouhassoune - Tech marketer - Freelance ... | Amin Bouhassoune - Tech marketer - Freelance      |


```
=IF(REGEXMATCH(E3;" ...");REGEXREPLACE(E3;" ..."; "");REGEXEXTRACT(E3;"(.*) | LinkedIn"))
```

### Tester si le IMPORTXML marche pour un site (Si le titre de la page ne s'affiche pas, pas la peine de continuer)
Ne pas oublier "http://" ou "https://" en début d'URL.
```
=importxml("L'url à tester ici";"//title")
```

### Extraire l'email d'un mailto: dans une page HTML via un IMPORTXML
```
=importxml(A1; "//a[starts-with(@href, 'mailto')]/@href")
```
### Extraire la description d'un site
```
=importxml(A1; "//meta[@name='description']/@content")
```
### Bonus : Supprimer le mailto via une regex
```
=REGEXEXTRACT(A2;"mailto:(.*)\?")
```
- Mise à jours du de ImportHtml, ImportFeed, ImportData, ImportXml : 1 heure
- La formule importxml s'utilise seulement avec un site en https donc on peut l'ajouter avec une formule de concatenation

