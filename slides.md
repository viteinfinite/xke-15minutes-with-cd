![](images/title_daytona.jpg)

#[fit]15 minutes avec l'équipe Caradisiac

^ Comme vous pouvez le voir, c'était plutôt éprouvant...<br />
C'était 15 minutes avec l'équipe Caradisiac<br />
Merci de nous avoir écouté

---

![fit](images/title_screenshot_caradisiac_search.png)

^ On cherchait une image de fond pour notre présentation<br />
Google Images "Caradisiac"

---

# TL;WL:

---

# Plan

---

# On se présente

---

# Caradisiac s'intègre dans le PEM CBM

- Comment ça marche niveau projet
- L'équipe (Xebia + CD)
- 0 Coach Agile
- Le dispositif

---

# Intro

- Durée du projet
- Contexte (Plateformes: web, utilisateurs, Cordova)
- But
- Montrer phonegap
- iOS: Alexis

---

# La méthodo

---

# La méthodo

## La rétro
### En fin de sprint

^ [?]
Et ben... pas chez nous non plus - aucune rétro

---

# La méthodo

## Daily
### tous les jours

^ [?] Généralement on fait un daily tous les jours
Et bien nous, on en faisait jamais

---

# La méthodo

## Durée du sprint
### 1 semaine

---

# La méthodo

## Démo

![](images/demo_appletv.jpg)

---

# La méthodo

## Démo

![](images/demo_chromecast.jpg)


---

# La méthodo

## Magic Cycle en V

---

![](http://33.media.tumblr.com/e986dd7b4537cb6c5a11a684bc472ed2/tumblr_mx34dx3oty1t0a0k9o1_400.gif)

---

# La méthodo

## Magic estimation

---

# La méthodo

## Pilotage avec eXceL

![inline](images/pilotage_xls.png)

^ [?]
Oui Excel, l'outil agile

---

# La méthodo

## Pilotage avec XL

![inline](images/pilotage_xl.jpg)

^[?]
Au niveau de la méthodo, on a pris le choix de tout piloter par Excel<br />
[? autre]
- Non non, "éxel", pas "ixel"

---

//TODO: [S] iOS Code très peu spécifique 

---

# Les devs

- Complexité des WS XML et JSON
- Comment on construit la page
- iOS (KIF) (S)
- Android (Spoon / Sonar) (G)
- Analytics
- Les modifs WS: le lendemain en prod (devops au top)
	- En fait... Coda

---

# Les services web

![fit](images/ws_xoxo.png)

^ [G]
*TODO: transition*

---

![original](images/ws_full.png)

^ [G]
Voila c'est cet espèce de truc déguelasse à parser qu'on a en permanence<br />
Et je vous parle même pas des écrans de l'application où il faut appeler et cumuler 8 web services pour avoir un résultat

---

![original](images/ws_scream.gif)

^ [G]
Non pas ça

---

# Les services web

## La compléxité

Actuellement

```
<result>
  <_connexion_db>OK</_connexion_db>
  <_erreurs/>
  <_data>
    <tag label="Clio 3" url="modele--renault-clio-3">
    <tag label="Renault" type="brand"/>
    <tag label="Clio" type="model"/>
    <logo path="/logos-ref/modele">modele--renault-clio-3.jpg</logo>
  </_data>
</result>
```

- Nom: *tag[type="brand"] + " " + tag[url="<url>"]*
- Image: *"http://images.caradisiac.com" + logo[path] + "/S5-" + logo*

^ [G]
Et encore, on a simplifié pour l'exemple parce qu'en vrai c'est plutôt ça

---

# Les services web

## La compléxité

![right](images/ws_clio3.png)

Idéalement

```
<model name="Renault Clio 3"
  image="logos-ref/modele/modele--
    renault-clio-3/S5-modele--renault-clio-3.jpg" />
```

^ [G]

---

# Les services web

## Du XML qui n'en est pas

```
<commentaire>
  <line>
     Salut <smiley mnemo=":hello:"/> les gamins <smiley mnemo=":lol:"/> !
  </line>
</commentaire>
```

> *<![CDATA[]]>* ? Connaît pas

^ [G]
Leurs WS contiennent des balises XML à des endroits qui devraient contenir du texte<br />
En plus de nous filer les WS sans content-type ils nous filent des XML invalides
Ça serait trop facile sinon

---

![fit](images/ws_complexity.gif)

^ [G]
Mais du coup, sur Android j'ai 15 services en XML... et 1 en JSON<br />
Connards<br />
Sur iOS le ratio XML/JSON, c'est du 50/50

---

# Les services web

- REST-like (mais pas RESTful)
- XML + JSON
 - content-type="text/plain"
 - Tous les services sont en XML
 - La moitié aussi dispo en JSON
 - 1 WS est en JSON uniquement

^ [G]
REST pour faire joli, pas pour Joachim<br />

---

# La recette

---

- Release Android réportée (G) // TODO

^ [G] Et du coup ça m'a bien fait chier pour Android
Parce que la recette, notre PO le fait le jour de la release
[SLIDE: NORMAL]
Et, alors qu'il aurait pu tester depuis 1 mois et demi une feature... todo

---

# La recette

## [fit] 10 minutes

^ [?]
Ensemble: La recette: 10 minutes !

---

# La recette

## ~~1 sprint~~
## ~~1 jour~~
## ~~1 heure~~
## 10 minutes

---

# La recette

## ~~1 sprint~~
## ~~1 jour~~
## 1 heure

---

# La recette

## ~~1 sprint~~
## 1 jour

---

# La recette

## ~~1 sprint~~

## Nous sommes agiles !

---

# La recette

## 1 sprint

---

# Fin projet

---

# La rétro

![inline](images/retro.jpg)

---

# Le résultat / Android

![inline fit](images/screenshot_playstore_01.png)![inline fit](images/screenshot_playstore_02.png)![inline fit](images/screenshot_playstore_03.png)

^ Bannières dans les screenshots

---

# Le résultat / iOS

![](images/screenshot_appstore_01.jpeg)![inline fit](images/screenshot_appstore_02.jpeg)![inline fit](images/screenshot_appstore_03.jpeg)

---

# Applis sur les Stores

![inline fill](images/store_playstore.png)
![inline fill](images/store_appstore.png)

---

# Publicité

![](http://i.giphy.com/FKcC27kUBByAo.gif)

---

# Publicité

## [fit] Caradisiac :heart: Pub

^ [S]
C'est une grande histoire d'amour

---

# Commentaires positifs

![inline fit](images/commentaires_itunes_01.png)
![inline fit](images/commentaires_itunes_02.png)
![inline fit](images/commentaires_itunes_03.png)

^ [S]
Linette est Aline

---

# Commentaires positifs

![inline fit](images/commentaires_playstore_01.png)
![inline fit](images/commentaires_playstore_02.png)

^ [S]
Voici d'ailleurs quelques commentaires sur les stores
A tel point qu'elle apparaît même dans les captures d'écran du store

---

# Conclusions

---

TODO

---

# Merci

^ [?] On va vous parler de Caradisiac, une appli de news auto (comme turbo ou auto plus) qu'on a réalisé et qu'on a sorti dernièrement


---

# Merci

![](images/thanks_clap.gif)

^ [?]
Mais merci d'être venus si nombreux<br />
[? autre]
Même si vous aviez pas trop le choix<br />
[?]
Vous êtes vraiment un public formidable

---

# Questions ?

^ On aura pas le temps pour les questions

