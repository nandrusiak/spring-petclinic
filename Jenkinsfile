pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh './mvnw package'
                archiveArtifacts artifacts: 'target/*.jar'
            }
        }
    }
}
