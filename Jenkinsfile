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
                withMaven(maven: 'maven3', mavenSettingsConfig: 'db461fc2-1ff0-4af8-baf6-a48384b1ff6e') {
                    sh "./mvnw -s ~/.m2/settings.xml clean deploy -Dmaven.test.skip=true"
                }
            }
        }
    }
}                        
