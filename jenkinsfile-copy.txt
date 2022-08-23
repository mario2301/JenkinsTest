pipeline {
    agent { docker { image 'maven:3.8.5-openjdk-18' } }
    stages {
        stage('log version info') {
            steps {
                sh 'mvn --version'
                sh 'mvn clean install'
            }
        }
    }
}
