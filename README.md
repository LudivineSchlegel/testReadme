# Projet integration continue
<!--
<img src="https://assets-cdn.github.com/images/modules/open_graph/github-mark.png" alt="logo git" height="20"/>

#<a href="https://github.com/">github</a>
#<b>boid</b>
#<i>italic</i>
-->
<h2>Bases</h2>
Projet se basant sur la documentation de déploiment d'une aplication web en Java avec Heroku:

https://devcenter.heroku.com/articles/getting-started-with-gradle-on-heroku

dépot original: https://github.com/heroku/gradle-getting-started

Integration continue avec <a href="https://travis-ci.org/">Travis CI</a>

lien : https://travis-ci.org/LudivineSchlegel/projet-CICD

<h2>Integration continue</h2>

Integration continue du dépot github vers le gitHeroku puis création de l'application.

création d'un fichier <a href="https://github.com/LudivineSchlegel/projet-CICD/blob/master/.travis.yml">.travis.yml</a>

3 étapes de déploiment organiser de la façon suivante :
```
stages:
  - install
  - test
  - name: deploy
    if: branch = master
```
  - install
  
compilation de l'application.

commande : 

```script: ./gradlew assemble```

  - test
  
test du bon fonstionnement de l'application

commande : 

```script: ./gradlew check```

et en parallèle test de fonctionnement scripte: 

commande : 

```script: echo "test en parallele"```

  - deploy
  
 deploiment sur heroku si sur branche masteur.
 
 commande :
 ``` 
    script: skip
    deploy: &heroku
       provider: heroku
       api-key: 
        secure: $HEROKU_API_KEY
       app: limitless-ravine-55613
```
avec $HEROKU_API_KEY une variable d'environement definie dans travis CI

<img src="Capture du 2018-02-05 10-36-46.png" alt="logo git"/>

<h2>problèmes rencontrés</h2>

principalement la prise en main de TRAVIS Ci : 

* documentaion faible, peu d'example
* partie "stage" et "job" très peu détailler et expliquer (élémments en version béta)
* documentation pour trouver comment faire une clef sécuriser sous heroku et l'intégrer dans trevis dificile à trouver. Donc déploiment de travis CI vers heroku difficile a mettre en place.
