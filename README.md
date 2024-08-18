# ci-cd-pipeline

## Projet Java "Hola Mundo" avec Jenkins et SonarQube

### Description du Projet

Ce projet est un simple programme "Hola Mundo" écrit en Java. Le but de ce projet est de démontrer l'utilisation de Jenkins et SonarQube pour l'intégration continue et l'analyse de code.

### Configuration du Serveur

Pour ce projet, un serveur a été configuré sur Google Cloud Platform (GCP) avec Jenkins et SonarQube installés.

#### Installation de Jenkins et SonarQube

1. **Création d'une instance sur GCP** :
   - Créez une instance virtuelle sur Google Cloud Platform.
   - Connectez-vous à l'instance via SSH.

2. **Installation de Jenkins** :
   - Suivez la documentation officielle pour installer Jenkins sur votre serveur.
   - Configurez Jenkins selon vos besoins.

3. **Installation de SonarQube** :
   - Téléchargez et installez SonarQube sur votre serveur.
   - Configurez SonarQube pour qu'il puisse recevoir les analyses de code.

### Pipeline Jenkins

Le fichier `Jenkinsfile` dans le projet est utilisé pour automatiser l'intégration continue et l'analyse de code avec Jenkins et SonarQube.

## Images du Projet 

Voici quelques captures d'écran montrant les résultats de Jenkins et SonarQube :

### Exemple de Code

![Résultat Jenkins](src/main/resources/images/JenkinsPanel.png)

### Résultat de build sur Jenkins avec SonarQube Scanner

![Résultat Jenkins (SonarQube Scanner)](src/main/resources/images/31_sonarScanner.png)

### Résultat de build sur Jenkins avec POST sur SonarQube

![Résultat Jenkins (SonarQube) POST 1](src/main/resources/images/32_POSTSonarqube_1.png)
![Résultat Jenkins (SonarQube) POST 2](src/main/resources/images/32_POSTSonarqube_2.png)
