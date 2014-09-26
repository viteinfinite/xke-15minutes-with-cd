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

^ [S]

---

# La méthodo

## La rétro
### En fin de sprint

^ [S]
Et ben... pas chez nous non plus - aucune rétro

---

# La méthodo

## Daily
### tous les jours

^ [S] Généralement on fait un daily tous les jours
Et bien nous, on en faisait jamais

---

# La méthodo

## Durée du sprint
### 1 semaine

^ [S]

---

# La méthodo

## Démo

![](images/demo_appletv.jpg)

^ [S]

---

# La méthodo

## Démo

![](images/demo_chromecast.jpg)

^ [S]

---

# La méthodo

## Magic Cycle en V

---

![](http://33.media.tumblr.com/e986dd7b4537cb6c5a11a684bc472ed2/tumblr_mx34dx3oty1t0a0k9o1_400.gif)

^ [S]

---

# La méthodo

## Magic estimation

^ [S]

---

# La méthodo

## Pilotage avec eXceL

![inline](images/pilotage_xls.png)

^ [S]
Oui Excel, l'outil agile

---

# La méthodo

## Pilotage avec XL

![inline](images/pilotage_xl.jpg)

^[S]
Au niveau de la méthodo, on a pris le choix de tout piloter par Excel<br />
[G]
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

^ [S]

---

# Les services web

![fit](images/ws_xoxo.png)

^ [S]
Et je vous parle même pas des écrans de l'application où il faut appeler et cumuler 8 web services pour avoir un résultat
*TODO: transition*

---

![original](images/ws_full.png)

^ [G]
Voila c'est cet espèce de truc déguelasse à parser qu'on a en permanence

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
En vérité c'est plutôt comme ça
Il faut retrouver dans le XML plein de valeurs et les concaténer entre elles<br />
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
Et puis tant qu'à faire, autant les rendre  super compliqués à être utilisés
Idéalement pour un écran suivant j'ai besoin d'un WS avec un noeud model et le nom "Renault Clio 3" dans un champ name
J'ai aussi besoin de l'image
Normal quoi

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
En plus de ça
Leurs WS contiennent des balises XML à des endroits qui devraient contenir du texte<br />
Ça serait trop facile sinon

---

# Les services web

- REST-like (mais pas RESTful)
- XML + JSON
 - content-type="text/plain"
 - Tous les services sont en XML
 - La moitié aussi dispo en JSON
 - 1 WS est en JSON uniquement

^ [G]
- On va dire que c'est du REST
- Avec un content-type text/plain parce qu'il faut pas déconner non plus<br />
- Tous leurs services web sont en XML sauf 1
- Du coup t'es obligé côté code de faire une stack qui gère les 2

---

# La recette

^ [G]
Par contre un truc qu'on aime pas, c'est leurs Services Webs

---

# La recette

![](images/postpone_tears0.gif)

^ [G]
Mais bon c'est le client, c'est lui qui nous paye et du coup on l'aime bien quand même.

---

# La recette

![](images/postpone_tears1.gif)

^ [G]
Et me fait EXACTEMENT le même coup la semaine suivante

---

# La recette

![](images/postpone_tears2.gif)

^ [G]
Il teste que dalle, reporte la release

---

# La recette

![](images/postpone_tears3.gif)

^ [G]
Je me fais chier à sortir son app dans les temps

---

# La recette

![](images/postpone_tears4.gif)

^ [G]
Et ça c'est ma réaction quand il décale la release du projet

---

# La recette

![](images/postpone_shocked.gif)

^ [G]
Ça c'est un peu la réaction de notre PO quand il s'est rendu compte que la story correspondait pas à ce qu'il attendait.
Par contre, ce qu'il attendait des stories, il nous l'écrivait pas dans les BDD... ça aurait été trop facile sinon

---

# La recette

##[fit]Ce qui devait arriver arriva

###[fit]-> Release Android réportée

^ [G]
Et le jour de la release
Sinon c'est pas drôle<br />
Et du coup "ce qui devait arriver arriva"... La release Android a été reportée<br />
Le PO avait 1 mois et demi pour tester une feature, et le jour de la release finalement il se met à faire la recette

---

# La recette

## [fit] 10 minutes

^ [G - S]
"La recette : 10 minutes !"

---

# La recette

## ~~1 sprint~~
## ~~1 jour~~
## ~~1 heure~~
## 10 minutes

^ [S]

---

# La recette

## ~~1 sprint~~
## ~~1 jour~~
## 1 heure

^ [S]

---

# La recette

## ~~1 sprint~~
## 1 jour

^ [S]

---

# La recette

## ~~1 sprint~~

## Nous sommes agiles !

^ [S]

---

# La recette

## 1 sprint

^ [S]

---

# Fin projet

^ [S]

---

# La rétro

![inline](images/retro.jpg)

^ [S]

---

# Le résultat / Android

![inline fit](images/screenshot_playstore_01.png)![inline fit](images/screenshot_playstore_02.png)![inline fit](images/screenshot_playstore_03.png)

^ [S]
Bannières dans les screenshots

---

# Le résultat / iOS

![](images/screenshot_appstore_01.jpeg)![inline fit](images/screenshot_appstore_02.jpeg)![inline fit](images/screenshot_appstore_03.jpeg)

^ [S]

---

# Applis sur les Stores

![inline fill](images/store_playstore.png)
![inline fill](images/store_appstore.png)

^ [S]

---

# Publicité

![](http://i.giphy.com/FKcC27kUBByAo.gif)

^ [S]

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

^ [?]
On va vous parler de Caradisiac, une appli de news auto (comme turbo ou auto plus) qu'on a réalisé et qu'on a sorti dernièrement


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

^ [?]
On aura pas le temps pour les questions
