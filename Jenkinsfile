pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout del código desde el repositorio Git
                checkout scm
            }
        }

        stage('Prepare Project') {
            steps {
                script {
                    // Crear estructura del proyecto y archivos de configuración
                    sh '''
                        mkdir -p src/main/java/com/example
                        echo 'package com.example; public class App { public static void main(String[] args) { System.out.println("Hello, SonarQube!"); } }' > src/main/java/com/example/App.java
                        echo 'sonar.projectKey=hola-mundo' > sonar-project.properties
                        echo 'sonar.projectName=Hola Mundo' >> sonar-project.properties
                        echo 'sonar.projectVersion=1.0' >> sonar-project.properties
                        echo 'sonar.sources=src/main/java' >> sonar-project.properties
                        echo 'sonar.language=java' >> sonar-project.properties
                        echo 'sonar.java.binaries=.' >> sonar-project.properties
                    '''
                }
            }
        }

        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool 'SonarQubeScanner'
                    withSonarQubeEnv('SonarQube') {
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed.'
        }
    }
}
