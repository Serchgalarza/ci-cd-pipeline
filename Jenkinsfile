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
                withSonarQubeEnv('SonarQube') {  // Usa el nombre de la configuración de SonarQube en Jenkins
                    sh """
                        /opt/sonar-scanner/bin/sonar-scanner \
                            -Dsonar.projectKey=ci-cd-pipeline \
                            -Dsonar.host.url=http://34.82.231.134:9000 \
                            -Dsonar.login=sqp_62967d39d7beed11b3f737be37f979e82dc69331
                    """
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

