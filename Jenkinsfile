pipeline {
    agent any
    stages {
        stage('Check SonarQube Connection') {
            steps {
                script {
                    def response = sh(
                        script: 'curl -u sqp_62967d39d7beed11b3f737be37f979e82dc69331: http://34.82.231.134:9000/api/server/version',
                        returnStdout: true
                    ).trim()
                    echo "SonarQube Server Version: ${response}"
                }
            }
        }
    }
}
