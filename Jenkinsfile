pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'target/*.jar'
            }
        }
    }
}
