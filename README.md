# Projet integration continue

<h1>h1</h1>
<img src="https://assets-cdn.github.com/images/modules/open_graph/github-mark.png" alt="logo git" height="20"/>

<a href="https://github.com/">github</a>
<b>boid</b>
<i>italic</i>

<h2>Bases</h2>
Projet se basant sur la documentation de déploiment d'une aplication web en Java avec Heroku:

https://devcenter.heroku.com/articles/getting-started-with-gradle-on-heroku

dépot original: https://github.com/heroku/gradle-getting-started

Integration continue avec <a href="https://travis-ci.org/">Travis CI</a>

lien : https://travis-ci.org/LudivineSchlegel/projet-CICD

<h2>Integration continue</h2>

Integration continue du dépot github vers le gitHeroku puis création de l'application.

3 testes :

  - install
  
compilation de l'application :

commande : <i>./gradlew assemble</i>
  - test
  - name: deploy
if: branch = master
