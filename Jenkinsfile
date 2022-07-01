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
                withMaven(maven: 'maven3', mavenSettingsConfig: '7d04c18d-74a8-4f6c-bc35-72a3184391a8') {
                    sh "./mvnw -X deploy -Dmaven.test.skip=true"
                }
            }
        }
    }
}                        
