pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Si tienes el proyecto en un repositorio Git, realiza el checkout
                // git 'https://your-repository-url.git'
                // Si no, podrías copiar el código de ejemplo al workspace, como en este caso:
                script {
                    sh 'mkdir -p src/main/java/com/example'
                    sh 'echo \'package com.example; public class App { public static void main(String[] args) { System.out.println("Hello, SonarQube!"); } }\' > src/main/java/com/example/App.java'
                    sh 'echo \'sonar.projectKey=my-java-project\' > sonar-project.properties'
                    sh 'echo \'sonar.projectName=My Java Project\' >> sonar-project.properties'
                    sh 'echo \'sonar.projectVersion=1.0\' >> sonar-project.properties'
                    sh 'echo \'sonar.sources=src/main/java\' >> sonar-project.properties'
                    sh 'echo \'sonar.language=java\' >> sonar-project.properties'
                    sh 'echo \'sonar.java.binaries=.\' >> sonar-project.properties'
                }
            }
        }

        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool 'SonarQubeScanner'
                    withSonarQubeEnv('SonarQube') {
                        sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=my-java-project -Dsonar.host.url=http://34.82.231.134:9000 -Dsonar.login=sqp_62967d39d7beed11b3f737be37f979e82dc69331"
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
