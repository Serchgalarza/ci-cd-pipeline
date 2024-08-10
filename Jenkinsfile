pipeline {
    agent any

    environment {
        SONARQUBE = 'SonarQube'  // Nombre del servidor SonarQube 
configurado en Jenkins
        SONARQUBE_SCANNER_HOME = tool name: 'SonarQube Scanner', type: 
'SonarQubeScanner'
    }

    stages {
        stage("Check SonarQube Configuration") {
            steps {
                script {
                    echo "Checking SonarQube Configuration"
                    echo "SONARQUBE: ${env.SONARQUBE}"
                    echo "SONARQUBE_SCANNER_HOME: 
${env.SONARQUBE_SCANNER_HOME}"
                    
                    // Verificar si el SonarQube Scanner está en el PATH
                    sh 'echo $SONARQUBE_SCANNER_HOME/bin/sonar-scanner 
--version'

                    // Verificar si la URL del servidor SonarQube es 
accesible
                    sh 'curl -I http://<tu-servidor>:9000'
                }
            }
        }
        
        // Otros stages...
    }
}

