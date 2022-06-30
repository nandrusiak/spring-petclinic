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
                withMaven(maven: 'maven3', mavenSettingsConfig: 'MySettings') {
                    sh "./mvnw clean deploy -Dmaven.test.skip=true"
                }
            }
        }
    }
}                        
