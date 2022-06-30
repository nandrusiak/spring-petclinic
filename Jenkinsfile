pipeline {
    agent any

    stages {
        stage('Maven Build') {
            steps {
                sh "./mvnw package -DskipTests=true"
            }
        }
        stage('Push to Nexus') {
            steps {
                sh "./mvnw clean deploy -Dmaven.test.skip=true"
            }
        }
    }
}
